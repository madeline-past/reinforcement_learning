#### 第七课 temporal-difference learning

这节课算法看着挺多，但都是同一个模板的不同变形。

1.state value

用TD算法计算给定策略的state value
$$
这里v_t(s) 代表t时刻对v_{\pi}(s)的估计值,s_t代表t时刻访问到的数据的state
$$
![72a927181befd6caca2059d5c58349e6](assets/72a927181befd6caca2059d5c58349e6.png)

![60733f7b983c2498afde940f898c368d](assets/60733f7b983c2498afde940f898c368d.png)

bellman equation的数学期望形式
$$
TD算法可以看作用RM求解bellman\ equation，只不过其中v_{\pi}(S\prime)用v_t(s_{t+1})近似表示
$$
![b1ea0861c4b22a6bc3e11dfcae8dd443](assets/b1ea0861c4b22a6bc3e11dfcae8dd443.png)

使用TD算法对系数的约束条件

![4daf6a2cdc2325d09e09b2a5f03d03a1](assets/4daf6a2cdc2325d09e09b2a5f03d03a1.png)

比较

![7fb62fc4baa8e42df1e0c66eef565ec9](assets/7fb62fc4baa8e42df1e0c66eef565ec9.png)

虽然TD的方差小，但TD会有bias

![b78ac9a1a6917d5f50870b8d044f5f50](assets/b78ac9a1a6917d5f50870b8d044f5f50.png)

2.Sarsa(estimate action value)

![844bca2ef86503a1cd2460eb11bc7535](assets/844bca2ef86503a1cd2460eb11bc7535.png)

![d2190516bfe1edb818c995061189b5f1](assets/d2190516bfe1edb818c995061189b5f1.png)

Sarsa+policy improvement寻找最优策略

![2b761a329ea5e87b55ab5995f2641cf3](assets/2b761a329ea5e87b55ab5995f2641cf3.png)

注，若只关心从某一点出发到达目标点的最优路径，此时就可以不需要算出全局所有点的value，每次的episode采样都从出发点开始即可。

3.expected Sarsa

![24fd80ca3b67ff2dca1d5cd905fefabd](assets/24fd80ca3b67ff2dca1d5cd905fefabd.png)

![18d46659111700fc29655c022cd97025](assets/18d46659111700fc29655c022cd97025.png)

4.n-step Sarsa

unify Sarsa and Monte Carlo

![5827ea6653eaa58f4a21ca2ea0bfbff2](assets/5827ea6653eaa58f4a21ca2ea0bfbff2.png)

![101f46c48f16d1ed3b0f7d4503de8a4e](assets/101f46c48f16d1ed3b0f7d4503de8a4e.png)

5.Q-learning(optimal action value)

![01188f3c0cdd8a3f13989d3400cca936](assets/01188f3c0cdd8a3f13989d3400cca936.png)

![066836b4da985c2489fcf825f5f8fc3c](assets/066836b4da985c2489fcf825f5f8fc3c.png)

on/off policy

![2680e708c4fce054b736d7f579d8d280](assets/2680e708c4fce054b736d7f579d8d280.png)

6.conclusion

![abdbf2b6692cc5f649ba73f2f3832ea1](assets/abdbf2b6692cc5f649ba73f2f3832ea1.png)

![983ce4a2786965e44f941a93da91902a](assets/983ce4a2786965e44f941a93da91902a.png)
