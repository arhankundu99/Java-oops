**Heap Implementation**: <https://www.youtube.com/watch?v=LhhRbRXhB40> <br/>
**Map Implementation**: <https://www.youtube.com/watch?v=c3RVW3KGIIE>

# HashMap and HashTable
HashMap and HashTable are data structures which store data in key-value pairs <br/>
Amortized Complexity of both hashmap and hashtable is O(1) <br/>

# Difference between hashmap and hashtable
HashMap can have one null key and multiple null values, whereas hashtable only contains key and value which are not null. <br/>
HashMap is not synchronized (It is not thread safe. (Eg: Without using synchronization, let's say there are two threads which are accessing a variable `foo`. Now thread1 may not 
see the change that the thread2 made to the variable `foo` or worse it may only have been half changed) <br/>
Hashtable is synchronized. <br/>

Read more about threads and processes: <https://www.guru99.com/difference-between-process-and-thread.html>

# What is hashing?
Hashing is a process of changing the value of a key to a hashcode using a hash function.

# Applications of hashing
1) Used in string matching algorithm: Rabin-Karp algorithm
2) When we login to a website, the password is first converted to a hash value and then it is checked in the servers. Servers do not contain the real passwords for security reasons.They contain the hash values of passwords.
3) Phone book :)

# References 
1) <https://www.geeksforgeeks.org/differences-between-hashmap-and-hashtable-in-java>
2) <https://www.geeksforgeeks.org/applications-of-hashing>
3) <https://stackoverflow.com/questions/1085709/what-does-synchronized-mean>

# Comparing same objects in map or set
```java
import java.io.*;
import java.util.*;

class GFG {
	public static void main (String[] args) {
		Set<pair>set = new HashSet<>();
		set.add(new pair("Apple", 40));
		set.add(new pair("Apple", 40));
		
		set.add(new pair("Banana", 40));
		set.add(new pair("Banana", 50));
		
		System.out.println(set.size());
		
	}
}
class pair{
    String name;
    int val;
    pair(String name, int val){
        this.name = name;
        this.val = val;
    }
    @Override
    public int hashCode(){
        int hashCode = val + name.hashCode();
        System.out.println(hashCode);
        return hashCode;
    }
    @Override
    public boolean equals(Object obj){
        pair pair = (pair) obj;
        if(pair.name.equals(this.name) && pair.val == this.val)return true;
        return false;
    }
}
```
