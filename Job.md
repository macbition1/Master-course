# Job
## 1.Java
### 1.1 Thread safe
* base on multiple thread on sharing data
* A class is thread-safe if it behaves correctly when accessed from multiple threads![](https://i.imgur.com/497v39A.png)

![](https://i.imgur.com/BoWCUPL.png)

> how to solve. thread safe problem?

lock 
* 保证共享资源在同一时间只能由一个线程进行操作 (原子性，有序性)。
* 将线程操作的结果及时刷新，保证其他线程可以立即获取到修改后的最新数据（可见性）
