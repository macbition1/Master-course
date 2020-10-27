# Decision Making and Optimize
## 1.Branch and Bound Algorithm base on 0/1 knapsack
* Branch: binary tree(1 and 0),不符合upper bound的进行剪枝，同时缩小边界
* Bound: capacity
> example 1
![](https://i.imgur.com/eIh87nJ.png)


## 2.Beam search algorithm
* 光束搜索
* beam size usually set 2(binary tree) other value (3,4,...) depends on the situation
![](https://i.imgur.com/KrdMzZU.png)

![](https://i.imgur.com/rrthXlA.png)


> Binary search tree
* the value of left node < father node
* the value of right node > father node

![](https://i.imgur.com/pKh07S4.png)


## 3.local search
### 3.1define
It is a approximate algorithm,which is greedy.
```
1.initialize the value x
2.find the neighborhood of x,if there is a value x' better than x, set x = x',loop 2
3.else x is the best 

x = x0;
while( not termination) do
    Generate(N(x)) ;/*generation of candiate neighbors*/
    if there is no better neighbor x' Then stop;
    x = x';
Endwhile
output final solution(local optima)
```

### 3.2 problem
1. how to find the initial solution
2. the number of iterations performed may not be know in advance.
3. 领域大小怎么确定
4. even if local search runs very qucikly,its worst case complexity is exponential.

![](https://i.imgur.com/4PbrrFI.png)

## 4.Meta-Heuristic Algorithms
### 4.1 tabu search 
### 4.2 simulated annealing
### 4.3 genetic algorithm

