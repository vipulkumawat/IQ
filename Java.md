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