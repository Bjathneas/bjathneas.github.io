# Index
1. [What are Arrays](#what-are-arrays)
2. [Indexing an Array](#indexing-an-array)
3. [Array Initialization](#array-initialization)
4. [Array Operations](#array-operations)
5. [Types of Arrays](#types-of-arrays)
6. [Arrays Pros and Cons](#arrays-pros-and-cons)
# What are Arrays
Arrays are a type of data structure that stores data of the same type in [contiguous memory](https://www.geeksforgeeks.org/difference-between-contiguous-and-noncontiguous-memory-allocation/). Arrays have a fixed size, this is because we cannot insure that changing the size of the array will result in the utilization of contiguous memory

# Indexing an Array
* **zero-based indexing**: The first element in an array is *Array<sub>0</sub>*
* **one-based indexing**: The first element in an array is *Array<sub>1</sub>*
* **N-based indexing**: The base of the array can be freely chosen, ussually allows for negative numbers or other data types. *Array<sub>n</sub>*

# Array Initialization
By default the array is not initialized, initializing an array can be done in the following ways:
1. **Passing no value within initializer**: You can initialize the array without passing values.
	`int arr[10] = {};`
2. **By passing specific values within initializer**: You can initialize the array with values as long as the number of values are less than or equal to the array size
	`int arr[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};`
3. **By passing specific values without declaring the size**: You can initialize and array like #2 but without declaring the array size as it will be calculated at compile time!
	`int arr[] = {0, 1, 2, 3};`
4. **Universal Initialization**: You can even omit the **=** sign
	`int arr[] {0, 1, 2, 3};`
# Array Operations
## Accessing
To access an element in an Array, pass the index of the element to the Array
```
int arr[] {0, 1, 4};
int second_element = arr[2];//second_element = 4
```
**Time Complexity of *O(1)***
## Insertions
When inserting an element in an Array, just access the Array at its element and set its value
```cpp
int arr[] {0, 1, 2, 3}//{0, 1, 2, 3}
arr[2] = 5;//{0, 1, 5, 3}
```
**Time Complexity of *O(1)***
## Searching
There are 2 ways of searching an Array
1. Searching using an in range loop
```cpp
int arr[] {0, 1, 2, 3, 4};
for(int i = 0; i < 5; i++) {
	std::cout << arr[i] << '\n';//Prints element at index
}
```
2. Searching using an object loop
```cpp
int arr[] {0, 1, 2, 3, 4};
for(int i : arr) {
	std::cout << i << '\n';//Prints element
}
```
Searching an Array has a **Time Complexity of *O(N)***
# Types of Arrays
There are 2 types of Arrays
1. **One-dimensional**: These Arrays have a single dimension
`int arr[] {0, 1, 2};`
2. **Muli-dimensional**: These Arrays have multiple dimensions
`int arr[][] {{0, 1},{2, 4}};`

Note Multi-dimensional Arrays have a different Time Complexity depending on the number of dimensions
# Arrays Pros and Cons
## Pros
* Random access of elements. Its quick to access an element by its index
* Arrays have better cache locality, which means better performance
* Arrays store multple elements of the same type under the same variable
* Can be used to create more complex data structures like Stacks, Queues, Heaps, Hash Tables, the list goes on
## Cons
* Arrays are static data structures, you cannot change their size
* Searching an Array is inefficient, especially when handling large amounts of data
# References
* [Data Structures - GeeksforGeeks](https://www.geeksforgeeks.org/what-is-array/)
