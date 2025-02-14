# Week-1
内容：排序算法与时间复杂度

插入排序-O(n^2)

合并排序-O(nlogn)

# Week-2
内容：堆

堆是最优队列的一种实现方式

最大(小)堆：每个节点的值都大(小)于或等于其子节点的值，根节点是最大(小)值。

堆是完全二叉树(最底层从左到右依次添加)

n个节点的堆高度为log(n)

### 相关算法：
---
**MIN-HEAPIFY(A, i)**：O(logn)

假设左右子树为最小堆

```
从i节点开始，和左右子节点对比
exchange A[i] with A[smallest]
MIN-HEAPIFY(A, smallest)  //递归
```
---

**Heap-Extract-Min(A)**：O(logn)

弹出根节点，最后一个节点值放到根，然后MIN-HEAPIFY

```
min = A[1]
A[1] = A[A.heap-size]
A.heap-size = A.heap-size -1
MIN-HEAPIFY(A, 1)
```
---
**HEAP-DECREASE-KEY(A, i, key)**: O(logn)

某一节点变化：跟父节点比较，需要则交换，不需要则结束，一直到根

---
**MIN-HEAP-INSERT(A, key)**: O(logn)

在最后添加一个节点，值为无限大，然后调用**HEAP-DECREASE-KEY(A, i, key)**

---
**BUILD-MAX-HEAP(A)**: O(n)

从底部开始构建堆

时间复杂度证明复杂，大概意思是，越高的节点数量越少，但时间消耗越接近O(logn);低的节点数量多但时间消耗接近O(1).

```
A.heap-size = A.length
for i =  [A.length/2] to 1     
  MAX-HEAPIFY(A, i)
```

---
**HEAPSORT(A)**: O(nlogn)

1.建立最大堆

2.根和最后节点交换

3.从堆排除最后一个节点(最大值)

4.**MAX-HEAPIFY(A, 1)**

5.重复直到堆只有一个节点

```
BUILD-MAX-HEAP(A)
for i = A.length to 2  //n次
  exchange A[last] with A[i]
  A.heap-size = A.heap-size - 1
  MAX-HEAPIFY(A, 1)  //Olog(n)
```

# Week-3
内容：哈希表

查询/插入/删除/修改-O(1)

哈希函数: H<sub>_pm_</sub> = {h<sub>_ab_</sub>(x) = ((_a_ x+_b_) mod _p_) mod _m_}

0<a≤p−1

0<b≤p−1

a,b 为随机值，p,m为固定值

碰撞概率：1/m

### 完美哈希

二阶哈希表,要插入n个值

![image](https://github.com/user-attachments/assets/2975a0b0-2181-4c8a-9138-a7cd4c4f4c80)

一阶表:

![image](https://github.com/user-attachments/assets/6a5c1c87-b925-46ee-85d0-a61ba4fbdc21)

二阶表大小: m<sub>i</sub>=n<sub>i</sub><sup>2</sup>

![image](https://github.com/user-attachments/assets/ef1786f7-7923-4712-92a8-dbf4e12f8cda)




