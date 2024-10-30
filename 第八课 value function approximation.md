#### 第八课 value function approximation

1.objective function

![bd36a3d46334c5ec705797945ce2db52](assets/bd36a3d46334c5ec705797945ce2db52.png)

问题是如何选择S的分布

![80fe31a887cb110af2aa05fedd9f4d9a](assets/80fe31a887cb110af2aa05fedd9f4d9a.png)

![10df5d2bcb9f753cc5749fbcee110a52](assets/10df5d2bcb9f753cc5749fbcee110a52.png)

![cbe1d40dc15a31e57fc77c6e0aa10ebf](assets/cbe1d40dc15a31e57fc77c6e0aa10ebf.png)

2.optimization algorithm

![e08339188561e815aa94fae7ae00e596](assets/e08339188561e815aa94fae7ae00e596.png)

![51a9be804f47869df365d1884e1c8d7d](assets/51a9be804f47869df365d1884e1c8d7d.png)

![9c3cebb781d536cb6650ef7fe2b339ca](assets/9c3cebb781d536cb6650ef7fe2b339ca.png)

value function的两种主要的选择，线性或者神经网络

![ec9a5604e9b3946ba4230b96f6cfd434](assets/ec9a5604e9b3946ba4230b96f6cfd434.png)

线性value function的参数更新策略

注，这里用到了矩阵求导，如果没接触过可以参考李沐深度学习中的[一节课](https://www.bilibili.com/video/BV1eZ4y1w7PY "矩阵求导")

![f00299927d84f90e3f108052c0b4a94d](assets/f00299927d84f90e3f108052c0b4a94d.png)

3.Sarsa+value function approximation

![0aff6cf137ced7dc69471cf940f9ea96](assets/0aff6cf137ced7dc69471cf940f9ea96.png)

4.q-learning+value function approximation(不常用，很底层)

![f5d8bc2405bc7416b1fcef061ed3c0c6](assets/f5d8bc2405bc7416b1fcef061ed3c0c6.png)



***



以上都是求解给定策略的state/action value function，下面我们要讨论直接求解最优策略对应的action value function



5.Deep Q-learning/Deep Q-network(DQN)

![8dd710d93468792d41dfdc7713eec7ed](assets/8dd710d93468792d41dfdc7713eec7ed.png)

![4930a509f4c6bb9f0a52f8def14c7cf0](assets/4930a509f4c6bb9f0a52f8def14c7cf0.png)

![9c14af6667a97159c3845a8b16c5d6ee](assets/9c14af6667a97159c3845a8b16c5d6ee.png)

![d5288d4f755548354e4b8bd17e859276](assets/d5288d4f755548354e4b8bd17e859276.png)

![6762717deb06ac3d09e18479b3831d87](assets/6762717deb06ac3d09e18479b3831d87.png)

![9ad25af3968cd64594307fe435079158](assets/9ad25af3968cd64594307fe435079158.png)

deep q-learning与tabular q-learning比较：

deep q-learning是对一个action value function做优化，而这一个action value function是建立在所有(s,a)状态之上，因此做优化时需要考虑(s,a)如何采样，也就是(s,a)的分布。在这里，我们使用experience replay是假设(s,a)为均匀分布。

tabular q-learning是针对每一个(s,a)求最优解，不需要考虑(s,a)之间的分布关系

![25bbf7895ecaab070c9fe5635d0fdb2e](assets/25bbf7895ecaab070c9fe5635d0fdb2e.png)
