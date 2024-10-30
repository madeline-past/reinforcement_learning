# 西湖大学赵世钰老师的【强化学习的数学原理】课程简略课堂笔记

本仓库存放本人第二遍学习赵世钰老师强化学习课程的记录与心得。

赵世钰老师【强化学习的数学原理】课程视频：https://www.bilibili.com/video/BV1sd4y167NS

第一次更新日期：2024.10.29

二更：感觉RL实际应用下来，最难的还是设计reward。等我明天看一篇基于RL解决vln的论文再研究一下。

更新完毕日期：2024.10.30

两天快速复习完了强化学习，接下来准备直接看篇CMA论文(Reinforced Cross-Modal Matching and Self-Supervised Imitation Learning  for Vision-Language Navigation)直接实战





***

分隔线

***

简单总结下这门课介绍的方法：

model-base：对环境完全掌握，例如：给定s，a，知道下个状态的概率分布；给定s，a，知道获得reward的概率分布。此时可直接套用bellman equation评估策略，或者套用bellman optimality equation直接求出最优策略。

接下来所有算法全部都是model-free

**Monte Carlo**：根据数据集episode，由公式
$$
q_{\pi}=r_t+r_{t+1}+r_{t+2}+r_{t+3}+...
$$
估算action value，然后根据action value更新greedy policy，再多次迭代求得最优解

**temporal-difference learning**：根据TD公式模板更新state/action value，多次迭代，最终求得给定策略下的state/action value，也就是策略评估。唯一例外的Q-learning，多次迭代后可直接求得optimal action value。

接下来要对各种离散的形式推广到连续空间

**value function approximation**：将离散state/action value的值用state/action function表示，用梯度下降更新参数。可以和temporal-difference learning结合进行策略评估。另外，Deep Q-learning可以直接求得optimal action value。

**policy gradient**：将离散policy的值用function表示，其中梯度上升时需要用到真实action value，可以用估计值近似，有Monte Carlo和TD两种估计方法。使用policy gradient可直接求得最优策略，但却是on policy。

**actor critic**：在policy gradient中用TD估计action value，就得到了最简单的actor critic。可以引入baseline减小更新policy时梯度上升的梯度方差。使用importance sampling可将on policy改进为off policy。推广到无限的动作空间，就可以得到deterministic actor critic。

总结：环环相扣的方法介绍，从离散一步一步推广到连续。值得反复学习。
