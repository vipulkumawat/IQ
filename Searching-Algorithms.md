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
Binary Search: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

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
