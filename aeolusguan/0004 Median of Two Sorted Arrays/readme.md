## 解题思路
要找中位数，就是要找第 k 大的数(k=L/2+1), 其中 L 就是合并后新数组的长度。当我们舍弃掉一部分，假设舍弃部分的长度为length，那么接下来就是在
剩下的求第 (k-length) 大的数。逐层缩小范围，直到两数组其中一个走完，或者要求的是第1大的元素，就可以直接返回结果了。
## 如何“选择”要舍弃哪部分呢？
既然是要找合并后的数组 C 的第 k 大元素，即 C[k-1], 那如果我们分别 A 和 B 中分别取前 k/2 个元素， 其中必有一部分数组 C 的前 k 个数里。设
mid = k / 2, 当 A[mid-1] < B[mid-1] 时，可以断定 A 的前 mid 个元素是在 C 的前 k 个数里， 那么我们则舍弃 A 的前 mid 个元素。反之则舍弃 B
的前 mid 个元素。
