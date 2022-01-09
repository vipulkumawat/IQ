A hash table is well suited for this purpose because it supports fast lookup in near constant time. I say "near" because if a collision occurred, a lookup could degenerate to O(n)O(n) time. However, lookup in a hash table should be amortized O(1), O(1) time as long as the hash function was chosen carefully.


**Internal Implementations of Collections and their time complexities:**
Java Collection internally uses the primitive and core elements like Arrays and datastructures like  Linked List, Tree etc
Knowing which collection class to use for best performance and optimum result is the key.
```
Lists : List of things ( Classes that implement List Interface) List interface promises that the elements maintain the order in which they are added. 
That means it is a ordered Collection.
Sets : Unique things ( Classes that implement Set Interface)
Maps : Things with unique id ( Classes that implement Map Interface)
Queues : Things arranged in order ( Classes that implement Queue Interface)
```
**ArrayList:**
```
ArrayList: works on the principle of creating a array and adding elements to it.ArrayList is dynamic sized array. add(E element)
When a new element is added the capacity of the array elementData is checked and if it is completely filled that is all element 10 are filled, a new array is created with a new capacity by using Arrays.copyOf, If the elementData array is not exhausted the new element is added in the array.
So adding a element in a array may take more time as a completely new array needs to be created with greater capacity and the data in the old array is transferred into the new array.

add(index i, E element)
On adding a element at a particular index in ArrayList, ArrayList checks if a element is already present at that index. If no than the parameter is added at that index, otherwise a new array is created with the index kept vacant and the remaining element shifted to right.
get(int index)
The element present at that index in that array is returned. This is very fast. Why? Because there is no need to traverse through the nodes as is the case with other collection classes.
When to use ArrayList
When the requirement is fetch data frequently and adding data is not so frequent activity.
When not to use ArrayList
When the list is updated frequently
```

**LinkedList:**
```
Linked List
Ordered
As opposed to ArrayList, LinkedList does not store elements in a array. Linked List is a actually a collection of objects linked together using a reference to each other. So in assence a java.util.LinkedList is a Doubly Linked List.

add(E element )
 Every Time we call add(var);  a new instance of 'Entry' class is created and attached at the end of the list.
 
add(var, position)
Inserts the specified element at the specified position in this list.
Shifts the element currently at that position (if any) and any subsequent elements to the right. This is not as fast as ArrayList.
 
get(int index)
It iterates through the list and returns the element. This is very expensive and time consuming as opposed to ArraList.get(int index)

When to use LinkedList
When the elements are getting added and removed frequently.
 
When not to use LinkedList
When you want to access or fetch a element by index.
```

**Map:**
```
Map:
 Map is a special collection provided by Java. It helps to find a added element quickly.
Map allows you to add 2 elements. One called as key and the other as value
The logic to save and fetch a value is based upon the key.

```

**HashMap:**
```
HashMap
HashMap works on the principal of hashing. It stores values in the form of key-value pair and to access a value you need to provide the key.
HashMap is basically a 2 dimensional Singly Linked List. It can grow in both directions.
For efficient use of HashMap the 'key' element should implement equals() and hashcode() method. equals() method define that two objects are meaningfully equal. hashcode() helps HashMap to arrange elements separately in a bucket. So elements with same hascode are kept in the same bucket together.
All elements that are stored horizontally are said to be in the same bucket.
So when we want to fetch a element using get(K key), HashMap first identifies the bucket in which all elements of the same hascode as the hashcode of the 'key' passed are present. Now since it knows the bucket, it will only have to traverse through that bucket to fetch the actual object.

Then it uses the equals() method to identify the actual object present in the bucket.

For fast access to a value HashMap places a element (both key and value) in a SinglyLinkedList(Bucket). All the elements that have the same hascode are placed in the same SinglyLinkedList. The number of SinglyLinkedList(buckets) depends upon how many objects are present with different hashcode. To hold these buckets together a array is used. The size of the array is initially defined to 12. And it changes as new elements with different hascodes are added

HashMap also has some more variables which define the initial size of the array.

DEFAULT_LOAD_FACTOR = 0.75f;
DEFAULT_INITIAL_CAPACITY = 16;

```

**TreeMap:**
```
TreeMap:
Sorted
TreeMap is a structure which is designed to work as a Red - Black - Tree. Here each node has only two child nodes and the insertion is a tree happens same as the insertion strategy of Java Binary Search Tree 

The Tree Map has Key and Value in the node, while the BST only has the value.


So the elements in a TreeMap are always sorted.
The elements added is a TreeMap should implement comparable and provide implementation of compareTo method. On the basis of this TreeMap decides wether the node is smaller or greater than other node. If Comparable is not implemented, a class which is Comparator should be passed in the constructor of TreeMap. If both Comparable and Comparator are present TreeMap uses Comparator implementation.

TreeMap internally maintains a List of Nodes with each node being a Entry<K,V> class which is actually a implementation of Map.Entry<K,V> interface.

When we use put(K,V) method it checks if root is pointing anywhere if no it makes the instance of Entry<K,V> and point to root;
The constructor of Entry<K,V> takes key, value and parent. In this case parent is null;
For the next time we enter something using put(K,V) it first identifies the comparison mechanism to use. First it check the Comparator class is present or not . This class is passed when creating the instance of TreeMap. If not present it uses the Key's Comparable implementation.
It then traverse through root and compares each node with the node entered and depending upon the comparison places the node either left or right of the parent node.
```

**Set:**
```
that can not contain duplicate values. So if we want to have a unique collection, Set is the obvious choice.
```

**HashSet:**
```

```