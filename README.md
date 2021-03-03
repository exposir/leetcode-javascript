# 数据结构与算法之美
#算法 #数据结构

- 数据结构： 一组数据的存储结构
- 算法：操作数据的一组方法

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/54163f16e152f71b8f91d3fba652cf48.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/913e0ababe43a2d57267df5c5f0832a7.jpg)

### 10个重要数据结构
- 数组
- 链表
- 栈
- 队列
- 散列表
- 二叉树
- 堆
- 跳表
- 图
- Trie树

### 10个重要算法
- 递归
- 排序
- 二分查找
- 搜索
- 哈希算法
- 贪心算法
- 分治算法
- 回溯算法
- 动态规划
- 字符串匹配算法

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/3723793cc5c810e9d5b06bc95325bf0a.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/b6b71ec46935130dff5c4b62cf273477.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/6ebf42641b5f98f912d36f6bf86f6569.jpg)

### 数组和链表的区别
- 数组支持随机访问，根据下标随机访问的时间复杂度为 O(1)。
- 链表适合插入、删除，时间复杂度 O(1)。

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/d5d5bee4be28326ba3c28373808a62cd.jpg)


- 单链表反转
- 链表中环的检测
- 两个有序的链表合并
- 删除链表倒数第 n 个结点
- 求链表的中间结点


![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/9eca53f9b557b1213c5d94b94e9dce3e.jpg)

### 排序算法
- **冒泡排序**
- **插入排序**
- 选择排序
- 归并排序
- **快速排序**
- 计数排序
- 基数排序
- 桶排序

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/fb8394a588b12ff6695cfd664afb17cd.jpg)
![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/1f6ef7e0a5365d6e9d68f0ccc71755fd.jpg)

##### 插入排序和冒泡排序的时间复杂度相同，都是 O(n2)，在实际的软件开发里，为什么我们更倾向于使用插入排序算法而不是冒泡排序算法呢？
- 冒泡排序需要 3 个赋值操作，而插入排序只需要 1 个

### 分析排序算法 
- 执行效率
- 存消耗
- 稳定性

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/aa03ae570dace416127c9ccf9db8ac05.jpg)

##### 快速排序
```js
    const quickSort = (array) => {
        const sort = (arr, left = 0, right = arr.length - 1) => {
            if (left >= right) {//如果左边的索引大于等于右边的索引说明整理完毕
                return
            }
            let i = left
            let j = right
            const baseVal = arr[j] // 取无序数组最后一个数为基准值
            while (i < j) {//把所有比基准值小的数放在左边大的数放在右边
                while (i < j && arr[i] <= baseVal) { //找到一个比基准值大的数交换
                    i++
                }
                arr[j] = arr[i] // 将较大的值放在右边如果没有比基准值大的数就是将自己赋值给自己（i 等于 j）
                while (j > i && arr[j] >= baseVal) { //找到一个比基准值小的数交换
                    j--
                }
                arr[i] = arr[j] // 将较小的值放在左边如果没有找到比基准值小的数就是将自己赋值给自己（i 等于 j）
            }
            arr[j] = baseVal // 将基准值放至中央位置完成一次循环（这时候 j 等于 i ）
            sort(arr, left, j - 1) // 将左边的无序数组重复上面的操作
            sort(arr, j + 1, right) // 将右边的无序数组重复上面的操作
        }
        const newArr = array.concat() // 为了保证这个函数是纯函数拷贝一次数组
        sort(newArr)
        return newArr
    }
```


## 二分查找
##### 性能 logn
##### 限制
- 必须是数组
- 有序数据
- 数据量太小
- 数据量太大（数组是连续内存）
##### 变体
- 查找第一个值等于给定值的元素
- 查找最后一个值等于给定值的元素
- 查找第一个大于等于给定值的元素
- 查找最后一个小于等于给定值的元素

## 跳表
- Redis 中的有序集合（Sorted Set）就是用跳表来实现的。
- 可以支持快速地插入、删除、查找操作，写起来也不复杂，甚至可以替代红黑树（Red-black tree）。
- 时间复杂度 O(logn)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/492206afe5e2fef9f683c7cff83afa65.jpg)



## 散列表 Hash Table
- 键
- 散列函数
- 散列值
![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/92c89a57e21f49d2f14f4424343a2773.jpg)

##### 散列函数设计的基本要求
- 散列函数计算得到的散列值是一个非负整数
- 如果 key1 = key2，那 hash(key1) == hash(key2)
- 如果 key1 ≠ key2，那 hash(key1) ≠ hash(key2)

##### 解决散列冲突
- 开放寻址法
- 链表法

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/5c31a3127cbc00f0c63409bbe1fbd0d5.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/a4b77d593e4cb76acb2b0689294ec17f.jpg)


##### 工业级散列表特性
- 支持快速查询、插入、删除操作
- 内存占用合理，不能浪费过多内存空间
- 性能稳定，极端情况下，散列表的性能也不会退化到无法接受的情况

##### 如何实现工业级散列表
- 设计一个合适的散列函数
- 定义装载因子阈值，并且设计动态扩容策略
- 选择合适的散列冲突解决方法

## 哈希算法
##### 定义
- 将任意长度的二进制值串映射为固定长度的二进制值串，这个映射的规则就是哈希算法，而通过原始数据映射之后得到的二进制值串就是哈希值。

##### 要求
- 从哈希值不能反向推导出原始数据
- 对输入数据非常敏感，哪怕原始数据只修改了一个 Bit，最后得到的哈希值也大不相同
- 散列冲突的概率要很小，对于不同的原始数据，哈希值相同的概率非常小
- 哈希算法的执行效率要尽量高效，针对较长的文本，也能快速地计算出哈希值

##### 应用
- 安全加密
- 唯一标识
- 数据校验
- 散列函数
- 负载均衡
- 数据分片
- 分布式储存

## 二叉树
##### 定义
- 二叉树，顾名思义，每个节点最多有两个“叉”，也就是两个子节点

##### 完全二叉树
- 完全二叉树要求，除了最后一层，其他层的节点个数都是满的，最后一层的节点都靠左排列。

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/220043e683ea33b9912425ef759556ae.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/4094a733986073fedb6b9d03f877d71e.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/50f89510ad1f7570791dd12f4e9adeb4.jpg)

### 存储二叉树

##### 链式存储法

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/12cd11b2432ed7c4dfc9a2053cb70b8e.jpg)

##### 顺序存储法

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/14eaa820cb89a17a7303e8847a412330.jpg)

### 二叉树遍历

- 前序遍历是指，对于树中的任意节点来说，先打印这个节点，然后再打印它的左子树，最后打印它的右子树。
- 中序遍历是指，对于树中的任意节点来说，先打印它的左子树，然后再打印它本身，最后打印它的右子树。
- 后序遍历是指，对于树中的任意节点来说，先打印它的左子树，然后再打印它的右子树，最后打印这个节点本身。

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/ab103822e75b5b15c615b68560cb2416.jpg)

## 二叉查找树 O(logn)
##### 定义
-  二叉查找树要求，在树中的任意一个节点，其左子树中的每个节点的值，都要小于这个节点的值，而右子树节点的值都大于这个节点的值。

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/f3bb11b6d4a18f95aa19e11f22b99bae.jpg)

##### 操作
- 查找
- 插入
- 删除
- 反转
- 快查找最大节点和最小节点、前驱节点和后继节点
- 中序遍历二叉查找树，可以输出有序的数据序列，时间复杂度是 O(n)，非常高效。

##### 二叉树比散列表的优势
- 散列表中的数据是无序存储的，如果要输出有序的数据，需要先进行排序。而对于二叉查找树来说，我们只需要中序遍历，就可以在 O(n) 的时间复杂度内，输出有序的数据序列。
- 散列表扩容耗时很多，而且当遇到散列冲突时，性能不稳定，尽管二叉查找树的性能不稳定，但是在工程中，我们最常用的平衡二叉查找树的性能非常稳定，时间复杂度稳定在 O(logn)。
- 笼统地来说，尽管散列表的查找等操作的时间复杂度是常量级的，但因为哈希冲突的存在，这个常量不一定比 logn 小，所以实际的查找速度可能不一定比 O(logn) 快。加上哈希函数的耗时，也不一定就比平衡二叉查找树的效率高。
- 散列表的构造比二叉查找树要复杂，需要考虑的东西很多。比如散列函数的设计、冲突解决办法、扩容、缩容等。平衡二叉查找树只需要考虑平衡性这一个问题，而且这个问题的解决方案比较成熟、固定。
- 散列表的构造比二叉查找树要复杂，需要考虑的东西很多。比如散列函数的设计、冲突解决办法、扩容、缩容等。平衡二叉查找树只需要考虑平衡性这一个问题，而且这个问题的解决方案比较成熟、固定。

## 红黑树 
##### 什么是“平衡二叉查找树”？
- 二叉树中任意一个节点的左右子树的高度相差不能大于 1

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/dd9f5a4525f5029a8339c89ad1c8159b.jpg)

##### 定义
- 根节点是黑色的
- 每个叶子节点都是黑色的空节点（NIL），也就是说，叶子节点不存储数据
- 任何相邻的节点都不能同时为红色，也就是说，红色节点是被黑色节点隔开的
- 每个节点，从该节点到达其可达叶子节点的所有路径，都包含相同数目的黑色节点

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/903ee0dcb62bce2f5b47819541f9069a.jpg)

- 红黑树是一种平衡二叉查找树。它是为了解决普通二叉查找树在数据更新的过程中，复杂度退化的问题而产生的。红黑树的高度近似 log2n，所以它是近似平衡，插入、删除、查找操作的时间复杂度都是 O(logn)。
- 因为红黑树是一种性能非常稳定的二叉查找树，所以，在工程中，但凡是用到动态插入、删除、查找数据的场景，都可以用到它。


## 堆
##### 定义
- 堆是一个完全二叉树，可以看成一个优先级队列
- 堆中每一个节点的值都必须大于等于（或小于等于）其子树中每个节点的值
- 对于每个节点的值都大于等于子树中每个节点值的堆，我们叫做“大顶堆”。对于每个节点的值都小于等于子树中每个节点值的堆，我们叫做“小顶堆”。

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/4d349f57947df6590a2dd1364c3b0b1e.jpg)

##### 操作
- 插入
- 删除

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/e3744661e038e4ae570316bc862b2c0e.jpg)

## 堆排序
- 建堆
- 排序

##### 为什么快速排序要比堆排序性能好？
1. 堆排序数据访问的方式没有快速排序友好。
2. 对于同样的数据，在排序过程中，堆排序算法的数据交换次数要多于快速排序。

## 图
##### 广度优先搜索
- 通俗的理解就是，地毯式层层推进，从起始顶点开始，依次往外遍历。广度优先搜索需要借助队列来实现，遍历得到的路径就是，起始顶点到终止顶点的最短路径。
- 深度优先搜索用的是回溯思想，非常适合用递归实现。换种说法，深度优先搜索是借助栈来实现的。在执行效率方面，深度优先和广度优先搜索的时间复杂度都是 O(E)，空间复杂度是 O(V)。


## 字符串匹配
##### BF算法
##### RK算法

## Trie树 （字典树）
##### 本质
- 利用字符串之间的公共前缀，将重复的前缀合并在一起

##### how hi her hello so see 

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/f848a7d8bda3d4f8bb4a7cbfaabab66c.jpg)

![](%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E4%B8%8E%E7%AE%97%E6%B3%95%E4%B9%8B%E7%BE%8E/06b45fde2ca8077465e0c557bc749ab6.jpg)

##### 时间复杂度
- 构建 O(n)
- 查询 O(k)

##### 使用 Trie 树的要求
1. 字符串中包含的字符集不能太大。我们前面讲到，如果字符集太大，那存储空间可能就会浪费很多。即便可以优化，但也要付出牺牲查询、插入效率的代价。
2. 要求字符串的前缀重合比较多，不然空间消耗会变大很多。
3. 如果要用 Trie 树解决问题，那我们就要自己从零开始实现一个 Trie 树，还要保证没有 bug，这个在工程上是将简单问题复杂化，除非必须，一般不建议这样做。
4. 我们知道，通过指针串起来的数据块是不连续的，而 Trie 树中用到了指针，所以，对缓存并不友好，性能上会打个折扣。

## 贪心算法
##### 应用
- 霍夫曼编码
- Prim 和 Kruskal 最小生成树算法
- Dijkstra 单源最短路径算法

## 分治算法
##### 核心思想
- 分而治之 ，也就是将原问题划分成 n 个规模较小，并且结构与原问题相似的子问题，递归地解决这些子问题，然后再合并其结果，就得到原问题的解。


## 回溯算法
##### 核心思想
- 大部分情况下，都是用来解决广义的搜索问题，也就是，从一组可能的解中，选择出一个满足要求的解。回溯算法非常适合用递归来实现，在实现的过程中，剪枝操作是提高回溯效率的一种技巧。利用剪枝，我们并不需要穷举搜索所有的情况，从而提高搜索效率。

## 动态规划
- 大部分动态规划能解决的问题，都可以通过回溯算法来解决，只不过回溯算法解决起来效率比较低，时间复杂度是指数级的。动态规划算法，在执行效率方面，要高很多。尽管执行效率提高了，但是动态规划的空间复杂度也提高了，所以，很多时候，我们会说，动态规划是一种空间换时间的算法思想。

