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

注，这里用到了矩阵求导，如果没接触过可以参考李沐深度学习中的

[一节课]: https://www.bilibili.com/video/BV1eZ4y1w7PY

![f00299927d84f90e3f108052c0b4a94d](assets/f00299927d84f90e3f108052c0b4a94d.png)

3.Sarsa+value function approximation

![0aff6cf137ced7dc69471cf940f9ea96](assets/0aff6cf137ced7dc69471cf940f9ea96.png)

4.q-learning+value function approximation(不常用，因为用神经网络作为action value function approximation，更新参数时要计算神经网络梯度)

![f5d8bc2405bc7416b1fcef061ed3c0c6](assets/f5d8bc2405bc7416b1fcef061ed3c0c6.png)

4.Deep Q-learning/Deep Q-network(DQN)

![8dd710d93468792d41dfdc7713eec7ed](assets/8dd710d93468792d41dfdc7713eec7ed.png)

![4930a509f4c6bb9f0a52f8def14c7cf0](assets/4930a509f4c6bb9f0a52f8def14c7cf0.png)

![9c14af6667a97159c3845a8b16c5d6ee](assets/9c14af6667a97159c3845a8b16c5d6ee.png)
