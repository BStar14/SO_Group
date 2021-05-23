# SO Group
It means Special Optimizer group. Shortly we call ourselves SO group.

### Team members
BoSeong Kim

KwangJun Choi

HeeKang Kim

JaeWon Choi

### Mentor
Takashi Imamichi

---

## Delivery Reward Maximization
>__Delivery Reward Maximization (DRM)__ is a optimization problem.
>
>Suppose there are customers who want your goods. But you have limited time.
>
>Customers don't wait forever. Then how can you maximize your profit? __DRM__ will give you an answer.

### Modeling DRM

>Let <img src="https://latex.codecogs.com/svg.latex?\small{V=\{v_1,v_2,\cdots,v_n\}}"/> be the nodes, the customers, and <img src="https://latex.codecogs.com/svg.latex?\small{v_0}"/> be your store.
>
>Each customer has deadline <img src="https://latex.codecogs.com/svg.latex?\small{d(v_i)}"/> and reward <img src="https://latex.codecogs.com/svg.latex?\small{c(v_i)}"/>.
>
>Your vehicle's speed is <img src="https://latex.codecogs.com/svg.latex?\small{s}"/>. Path is denoted as edge. Weights of egdes <img src="https://latex.codecogs.com/svg.latex?\small{w(e_i,e_j)}"/> represent distance.
>
>There is also service time <img src="https://latex.codecogs.com/svg.latex?\small{t(v_i)}"/> that may represent the time needed to pass the goods.
>
>__DRM__ algorithm requires a huge amount of resources as the dimension increases.
>
>In this project, we consider a special case called __LDRM (Line Delivery Reward Maximization)__.


### Modeling LDRM

> We modified __LDRM__ little. Assume that <img src="https://latex.codecogs.com/svg.latex?\small{v_0}"/> is at origin and customers were numbered sequentially.
>
> That is, nodes will like this <img src="https://latex.codecogs.com/svg.latex?\small{v_0,v_1,v_2,\cdots}"/>.
>
>We added varibales <img src="https://latex.codecogs.com/svg.latex?\small{x_{11},x_{22},\cdots}"/> which represent whether the solution ends at <img src="https://latex.codecogs.com/svg.latex?\small{v_i}"/> or not.
>
>Also set variables <img src="https://latex.codecogs.com/svg.latex?\small{x_{ij}}"/>, which implies that airplane stop by <img src="https://latex.codecogs.com/svg.latex?\small{j\mathrm{th}}"/> airport whose final destination is <img src="https://latex.codecogs.com/svg.latex?\small{i}"/>.
>
>We added a constraint
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\limits_{j\:<\:i}x_{ij}-ix_{ii}\leq0}"/>
>
>Note that <img src="https://latex.codecogs.com/svg.latex?\small{x_{ii}}"/> is 1 if and only if the final destination is <img src="https://latex.codecogs.com/svg.latex?\small{i}"/>.
>
>Then there are <img src="https://latex.codecogs.com/svg.latex?\small{i}"/> possible airport that airplane can stop by. So when <img src="https://latex.codecogs.com/svg.latex?\small{x_{ii}=0}"/>, <img src="https://latex.codecogs.com/svg.latex?\small{x_{ij}}"/> is 0 for all <img src="https://latex.codecogs.com/svg.latex?\small{j}"/>.
>
>Otherwise, airplane can choose airport before its destination.

---

## Into a real problem
>Suppose the depot is in Incheon. You may deliver you goods by airplane.
>
>Since your goods require extremly cold environment, there is few airplane that can carry your goods.
>
>In this case, assume that only one airplane is available. Customers are in Shanghai, Hanoi and Suvarnabhmi.
>
>Roughly speaking, they are in a line fortunately. So this problem can be converted into __LDRM__.

---

## Conclusion
>__NP-Complete__ problems are considered unsolvable even if we have a complete fault-tolerent quantum computer.
>
>It is almost impossible to get the exact solution. However in most case, we don't have to find the best answer.
>
>If a properly optimized solution is sufficient, we can get such a solution much faster.
>
>Still, with growing variables, classical algorithms also operate too slowly.
>
>In this case quantum computing can be a solution. Using quantum speedup, one can get optimized solution in reasonable time.

---

## Appendix : DRM is NP-Complete
>Suppose there is no weight and deadline is constant which is a special case of __DRM__. Then the problem is reduced to
>
>Maximize <img src="https://latex.codecogs.com/svg.latex?\small{c(v_i)}"/>
>
>Subject to
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\,t(v_i)\leq\,D"/>
>
>Remember the knapsack problem. The bag has a limited weight and you want to maximize the value.
>
>Maximize <img src="https://latex.codecogs.com/svg.latex?\small{v(x_i)}"/>
>
>Subject to
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\,w(x_i)\leq\,W}"/>
>
>As you can check two are equivalent. Since __knapsack problem__ is __NP-Complete__, so is __DRM__.


## Reference
>[1] Chuanwen Luo, Deying Li, Xingjian Ding, Weili Wu. __*Delivery Route Optimization with automated vehicle in smart urban environment*__. Theoretical Computer Science 836(2020). 42-52.
>
>[2] Edward Farhi, Jeffrey Goldstone, Sam Gutmann. __*A Quantum Approximate Optimization Algorithm*__. arXiv:1411.4028.
