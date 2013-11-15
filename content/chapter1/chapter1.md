title:Chapter 1 & Chapter 2
date:2013-11-11

# Introduction & Supervised Learning
(Because chapter 1 is only a brief of introduction to the various domain in which machine learning is applied. We combine this chapter with Chapter 2).

##1. Definition lists
- #### Vapnik-Chervonenkis (VC) Dismension ($P67$)

:   The maximum number of points that can be shattered by
$\mathcal{H}$, is denoted as $VC(\mathcal{H})$, and 
measures the capacity of $\mathcal{H}$.

- #### Probably Approximately Correct (PAC) Learning ($P69$)

:   In *Probably Approximately Correct (PAC) learning*, given a class, $\mathcal{C}$, and examples drawn from some unknown but fixed probability distribution, $\mathcal{p(x)}$, we want to find the number of examples, $N$, such that with probability at least $1 - \delta$, the hypothesis $h$ has error at most $\epsilon$, for arbitrary $\delta \le 1/2$ and $\epsilon > 0$
> $P\\{\mathcal{C} \Delta h \le \epsilon \\} \ge 1 - \delta$

:   where $\mathcal{C} \Delta h$ is the region of difference between $\mathcal{C}$ and hypothesis $h$.

:   Why I think PAC is important? I think the PAC gives a us way to quantify the value of proximity between the underlying distribution and our hypothesis under a number of samples.

##2. Problems
- #### 1. What kind of learning algorithm (Supervised/Unsupervised/Reinforement) do you think is most suitable for pattern formation (e-Mouse is used) task in our lab.? If we change the task to navigation issue?
A:

- #### 2: On page $P69$ of Chapter 2, the author gives an example about how to calculate the number of samples needed to satisfy the miss value $\delta$. The author uses upper bound $\epsilon / 4$ to measure the error, note in here $\epsilon / 4$ is the upper bound for one strip. Then the actually error, noted as $\alpha$, then $\alpha \le \epsilon$. Why not calculated by $(1 - \alpha)^N$ instead of $(1 - \epsilon / 4)^N$?
A: 
