**Sorting Algorithms:**
Sorting Terminology:
```
**What is in-place sorting?**
An in-place sorting algorithm uses constant space for producing the output (modifies the given array only). It sorts the list only by modifying the order of the elements within the list.
For example, Insertion Sort and Selection Sorts are in-place sorting algorithms
Merge Sort is not in-place, also the implementation for counting sort is not in-place sorting algorithm.
What are Internal and External Sortings?
When all data that needs to be sorted cannot be placed in-memory at a time, the sorting is called external sorting. External Sorting is used for massive amount of data. Merge Sort and its variations are typically used for external sorting
When all data is placed in-memory, then sorting is called internal sorting.

**Stability in sorting algorithms:**
Stability is mainly important when we have key value pairs with duplicate keys possible 
A sorting algorithm is said to be stable if two objects with equal keys appear in the same order in sorted output as they appear in the input array to be sorted.
stability means that equivalent elements retain their relative positions, after sorting.
Some Sorting Algorithms are stable by nature, such as Bubble Sort, Insertion Sort, Merge Sort, Count Sort etc.

Quick Sort, Heap Sort etc., can be made stable by also taking the position of the elements into consideration. 

Efficiency of an algorithm depends on two parameters:
1. Time Complexity
2. Space Complexity

https://www.geeksforgeeks.org/time-complexities-of-all-sorting-algorithms/
```


**Selection Sort:**
```
The selection sort algorithm sorts an array by repeatedly finding the minimum element (considering ascending order) from unsorted part and putting it at the beginning. The algorithm maintains two subarrays in a given array.
1) The subarray which is already sorted. 
2) Remaining subarray which is unsorted.

In every iteration of selection sort, the minimum element (considering ascending order) from the unsorted subarray is picked and moved to the sorted subarray. 
  private static void selectionsort(int[] arr){
        int minIndex=0;
        for(int i=0;i<arr.length-1;i++){
            minIndex=i;
            for(int j=i+1;j<arr.length;j++){

                if(arr[j]<arr[minIndex])
                    minIndex=j;
            }

            if(minIndex!=i) {
                int temp = arr[i];
                arr[i] = arr[minIndex];
                arr[minIndex]=temp;
            }
        }
    }
```

**BubbleSort:**
Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in wrong order.
Best case occurs when array is already sorted.
Worst case occurs when array is reverse sorted
```
    private static void bubbleSort(int[] arr,int n){
        boolean swapped=true;
        int temp=-1;
        for(int i=0;i<n-1;i++){
            swapped=true;
            for(int j=0;j<n-1-i;j++){
                if(arr[j]>arr[j+1]){
                    temp=arr[j];
                    arr[j]=arr[j+1];
                    arr[j+1]=temp;
                    swapped=false;
                }
            }
            if(swapped)
                break;
        }
    }

    private static void bubbleSortRec(int[] arr,int n){

        if(n==1)
            return;
        int temp=0;
        boolean swapped=true;
        for(int i=0;i<n-1;i++){
            if(arr[i]>arr[i+1]){
                temp=arr[i];
                arr[i]=arr[i+1];
                arr[i+1]=temp;
                swapped=false;
            }
        }

        if(swapped)
            return;
        bubbleSort(arr,n-1);
    }

```


