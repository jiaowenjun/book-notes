# 2.3.2 Calendar cubes

## 1. 问题描述

1. 有两个骰子，上面的数字可以用来拼成日期（几号）
1. 日期`1~9`表示成`01~09`
1. 骰子上如何安排数字使其能显示01~31所有的日期？

## 2. 解题思路：

1. 两个骰子一共 6面 + 6面 = 12面
1. 罗列所有日期组合（10, 20, 21, 30, 31 等同于 01, 02, 12, 03, 13）
    - `01, 02, 03, 04, 05, 06, 07, 08, 09`
    - `11, 12, 13, 14, 15, 16, 17, 18, 19`
    - `22, 23, 24, 25, 26 ,27, 28, 29`
1. 看到有11和22，说明两个骰子上都要有数字1和2，剩余：4面+4面 = 8面
1. 剩余需要用到的数字为：0,3,4,5,6,7,8,9，有8个数字
1. 如果0只放到一个骰子上，那另一个骰子上要有1~9才行，这不可能
1. 所以两个骰子上都要有0，那么剩余的面数为：3面 + 3面 = 6面
1. 剩余需要的数字为：3,4,5,6,7,8,9，有7个数字
1. 注意，**数字9可以通过6倒过来表示**
1. 剩余的数字为：3,4,5,6,7,8，有6个数字，正好放到剩余的6个面上
1. 骰子1：0,1,2,3,4,5
1. 骰子2：0,1,2,6,7,8