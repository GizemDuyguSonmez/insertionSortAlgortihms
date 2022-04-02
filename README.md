# Insertion Sort Algorithm
Insertion sort is a simple algorithm that builds the final sorted array(or list) one item at a time. It's much less efficent on large lists than more advanced algorithms such as quicksort, heapsort, merge sort.

The Insertion Sort algorithm repeats the operations of shifting large elements to the right in the array by comparing the element with the previous elements, starting from the second element.

For example, sort **[22, 27, 16, 2, 18, 6]** in principles with insertion sorting.

Firstly let's we check complexity:
It is not ordered, so it is not best case. It is not exactly opposite than we need to, so it is not worst case. So, it is average case. Then time complexity is O(n^2).

```
İnital array is [22, 27, 16, 2, 18, 6]:
 22,27,16,2,18,6 --> 22 is stored and 27 started to compare with first element. So, 27 is greater than first.
=> [22, 27, 16, 2, 18, 6]

22,27,16,2,18,6 --> 27 was stored and 16 started to compare with stored ones. 16 is smaller than stored ones. So, 16 will go to beginning.
 => [16, 22, 27, 2, 18, 6]

16,22,27,2,18,6 --> 16 was stored and 2 started to compare with stored ones. 2 is smaller than stored ones. So, 2 will go to beginning.
=> [2, 16, 22, 27, 18, 6]

2,16,22,27,18,6 --> 2 was stored and 18 started to compare with stored ones. 18 will go to between 16 and 22.
=> [2, 16, 18, 22, 27, 6]

2,16,18,22,27,6 --> 18 was stored and 6 started to compare with stored ones. 6 will go to between 2 and 16.
=> [2, 6, 16, 18, 22, 27]

2,6,16,18,22,27 --> 6 was stored and elements were ordered in ascending by insertion algorithm.

The array sorted.
``` 
Time Complexity of Insertion Sort  : 
1. *The worst case time complexity of Insertion sort is O(N^2)*
2. *The average case time complexity of Insertion sort is O(N^2)*
3. *The time complexity of the best case is O(N).*

**Question:** What case does the number 18 fall into after the array sorted?
Sorted array: [2, 6, 16, 18, 22, 27]
The number 18 fall into **avarage case**.

**Question:** Sort the array **[7,3,5,8,2,9,4,15,6]** with insertion sorting and write the first four steps.

```
First step:   [3, 7, 5, 8, 2, 9, 4, 15, 6]
Second step:  [3, 5, 7, 8, 2, 9, 4, 15, 6]
Third step:   [2, 3, 5, 7, 8, 9, 4, 15, 6]
.
.
.
```

```
using System;
namespace InsertionSortDemo
{
    public class Example
    {
        public static void Main(string[] args)
        {
            int[] arr = new int[6] {22,27,16,2,18,6 };
            int n = 6, i, j, val;
            Console.WriteLine("Insertion Sort");
            Console.Write("Initial array is: ");
            for (i = 0; i < n; i++)
            {
                Console.Write(arr[i] + " ");
            }
            for (i = 1; i < n; i++)
            {
                val = arr[i];
                for (j = i - 1; j >= 0;)
                {
                    if (val < arr[j])
                    {
                        arr[j + 1] = arr[j];
                        j--;
                        arr[j + 1] = val;
                    }
                    else
                    {
                        break;
                    }   
                }
            }
            Console.Write("\nSorted Array is: ");
            for (i = 0; i < n; i++)
            {
                Console.Write(arr[i] + " ");
            }

            Console.ReadKey();
        }
    }
}
```
