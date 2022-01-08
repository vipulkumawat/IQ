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