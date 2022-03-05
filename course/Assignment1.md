1.

(a)
$$
\begin{align}
&1. Θ(n)=n^4\\
&2. Θ(n)=n^2\\
&3. Θ(n)=n\log{n}\\
&4. Θ(n)=n^4\\
&5. Θ(n)=n^2(\log{n})^3\\
\end{align}
$$
(b) The sorted Theta classes look like this:
$$
\begin{align}
&1. Θ(1)\\
&2. Θ(\log{n})\\
&3. Θ(n^2)\\
&4. Θ(n^3)\\
&5. Θ(\frac{n^3}{\log{n}})\\
&6. Θ(n^3\log{n})\\
&7 Θ(2^n)\\
&8 Θ(n!)\\
\end{align}
$$
(c) 
$$
\begin{align}
&1. n_0=5, c=1\\
&2. n_0=10, c=1\\
&3. n_0=1, c=1\\
\end{align}
$$
2.

(a)

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222174927851.png" alt="image-20220222174927851" style="zoom:50%;" />

(b)

This is always unique for a fixed array and a fixed BST. Because once the array and BST are determined, the size relationship of the items is also determined.



<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222175022437.png" alt="image-20220222175022437" style="zoom:50%;" />

(c)

Nodes with red background are unbalanced nodes. Because the height difference between the left and right subtrees of these nodes is more than 1.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222180705384.png" alt="image-20220222180705384" style="zoom:50%;" />

(d) The BST after deleting 1:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222181531345.png" alt="image-20220222181531345" style="zoom:50%;" />

The BST after deleting 2:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222181701456.png" alt="image-20220222181701456" style="zoom:50%;" />

The BST after deleting 33:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222181952660.png" alt="image-20220222181952660" style="zoom:50%;" />

(e)

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220222182321939.png" alt="image-20220222182321939" style="zoom:50%;" />

3.

Running Times:

If n<m, the running time of fnA is O(nlogm).

If m<n, the running time of fnA is O(mlogn).



Explanation:

Because this algorithm takes the larger arrays of A and B and finds all the elements in the smaller arrays bisection and adds them to a linkedlist.



Result:

The result is always sorted because both initial arrays are sorted. And the smaller arrays are traversed sequentially.



4.

1. Input list: [6, 26, 21, 13, 10, 30, 22, 25]

   pivot=6

   Swap(26,10), Swap(21,13)

   Result after Partition: [6, 10, 13, 26, 30, 22, 25]. 

2. Subarray1:[10, 13]

   Subarray2:[26, 30, 22, 25]

   

3. Subarray1  Partition: [10, 13]. 

   pivot=10, only one number is left.

   result: [10, 13].

   Subarray2 result after Partition: [26, 30, 22, 25].

   pivot=26

   swap(30,25) 

   Result: [26, 25, 22, 30]

4. Subarray3:[25, 22]:

   Pivot=25, only one number is left.

   Result: [22, 25]

5. Combine the subarray and pivot and get the final result: [6, 10, 13, 21, 22, 25, 26, 30]

   

5.

This can be done with a data strcture based on AVL. Each node stores the **deadline** and **cost**.


- Add a new unpaid bill:

  

  Only requires maintaining the AVL tree.

  Time: O(log(n))

  

- Find the bill with the earliest deadline

  

  Iterate the AVL with in-order. You can find all the bills in order of deadline.

  Time: O(log(n))

  

- Calculate the total cost of bills with deadlines up to T, for any time T.

  Iterate the AVL with in-order until the node that deadline is latter than T. Sum up all nodes's cost we iterated.

  Time: O(log(n))



