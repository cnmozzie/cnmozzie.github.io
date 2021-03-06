---
layout: post
category: wiki
author: Weixuan
title: Quantum Annealing
---

# 量子退火(Quantum Annealing)

下面我们以一个例子讲述如何用量子退火法解决一个旅行者问题。

问题描述：假设现在有若干座城市以及若干条连接这些城市的道路。已知这些道路的长度，求恰好路过所有城市一次并最终回到起点的最短路径。

我们可以通过下述方法将其转化为一个伊辛模型：
将连接城市i和j的道路标记为<i,j>，其长度标记为$$d_{<i,j>}$$。我们用伊辛自旋$$S_{<i,j>}$$向上或向下代表道路<i,j>是否被经过。问题变为寻找一组自旋参量使得哈密顿量

$$H_{TSP}=\sum_{all\ links}d_{<i,j>}\frac{S_{<i,j>+1}}{2}$$

在约束条件$$\sum_{j}\frac{S_{<i,j>}+1}{2}$$以及$$\sum_{j}\frac{S_{<j,i>}+1}{2}$$取得最小值的问题。

## 量子绝热过程(Quantum Adiabatic Evolution)

现在我们知道可以通过含N个伊辛自旋的哈密顿量$$H_0(\{S_i\})$$代表一个优化问题，我们的目标就是找到这个哈密顿量的基态。为了找到这个基态，我们首先构造了一个垂直场哈密顿量$$H_{TF}(\{S_i^x\})=-\sum_iS^x_i$$的基态，然后对其应用如下的随时间变化的哈密顿量：

$$f(t)H_{TF}(\{S_i^x\})+g(t)H_0(\{S_i^z\})$$

其中，f(0)/g(0)$$\gg$$1，f($$\tau$$)/g($$\tau$$)$$\ll$$1。

如果基态间的能隙足够小，哈密顿量的变化足够慢的话。我们的基矢$$\lvert\Psi(t)\rangle$$将从$$H_{TF}$$的基态绝热演化为$$H_0$$的基态。

该论断由下述理论支撑：不相交规则(Non-crossing Rule)以及量子绝热理论。前者给出了随着哈密顿量变化不同本征态能量的变化规律，保证了如果调节的独立参量小于三个，那么基态与第一激发态的能量变化曲线是不会相交的。后者给出了态矢量在哈密顿量作用下的变化规律：只有绝热演化时间$$\tau$$与演化过程中激发态与基态的最小能隙$$\Delta$$的乘积足够大时，态矢量才大概率一直停留在基态。而在很多问题中，这一能隙被证明十分的小，使得量子退火法不能高效地解决所有问题。


### 参考文献

1. Sei Suzuki et al, Quantum Ising Phases and Transitions in Transverse Ising Models, Chapter 8 (DOI: 10.1007/978-3-642-33039-1)