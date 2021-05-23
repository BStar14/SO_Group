# SO Group
Special Optimizer group

## Qiskit Hackathon Korea 2021 (Feb.16 - Feb.19)

### Team members
BoSeong Kim

KwangJun Choi

HeeKang Kim

JaeWon Choi

### Mentor
Takashi Imamichi

---

## Delivery Reward Maximization
>__Delivery Reward Maximization (DRM)__ is an optimization problem.
>
>Suppose we should deliver goods to a lot of customers. But you have limited time.
>
>Customers don't wait forever. Then how can you maximize your profit? __DRM__ will give you an answer.

### Modeling DRM

>Let <img src="https://latex.codecogs.com/svg.latex?\small{V=\{v_1,v_2,\cdots,v_n\}}"/> be the nodes, the customers, and <img src="https://latex.codecogs.com/svg.latex?\small{v_0}"/> be your store.
>
>Each customer has a deadline <img src="https://latex.codecogs.com/svg.latex?\small{d(v_i)}"/> and a reward <img src="https://latex.codecogs.com/svg.latex?\small{c(v_i)}"/>.
>
>Your vehicle's speed is <img src="https://latex.codecogs.com/svg.latex?\small{s}"/>. The edges are the path. Weights of edges <img src="https://latex.codecogs.com/svg.latex?\small{w(e_i,e_j)}"/> represent distance.
>
>There is also service time <img src="https://latex.codecogs.com/svg.latex?\small{t(v_i)}"/> that may represent the time needed to pass the goods.
>
>__DRM__ algorithm requires a massive amount of resources as the dimension increases.
>
>In this project, we consider a particular case called __LDRM (Line Delivery Reward Maximization)__.


### Modeling LDRM

> We modified __LDRM__ a little. Assume that <img src="https://latex.codecogs.com/svg.latex?\small{v_0}"/> is at origin and customers were numbered sequentially.
>
> That is, nodes will like this <img src="https://latex.codecogs.com/svg.latex?\small{v_0,v_1,v_2,\cdots}"/>.
>
>We added variables <img src="https://latex.codecogs.com/svg.latex?\small{x_{11},x_{22},\cdots}"/> which represent whether the solution ends at <img src="https://latex.codecogs.com/svg.latex?\small{v_i}"/> or not.
>
>Also, set variables <img src="https://latex.codecogs.com/svg.latex?\small{x_{ij}}"/>, which implies that airplane stop by <img src="https://latex.codecogs.com/svg.latex?\small{j\mathrm{th}}"/> airport whose final destination is <img src="https://latex.codecogs.com/svg.latex?\small{i}"/>.
>
>We added a constraint
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\limits_{j\:<\:i}x_{ij}-ix_{ii}\leq0}"/>
>
>Note that <img src="https://latex.codecogs.com/svg.latex?\small{x_{ii}}"/> is 1 if and only if the final destination is <img src="https://latex.codecogs.com/svg.latex?\small{i}"/>.
>
>Then there are <img src="https://latex.codecogs.com/svg.latex?\small{i}"/> possible airport that airplane can stop by. So when <img src="https://latex.codecogs.com/svg.latex?\small{x_{ii}=0}"/>, <img src="https://latex.codecogs.com/svg.latex?\small{x_{ij}}"/> is 0 for all <img src="https://latex.codecogs.com/svg.latex?\small{j}"/>.
>
>Otherwise, the airplane can choose the airport before its destination.

---

## Into a real problem
>Suppose the depot is in Incheon. You may deliver your goods by airplane.
>
>Since your goods require a freezing environment, only a few airplanes can carry your goods.
>
>In this case, assume that only one airplane is available. Customers are in Shanghai, Hanoi, and Suvarnabhumi.
>
>Roughly speaking, they are in a line, fortunately. So we can convert this problem into __LDRM__.

---

## Conclusion
>__NP-Complete__ problems are considered unsolvable even if we have a complete fault-tolerant quantum computer.
>
>It is almost impossible to get the exact solution. However, in most cases, we don't have to find the best.
>
>If an adequately optimized solution is sufficient, we can get such a solution much faster.
>
>Still, with growing variables, classical algorithms also operate too slowly.
>
>In that case, one can get an optimized solution in a reasonable time with a quantum speedup.

---

## Appendix : DRM is NP-Complete
>Suppose there is no weight and the deadline is constantm which is a special case of __DRM__.
>
>Then the problem is reduced to
>
>Maximize <img src="https://latex.codecogs.com/svg.latex?\small{c(v_i)}"/>
>
>Subject to
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\,t(v_i)\leq\,D"/>
>
>Remember the knapsack problem. The bag has a limited weight, and you want to maximize the value.
>
>Maximize <img src="https://latex.codecogs.com/svg.latex?\small{v(x_i)}"/>
>
>Subject to
>
><img src="https://latex.codecogs.com/svg.latex?\small{\sum\,w(x_i)\leq\,W}"/>
>
>As you can check, two are equivalent. Since the __knapsack problem__ is __NP-Complete__, so is __DRM__.


## Reference
>[1] Chuanwen Luo, Deying Li, Xingjian Ding, Weili Wu. __*Delivery Route Optimization with automated vehicle in smart urban environment*__. Theoretical Computer Science 836(2020). 42-52.
>
>[2] Edward Farhi, Jeffrey Goldstone, Sam Gutmann. __*A Quantum Approximate Optimization Algorithm*__. arXiv:1411.4028.
