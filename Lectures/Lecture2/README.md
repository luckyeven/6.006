# Lecture 2: Data Structures Note
### Data Structure Interfaces
* A data structure is a way to store data, with algorithms that support operations on the data.
* Collection of supported operation is called interface or API.  

|Interface(API)|Data Structure|
|---|---|
|Specification |Representation|
|What data can store |How to store data|
|What operations are supported& What they mean|Alogorithms to support operations|
## Two Main Interfaces:

### Sequence Interface
* Maintain a sequence of items. Order is extrinsic
#### Problem
```Python
# items X0,X1,...,X(N-1)
# build(x): make a new DS for items in X
# len(): return N
# iter_seg(): output X0 to XN-1 in seg order
# get_at(i): return object Xi
# set_at(i,x): change Xi to x
# insert_at(i,x): insert x at index i
# delete_at(i):  delete item at index i
# get_first/last():
# set_first/last():
```
#### Solution

What data structure solves this?
static array A[0...n-1] 

> *ps: There is no static array in python, only dynamic array*
* O(1) per get_at/set_at/len
* O(n) per build/iter_seg  

This is called memory allocation model: allocate an array of size n in Θ(n) time; Space-> O(time).
### Set Interface

## Two Main Data Structure:
* Pointer based
* Array based
## Linked lists:
<img src="https://github.com/luckyeven/6.006/blob/main/pictures/linked_list.png?raw=true" width="98.39%" height="98.39%">

* allocate 1 item at a time. 
* connect items together with pointers
* Maintain global head pointer to keep tracking the list
* insert/delete_first(x) also O(1) time, by editing the head pointer.

## Dynamic Array: Python's List
* Instead of resizing array to exactly m, allow array to have size = Θ(n).
* When inserting & size =n, double size.
* Worst case, insert_last() still Θ(n)
* But resize only when n = 2^i
* A few insert cost linear time, but Θ(1) on average.

## Amortization
An operation takes T(n) amortized time if any k operations take <= k*T(n)