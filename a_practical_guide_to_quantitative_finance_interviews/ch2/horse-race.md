# 2.2.7 Horse race

## 1. 问题描述

1. 25匹马
1. 5个赛道，没有计时器
1. 一次比赛可比较出5匹马的相对快慢
1. 最少要几次比赛找出最快的3匹马？

## 2. 解题思路

1. 给马编号为 1-25
1. 每匹马至少要比一次，所以首先5匹马一组，假设5场比赛结果为（其他情况根据对称性可按同理推导）：

    ```
    1 >  2 >  3 >  4 >  5
    6 >  7 >  8 >  9 > 10
    11 > 12 > 13 > 14 > 15
    16 > 17 > 18 > 19 > 20
    21 > 22 > 23 > 24 > 25
    ```

1. 每组最后两名可直接淘汰，因此剩下的马为：

    ```
    1 >  2 >  3
    6 >  7 >  8
    11 > 12 > 13
    16 > 17 > 18
    21 > 22 > 23
    ```

1. 各组之间肯定要互相比，最好让每组第一名比赛一场（能得到最多信息），假设第6场比赛结果为（其他情况根据对称性可按同理推导）：

    ```
    1 >  6 > 11 > 16 > 21
    ```

1. 最后两名 16 和 21 可直接淘汰，同时慢于 16 和 21 的（17-20，22-25）都可以淘汰，剩下的马为：

    ```
    1 >  2 >  3
      >  6 >  7 >  8
           > 11 > 12 > 13
    ```

1. 从上面的信息，还可以淘汰 8, 12, 13，剩下的马为：  

    ```
    1 >  2 >  3
      >  6 >  7
           > 11
    ```

1. 可知1号最快。再让 2, 3, 6, 7, 11 进行第7场比赛，取前两名即可知最快的3匹马。
1. 以上共进行了7场比赛。
