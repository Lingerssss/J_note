# Assignment2

## 1.

### (1)

#### (a)

<img src="/Users/jiaxi.gong/Library/Application Support/typora-user-images/image-20220315012533422.png" alt="image-20220315012533422" style="zoom:50%;" />

#### (b)

Step1: Add 8 to the last position in the heap.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315012756167.png" alt="image-20220315012756167" style="zoom:50%;" />

Step2: Check the lowest node in the heap and adjust upward.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315013018145.png" alt="image-20220315013018145" style="zoom:50%;" />

Step3: Check the second-to-last node in the heap and adjust upward.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315013304323.png" alt="image-20220315013304323" style="zoom:50%;" />

Step4: Check the second tier node in the heap and there is no need to adjust. The final result is as shown above.

#### (c)

Step1: Swap the top node with the last node on the heap.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315021511414.png" alt="image-20220315021511414" style="zoom:50%;" />

Step2: Remove last node on the heap.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315021640420.png" alt="image-20220315021640420" style="zoom:50%;" />



Step3: Check the last layer node. No adjustment is required.

Step4: check the second layer node. Move the head node down.

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315021903010.png" alt="image-20220315021903010" style="zoom:50%;" />



### (2)

Step1:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315022110107.png" alt="image-20220315022110107" style="zoom:50%;" />

Step2:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315022151948.png" alt="image-20220315022151948" style="zoom:50%;" />

Step3:

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315022302291.png" alt="image-20220315022302291" style="zoom:50%;" />

### (3)

You can build priority queue with build_heap() method. And You can insert data into the priority queue using the insert() method.

You can also use delete_min() method to push the lowest-priority element off the priority queue.

```python
class BinaryHeap(object):
    def __init__(self):
        self.items = [0]

    def __len__(self):
        return len(self.items) - 1
      
    def percolate_up(self):
        i = len(self)
        while i // 2 > 0:
            if self.items[i] < self.items[i // 2]:
                self.items[i // 2], self.items[i] = \
                    self.items[i], self.items[i // 2]
            i = i // 2
		def insert(self, k):
        self.items.append(k)
        self.percolate_up()

    def percolate_down(self, i):
        while i * 2 <= len(self):
            mc = self.min_child(i)
            if self.items[i] > self.items[mc]:
                self.items[i], self.items[mc] = self.items[mc], self.items[i]
            i = mc

    def min_child(self, i):
        if i * 2 + 1 > len(self):
            return i * 2

        if self.items[i * 2] < self.items[i * 2 + 1]:
            return i * 2

        return i * 2 + 1
      
		def delete_min(self):
        return_value = self.items[1]
        self.items[1] = self.items[len(self)]
        self.items.pop()
        self.percolate_down(1)
        return return_value
      
		def build_heap(self, alist):
        i = len(alist) // 2
        self.items = [0] + alist
        while i > 0:
            self.percolate_down(i)
            i = i - 1
```



## 2.

### (1)

Put an element into a hash table is implemented in two steps:
1, Count an element’s hash value using a hash function.

2, The element is stored in the hash table according to its hash value 

In this question. Insert 3, 11, 16, 22 into the hash table.

3%7 =3, 3 is added in bucket3
11%7 =4, 11 is added to bucket 4
16%7 =2, 16 is added to bucket 2
22%7 =1, 22 is added to bucket 1

| Index | Key  |
| ----- | ---- |
| 0     |      |
| 1     | 22   |
| 2     | 16   |
| 3     | 3    |
| 4     | 11   |
| 5     |      |
| 6     |      |

And then if we need to insert an element 18, it needs to be added to the  bucket 4.

But the bucket4 already holds element 11. According to linear detection, 18 needs to be added to the next bucket 5.

| Index | Key  |
| ----- | ---- |
| 0     |      |
| 1     | 22   |
| 2     | 16   |
| 3     | 3    |
| 4     | 11   |
| 5     | 18   |
| 6     |      |

### (2)

For the delete operation. We first search for the location of the deleted number, and then examine each bucket to determine the element to move, starting with the next bucket at the deleted location, until we reach an empty bucket or return to the deleted location. When deleting, do not move a pair before its start bucket; otherwise, the search for the book pair may fail.

It is realized by fixed-point A and B operations. B increases successively and traverses backward in order to judge whether the value should move forward, and A is responsible for moving the number that should move forward.

| 0    | 1    | 2    | 3    | 4    | 5    | 6    | 7    | 8    | 9    | 10   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 0    | 1    | 12   | 62   | 51   | 50   | 17   | 18   | 28   | 39   | 21   |

1. BOTH a and b are greater than N, and the starting number of the number moving forward is also greater than N;

In the first case, there are two cases. The statement "Do not move a pair before its starting bucket" is true and false in both cases.

This statement is true, 17,28, and 39 are moved forward.

This statement is false, if 1 is deleted, pairs 12, 51, and 50 need to be moved forward. If a pair is already ahead of the start bucket, it can be moved forward.

2) A is greater than n, b is less than n, and the number moving forward starts from buckets greater than n;

That is, delete 17,51 pairs move forward, attention!! And then 50 is going to move forward

3) Both a and b are less than n, and the position of the starting bucket of the number moving forward is greater than N;

This corresponds to moving forward when deleting 18,51.

## 3.

We need to build a hash table where key is the artist and value is the number of songs by the artist.

| Key   | Kim  | Bob  | Jason | ...  |      |      |      |      |      |
| ----- | ---- | ---- | ----- | ---- | ---- | ---- | ---- | ---- | ---- |
| Value | v1   | v2   | v3    | ...  |      |      |      |      |      |

You also need to maintain a key-value pair to temporarily store the artist with the most songs and the number of songs.

| Artist |      |
| ------ | ---- |
| Number |      |

And then we started going through all the songs. Each time we iterate over a song, we increment the Value of the hash table for that song's artist by 1.
Compare the Value to the maximum number we maintain, and if the Value is greater than the current maximum Value, replace it.

So at the end of the walk, we can get the result by looking at the key-value pair that holds the maximum number of songs.

Time complexity is O(n).

Spatial complexity is O(t).



## 4.

### (1)

Introduce two arrays S and U. The purpose of S is to record the vertices of the shortest path that have been solved (and the corresponding shortest path lengths), while the purpose of U is to record the vertices of the shortest path that have not been solved (and the distance from that vertex to the starting Vertex A).

| Step               | S                                          | U                                    |
| ------------------ | ------------------------------------------ | ------------------------------------ |
| 1. Select vertex A | {A)(0)}                                    | {B(1), C(4), D(∞), E(∞), F(∞), G(∞)} |
| 2. Select vertex B | {A(0), B(1)}                               | {C(3), D(4), E(6), F(∞), G(∞)}       |
| 3. Select vertex C | {A(0), B(1), C(3)}                         | {D(4), E(5), F(7), G(∞)}             |
| 4. Select vertex D | {A(0), B(1), C(3), D(4)}                   | {E(5), F(6),  G(∞)}                  |
| 5. Select vertex E | {A(0), B(1), C(3), D(4), E(5)}             | {F(6), G(9)}                         |
| 6. Select vertex F | {A(0), B(1), C(3), D(4), E(5), F(6)}       | {G(8)}                               |
| 7. Select vertex G | {A(0), B(1), C(3), D(4), E(5), F(6), G(8)} | {}                                   |

So the parentOf and distanceTo arrays are: 

|            | A    | B    | C    | D    | E    | F    | G    |
| ---------- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| parentOf   | -    | A    | B    | B    | D    | D    | F    |
| distanceTo | 0    | 1    | 3    | 4    | 5    | 6    | 8    |

### (2) 

<img src="https://raw.githubusercontent.com/Lingerssss/notePicture/main/image-20220315214549285.png" alt="image-20220315214549285" style="zoom:50%;" />



## 5.

### (1)

1. For each vertex *u* of the graph, mark *u* as unvisited. Let *L* be empty.

2. For each vertex *u* of the graph do Visit(*u*), where Visit(*u*) is the recursive subroutine:

   If *u* is unvisited then:

   1. Mark *u* as visited.
   2. For each out-neighbour *v* of *u*, do Visit(*v*).
   3. Prepend *u* to *L*.

   Otherwise do nothing.

3. For each element *u* of *L* in order, do Assign(*u*,*u*) where Assign(*u*,*root*) is the recursive subroutine:

   If *u* has not been assigned to a component then:

   1. Assign *u* as belonging to the component whose root is *root*.

   2. For each in-neighbour *v* of *u*, do Assign(*v*,*root*).

      Otherwise do nothing.


### (2)

I think that splitting a directed graph into two undirected graphs and executing the algorithm in part1 separately can compute all the strong connected components of a directed graph.











