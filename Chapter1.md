# **深度强化学习导论**

### 摘要

深度强化学习是强化学习(RL)和深度学习的结合。这一领域的研究已经能够解决之前机器学习所不能解决的一系列复杂决策问题。因此，Deep RL在医疗、机器人、智能电网、金融等领域开辟了许多新的应用。本文介绍了深度强化学习模型、算法和技术。特别关注的是与泛化相关的方面以及深度强化学习在实际中的应用。我们假设读者熟悉基本的机器学习概念。

### 第一章:介绍

#### 1.1:动机

机器学习的一个核心主题是序列决策,这是一项决策任务,根据经验决定在不确定的环境中为实现某些目标而采取的一系列行动,序列决策任务涵盖各种的可能应用，可能影响许多领域，如机器人、医疗保健、智能电网、金融、自动驾驶汽车等等.

在行为心理学的启发下(参见sutton 1984),强化学习(RL)提出了一个正式的框架来解决这个问题.其主要思想,与生物智能体类似，人工智能体可以通过与环境的相互作用来学习.利用所收集的经验,人工智能体应该能够优化一些以累积奖励的形式给出的目标.这种方法原则上适用于任何依赖于过去经验的序列决策问题。环境可能是随机的，智能体(agent)可能只观察到当前状态的部分信息，观察可能是高维的(例如，帧和时间序列)，智能体(agent)可能自由地收集环境中的经验，相反地，数据可能遇到受限制情况(例如，不能访问精确的模拟器或有限的数据)。

在过去几年中，强化学习由于成功地解决了具有挑战性的序列决策问题而越来越受欢迎。其中一些成就是因为强化学习与深度学习技术的结合(LeCun et al.， 2015;Schmidhuber,2015;Goodfellow等，2016)。这种组合称为深度强化学习，在高维状态空间的问题中最有用。以前的强化学习方法在功能选择上有一个困难的设计问题(Munos和Moore, 2002;Bellemare等，2013)。然而，由于深度强化学习能够从数据中学习不同层次的抽象，因此它能够在先验知识较低的复杂任务中取得成功。例如，深度强化学习智能体(agent)可以成功地从数千像素的视觉感知输入中学习(Mnih et al.， 2015)。这为模仿人类解决问题的能力提供了可能性，甚至是在高维空间中，这在几年前还是难以想象的

在几部著名游戏作品中《Atari games》利用像素进行输入(Mnih et al,2015),《mastering Go》(Silver et al,2016a)都取得了超人类的水平,在《Poker》中击败了世界顶级职业选手 (Brown and Sandholm, 2017; Moravčik et al., 2017), 深度强化学习还具有实际应用的潜力，如机器人技术（Levine等，2016; Gandhi等，2017; Pinto等，2017），自动驾驶汽车（You et al。，2017），金融 （Deng et al。，2017）和智能电网（François-Lavet，2017），仅举几例。 尽管如此，在应用深度RL算法时出现了一些挑战。 其中，有效地探索环境或能够在稍微不同的背景下总结出良好行为并非易事。 因此，已经为深度强化学习框架提出了大量算法，取决于序列决策任务的各种设置。

#### 1.2大纲:

本文对深度强化学习的介绍旨在指导读者有效地使用和理解核心方法，并提供

进一步阅读的参考资料。读完本介绍后，读者应该能够理解不同的深度强化学习方法和算法，并能够应用它们。读者也应该有足够的背景来进一步研究科学文献和深入的研究。

在**第二章**中，我们介绍了机器学习和深度学习方法。 我们的目标是提供一般的技术背景，并解释深度学习在更广泛的机器学习领域中所处的位置。我们对于有监督和无监督学习的基本要求非常熟悉; 但是，我们简要回顾一下要点。

在**第三章**中，我们提供了一般的强化学习框架以及马尔可夫决策过程（MDP）的案例。 在这种情况下，我们研究了可用于训练深度强化学习智能体(agent)的不同方法。 一方面，学习值函数(第4章)和/或策略的直接表示(第5章)属于所谓的模型自由方法。另一方面，可以利用环境的学习模型的规划算法属于所谓的基于模型的方法(第6章)。

我们在**第七章**中介绍了强化学习中的泛化概念。在基于模型或无模型的方法中，我们讨论了不同元素的重要性：（i）特征选择，（i i）函数近似选择，（i i i）修改目标函数和（iv）分层学习。在**第八章**中，我们介绍了在线设置中使用RL的主要挑战。特别地，我们讨论了开发利用困境和存储器重放的使用

在**第九章**中，我们概述了评估强化学习算法的不同现有基准。此外，我们还提供了一组最佳实践，以确保在不同基准上获得的结果的一致性和重现性

在**第十章**中，我们讨论了比马尔可夫决策过程(MDP)更多的一般设置：（i）部分可观察的马尔可夫决策过程（POMDP），（ii）马尔可夫决策过程(MDP)（而不是给定的MDP）的分布以及转移学习的概念，（iii） 学习没有明确的奖励功能和（iv）多智能体系统。 我们提供了在这些配置中可以使用深度强化学习的描述。

在**第十一章**中，我们对深度强化学习提出了更广泛的观点。这包括对深度强化学习在各个领域的应用的讨论，以及已经取得的成功和仍然存在的挑战。机器人、自动驾驶汽车、智能电网、医疗保健等)。这也包括一个关于深度强化学习和神经科学之间的关系的简短讨论。最后，我们在**第十二章**给出了一个结论，展望了深度强化技术的未来发展，未来应用，以及深度强化学习和人工智能的社会影响
