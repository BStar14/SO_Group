# SO Group
It means Special Optimizer group. Shortly we call ourselves SO group, because it looks like rotation group in physics.

### Team members
Kim BoSeong

Choi KwangJun

Kim HeeKang

Choi JaeWon

### Mentor
Takashi Imamichi


## Delivery Reward Maximization
__Delivery Reward Maximization(DRM)__ is a optimization problem. Suppose there are customers who want your goods. But you have limited time. Customers don't wait forever. Then how can you maximize your profit? __DRM__ will give you an answer.

Before telling what __DRM__ is, define the problem mathematically. Let $V=\{v_1,v_2,\cdots,v_n\}$ be the nodes, the customers, and $v_0$ be your store. Each customer has deadline $d(v_i)$ and reword $c(v_i)$. Your vehicle's speed is $s$. Path is denoted as edge. Weights of egdes $w(e_i,e_j)$ represent distance. There is also service time $t(v_i)$ that may represent the time needed to pass the goods. __DRM__ algorithm is hard. In this project, we consider a special case called __LDRM(Line Delivery Reward Maximization)__.

We modified __LDRM__ little. Assume that $v_0$ is at origin and customers were numbered sequentially, that is, nodes will like this $v_0,v_1,v_2,\cdots$. We added varibales $x_{11},x_{22},\cdots$ which represent whether the solution ends at $v_i$ or not. Also set variables $x_{ij}$, which implies that airplane stop by $j$th airport whose final destination is $i$. We added a constraint that $\sum\limits_{j<i} x_{ij}-ix_{ii}\leq 0$. Note that $x_{ii}$ is 1 if and only if the final destination is $i$. Then there are $i$ possible airport that airplane can stop by. So when $x_{ii}=0$, $x_{ij}$ is 0 for all $j$. Otherwise, airplane can choose airport before its destination.


## Into a real problem
Suppose the depot is in Incheon. You may deliver you goods by airplane. Since your goods require extremly cold environment, there is few airplane that can carry your goods. In this case, assume that only one airplane is available. Customers are in Shanghai, Hanoi and Suvarnabhmi. Roughly speaking, they are in a line fortunately. So this problem can be converted into __LDRM__.


## Conclusion
There are many __NP-HARD__ problems in real world. Any computer, even a supercomputer, can solve these problems. It is impossible to get exact solution. But if we don't have to get the best solution, if we can be satisfied with optimized solution, we can get a solution faster. Still, for large data, some optimization algorithm are slow. In this case quantum computing can be a solution. Using quantum speedup, one can get optimized solution in reasonable time.


## Appendix : DRM is NP-HARD
We will follow the step that the paper shows. Suppose there is no weight and deadline is constant. Then it is a special case of __DRM__. This problem is described as

Maximize $c(v_i)$

Subject to

$\sum t(v_i) \leq D$

Remember knapsack problem. The bag has limited weight and you want to maximize value.

Maximize $v(x_i)$

Subject to

$\sum w(x_i) \leq W$

As you can check two are equivalent. Since __knapsack problem__ is __NP-HARD__ problem, so is __DRM__.


## Reference
[1] Chuanwen Luo, Deying Li, Xingjian Ding, Weili Wu, __*Delivery Route Optimization with automated vehicle in smart urban environment*__, Theoretical Computer Science 836(2020), 42-52

[2] Edward Farhi, Jeffrey Goldstone, Sam Gutmann, __*A Quantum Approximate Optimization Algorithm*__, arXiv:1411.4028
