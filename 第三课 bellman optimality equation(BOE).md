#### 第三课 bellman optimality equation(BOE)

bellman optimality equation只是在bellman equation前面加了max pai

![043555bb19c19872f85b79c268481f00](assets/043555bb19c19872f85b79c268481f00.png)

![653dc7030deb322345aa46eecc13abf2](assets/653dc7030deb322345aa46eecc13abf2.png)

等式右侧，对每个给定的v，都能找到使等式右侧取最大值的pai。因此可以将该等式看作v=f(v)形式。

可以用以下迭代算法求解BOE，得到唯一最优解state value，和与之对应的policy

注：该迭代算法被称为值迭代算法value iteration

![80e543a024ab00adc65a81fd63444691](assets/80e543a024ab00adc65a81fd63444691.png)

得到的唯一最优解state value，是所有state value中最大的

![137b331800fe54736821a9dd561f65ea](assets/137b331800fe54736821a9dd561f65ea.png)

最优策略是deterministic greedy policy

![bad054241823fc4f51a3ac9d9c5794ee](assets/bad054241823fc4f51a3ac9d9c5794ee.png)



附录：线性改变reward，并不会影响最优策略

![b2217332bad05b7e89323af4d68f164a](assets/b2217332bad05b7e89323af4d68f164a.png)
