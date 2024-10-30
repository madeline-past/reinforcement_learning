#### 第十课 actor critic

![0d130daaec70f9c28a2532e51f5d5ce9](assets/0d130daaec70f9c28a2532e51f5d5ce9.png)

1.the simplest actor critic algorithm(QAC)

critic:sarsa+value function approximation

actor:policy update algorithm

![6fa9ef21ab4b234bdaa6994931982a39](assets/6fa9ef21ab4b234bdaa6994931982a39.png)

2.advantage actor critic(A2C)

基本思想是引入baseline减小方差

先来个引理

![8f26c484a2f1457c4a73a19e7e9736d5](assets/8f26c484a2f1457c4a73a19e7e9736d5.png)

![e8e4ed9e4a71cc35ff3e334c86aae40c](assets/e8e4ed9e4a71cc35ff3e334c86aae40c.png)

引入baseline不会改变X的期望，但是会改变方差

![7d96ab839e41654a8ef3657e0a3d8ba8](assets/7d96ab839e41654a8ef3657e0a3d8ba8.png)

这样，我们就可以通过修改baseline来减小X的方差

![5e49ec82384f01eb08f9ea96d467f4da](assets/5e49ec82384f01eb08f9ea96d467f4da.png)

![68731b64787fb86a84988998545f3caf](assets/68731b64787fb86a84988998545f3caf.png)

![66dcacdf4fa6df64be3bcf7cd0fbe3a6](assets/66dcacdf4fa6df64be3bcf7cd0fbe3a6.png)

![126639418c79da3138e958188eac743a](assets/126639418c79da3138e958188eac743a.png)

3.importance sampling

之前介绍的两种算法都是on policy，也就是基于待优化策略生成数据，评估策略，进而改进策略。这种方法的缺点在于不能使用其他策略事先生成好的数据。而importance sampling就可以将on policy改进为off policy

![5a8e31fc8101a0dd2c898fd1fddb077b](assets/5a8e31fc8101a0dd2c898fd1fddb077b.png)

![b4a5847efabd36e18f1990ab2db3dce9](assets/b4a5847efabd36e18f1990ab2db3dce9.png)

4.off policy actor critic

我们将基于beta策略下生成的数据，使用off policy的actor critic算法，算出最优策略

既然是基于beta策略下生成的数据，那么我们的loss函数中，原先基于不断更新的策略下的(s,a)的分布也就变为服从beta策略下(s,a)的分布

值得注意的是，这里loss函数对state value求和时取的分布是在beta策略上的分布

![7428c90cc522da041c0ce0228c7a94fa](assets/7428c90cc522da041c0ce0228c7a94fa.png)

![d1c0f7801943c3f8c298e67a7aa57f2e](assets/d1c0f7801943c3f8c298e67a7aa57f2e.png)

![982acd483ff4ec91596f3bf7b3d2854b](assets/982acd483ff4ec91596f3bf7b3d2854b.png)
