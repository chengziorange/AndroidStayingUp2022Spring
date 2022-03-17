# 启发式搜索

**启发式搜索**（Heuristic Search）是一种改进的搜索算法。它在普通搜索算法的基础上引入了**启发式函数** $G \left (  X \right )$，该函数的作用是基于已有的信息对搜索的每一个分支选择都做估价，进而选择分支。**简单来说，启发式搜索就是对每一步行动的取和不取都做分析，从中选取更优解或删去无效解。**

请阅读下面 C 语言代码，在本 Markdown 文件中补足启发式搜索中的启发式函数 $G \left (  X \right )$ 或为其添加启发式函数 $G \left (  X \right )$，从而优化原有的搜索算法的搜索效率。如果你对算法模式在 C 语言下的表示还不甚熟悉，你可以使用 **伪代码** 或者 **自然语言** 来进行描述。

完成这道题目，你需要掌握搜索算法（尤其是深入优先搜索算法）相关的知识。



## 最小距离

有 $m$ 行 $n$ 列的方格挨在一起，第 $x$ 行第 $y$ 列的格子记作 $(x,y)$。

在不超过边界的情况下你可以向上、下、左、右四个方向移动，离开 $(x,y)$ 的代价为 `DistanceValue[x][y] ` (整型，且 `DistanceValue[x][y]` >= 1)。

求 $(1,1)$ 点到 $(m,n)$ 点的最少代价。


```c++
void dfs(int Distance, int &MinDistance, int x, int y)
{
    if (x > m || y > n || x < 1 || y < 1)
        return ;
    if (G(X))
        return ;
    if (x == m && y == n)
    {
        MinDistance = min(MinDistance, Distance);
        return ;
    }
    dfs(Distance + DistanceValue[x][y], MinDistance, x + 1, y) ;
    dfs(Distance + DistanceValue[x][y], MinDistance, x, y + 1) ;
    dfs(Distance + DistanceValue[x][y], MinDistance, x - 1, y) ;
    dfs(Distance + DistanceValue[x][y], MinDistance, x, y - 1) ;
}
dfs(0,inf,1,1);
```



## 拆分小球

把 $N$ 个完全相同的小球分成 $K$ 份，求有多少种分法。

注: 将 $4$ 个小球分成 $3$ 份，`1 1 2` 和 `2 1 1` 属于同一种分法。

```C++
void dfs(int LastNumber, int SumNumber, int Residual)
{
    if (Residual == 0)
    {
        if (SumNumber == N)
            Answer++;//全局变量，记录分法
        return;
    }
    for (int i = LastNumber; G(X); i++) 
        dfs(i, SumNumber + i, Residual - 1);
}
dfs(1,0,K);
```



## 01 反转

给定 $3*3$ 的 01 矩阵

```
0 1 1
1 0 0
1 0 1
```

定义一个操作：将一个点及其相邻的上、下、左、右四个点的数字反转，求得到下列状态的最少操作数。

```
1 1 1
1 1 1
1 1 1
```

```C++
int Change[9] = {0b1011, 0b10111, 0b100110, 0b1011001, 0b10111010, 0b100110100, 0b11001000, 0b111010000, 0b110100000};
void find(int Status, int Steps)
{
    if (G(X))
        return;
    if (Status == FinalStatus)
    {
        Answer = Steps;
        return;
    }
    for (int i = 0; i < 9; i++)
        find(Status ^ Change[i], Steps + 1);
}
find(0b101001110, 0);
```

