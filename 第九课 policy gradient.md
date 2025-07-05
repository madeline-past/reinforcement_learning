#### 第九课 policy gradient

直接求解最优策略

通过计算所有state value/immediate reward value之和作为loss来评估策略的好坏，进而梯度上升优化策略。

策略函数可以任选。可直接选取神经网络。注意，在本章中还需要将神经网络对某一state的每个action的输出送入softmax中，最终作为策略函数的输出。这样就会使得策略是stochastic。

![5f80f102462f57ad13f26168c2cec633](assets/5f80f102462f57ad13f26168c2cec633.png)

![1d8c2f8c2336777ba74c1c58efbbc366](assets/1d8c2f8c2336777ba74c1c58efbbc366.png)

![f3bb1e153a06946396648022105d0e51](assets/f3bb1e153a06946396648022105d0e51.png)

![281d0886b70ed8c71bc7723cc0d6f649](assets/281d0886b70ed8c71bc7723cc0d6f649.png)

![1c5130ec77d91635aa9d56517d4c0bfc](assets/1c5130ec77d91635aa9d56517d4c0bfc.png)

![0c324f1e9b072ba52689de325ed92506](assets/0c324f1e9b072ba52689de325ed92506.png)

![4ed2b0716c4c3ff28447a2c4dc076129](assets/4ed2b0716c4c3ff28447a2c4dc076129.png)

![917f8c4ef79084d1fbd5041650901978](assets/917f8c4ef79084d1fbd5041650901978.png)

![e2a9589e0da8f3ecf96142503886b491](assets/e2a9589e0da8f3ecf96142503886b491.png)

![ece18c0c8db8a4c1b6710319139b5ba5](assets/ece18c0c8db8a4c1b6710319139b5ba5.png)

![9fadcb38ce792352db1bc558d96c34d6](assets/9fadcb38ce792352db1bc558d96c34d6.png)

选取策略函数

![c4c968c3a860256596e9b7dca9f504b3](assets/c4c968c3a860256596e9b7dca9f504b3.png)

梯度上升求最优策略

![b6b5a591c31e7b6208515490c0ecf72d](assets/b6b5a591c31e7b6208515490c0ecf72d.png)

![15af286589118c1f93bf169a40bce8a0](assets/15af286589118c1f93bf169a40bce8a0.png)

先估计action value，也即是评估策略，然后再更新策略

这里有个问题：到底按什么样的概率分布采样初始状态s0？ppt里并未说明

其实这里采样s0的概率分布，就对应了前面评估策略时，到底选用的是什么样的状态概率分布

方便理解的话，可以直接想象是等概率挑选所有状态

![6579fa12baf03de1799a8724be231852](assets/6579fa12baf03de1799a8724be231852.png)
