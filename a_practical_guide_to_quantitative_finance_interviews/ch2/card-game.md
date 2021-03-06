# 2.2.3 纸牌游戏 Card game

## 1. 问题描述

1. 一副牌有52张
1. 每次翻开两张牌
    1. 如果都是黑色，交给发牌员
    1. 如果都是红色，留给自己
    1. 如果是一张红一张黑，丢弃
1. 翻完52张牌后，如果自己的牌比发牌员的牌多，则赢100元，否则什么都不得
1. 问题：开始玩之前，你愿意下注多少钱？

## 2. 解题思路

1. 常规思路：
    1. 题目似乎是问赢的概率有多大。如果赢的概率为 P，则下注少于 100 * P 的钱即可。
    1. 赢的条件：我手上的牌比发牌员的牌多
    1. 输的条件：我手上的牌比发牌员的牌少
    1. 由于红色与黑色有对称性，所以赢的概率应该与输的概率一样大，都是50%
1. 思维陷阱：
    1. 还有一种情况是：双方手上的牌一样多。这种情况将被判定为输
    1. 仔细想会发现，双方手上的牌最终总是一样多的，也就是每盘都输
        1. 初始52张牌，红色跟黑色牌数量相等
        1. 被丢弃的牌总是一红一黑，所以被丢弃的红色与黑色牌数量相等
        1. 所以，剩余在手上的牌，红色与黑色的数量也相等
        1. 自己只有红色，对方只有黑色，所以最终双方的牌数相等
1. 由于每盘都会输，所以不应该下注
