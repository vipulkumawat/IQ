**Searching Algorithms:**
Sequential Search: List or array is traversed sequentially and every element is searched. ex: linear search
Interval Search:  specifically designed for searching in sorted data-structures. ex: binary search

Linear search:  time complexity  is O(n).
Linear search is rarely used practically because other search algorithms such as the binary search algorithm and hash tables allow significantly faster-searching comparison to Linear search.

```
private static int ilsearch(int[] arr,int searchEle){
        int left=0,right=arr.length-1;
        while(left<=right){
            if(arr[left]==searchEle){
                return left;
            }
            if(arr[right]==searchEle){
                return right;
            }
            left++;
            right--;
        }
        return -1;
    }
``` 
Binary Search: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty. O(logN)

```
    static int binarySearchItr(int[] arr,int ele){
        int l=0,r=arr.length-1;
        while(l<r){

            int m=l+(r-l)/2;

            if(arr[m]==ele)
                return m;

            if(arr[m]<ele)
                l=m+1;
            else
                r=m-1;
        }
        return -1;
    }


    private static int binarySearch(int[] arr,int x,int low,int high){
        if(low<=high){
            int mid=low+(high-low)/2;
            if(arr[mid]==x)
                return mid;
            if(arr[mid]<x){
                return binarySearch(arr,x,mid+1,high);
            }
            return binarySearch(arr,x,low,mid-1);
        }
        return -1;
    }


```

Bitwise binary search:


```
    static int bitwiseBinarySearch(int[] arr,int target){

        int index,power;

        // Compute the first power of 2 that is >= size
        for(power=1;power<arr.length;power<<=1);

        // loop while(power > 0)
        // and divide power by two each iteration
        for(index=0;power>0;power>>=1){

            // if the next condition is true
            // it means that the power value can
            // contribute to the "sum"(a closer index where target might be)
            if(index+power<arr.length && arr[index+power]<=target)
                index+=power;
        }

        // if the element at position [index] == target,
        // the target value is present in the array
        if(arr[index]==target)
            return index;

        // else the value is not present in the array
        return -1;
    }
```


Jump Search:  basic idea is to check fewer elements (than linear search) by jumping ahead by fixed steps or skipping some elements in place of searching all elements.What is the optimal block size to be skipped? 
In the worst case, we have to do n/m jumps and if the last checked value is greater than the element to be searched for, we perform m-1 comparisons more for linear search. Therefore the total number of comparisons in the worst case will be ((n/m) + m-1). The value of the function ((n/m) + m-1) will be minimum when m = √n
Important points: 
 

Works only sorted arrays.
The optimal size of a block to be jumped is (√ n). This makes the time complexity of Jump Search O(√ n).
The time complexity of Jump Search is between Linear Search ( ( O(n) ) and Binary Search ( O (Log n) ).
Binary Search is better than Jump Search, but Jump search has an advantage that we traverse back only once (Binary Search may require up to O(Log n) jumps, consider a situation where the element to be searched is the smallest element or just bigger than the smallest). So in a system where binary search is costly, we use Jump Search.

Interpolation Search:
Interpolation Search is an improvement over Binary Search for instances, where the values in a sorted array are uniformly distributed. Binary Search always goes to the middle element to check. On the other hand, interpolation search may go to different locations according to the value of the key being searched.  if the value of the key is closer to the last element, interpolation search is likely to start search toward the end side.


exponential search: O(logN)
Exponential search involves two steps:  
Find range where element is present
Do Binary Search in above found range.
Applications of Exponential Search: 

Exponential Binary Search is particularly useful for unbounded searches, where size of array is infinite. 
It works better than Binary Search for bounded arrays, and also when the element to be searched is closer to the first element.

```
 static int exponentialSearch(int[] arr,int x){

        if(arr[0]==x)
            return 0;
        int i=1;
        while(i<arr.length && arr[i]<=x)
            i=i*2;

        return Arrays.binarySearch(arr,i/2,Math.min(i,arr.length-1),x);
        
    }


```
SublistSearch: Timecomplexity: O(m*n) where m is the number of nodes in second list and n in first



