title:Chapter1-2
date:2013-11-11

-----------------

# Chapter1 : Introduction
**Machine learning** consist of two parts:

* learn from  experience(history data)
* adapt to environments

In past, I usually confuse **Machine Learning** and **Data Mining**. *Data Mining* is an application of machine learning methods to large databases. But machine learning is also a part of artificial intelligence. Something is called to be "Intelligent" means it has the abiliy to **learn and adapter to changes**.

I don't think machine learning is just the execution of a computer program to optimize the parameters of a model. It should also tell us how to select or create the model. **Learning** should not merely optimize the parameters of an known formular(model,hypothesis).

## Problem: 
### 1. What kind of learning algorithm (Supervised/Unsupervised/Reinforement) do you think is most suitable for pattern formation (e-Mouse is used) task in our lab.? If we change the task to navigation issue?
A:I think we should understand what is supervised/unsupervised/reinforemen learning formally at first.(To be added).
Reinforement is the best choice I think. We don't have any history data to make prediction and the emouse won't get together automatically in the form of letter A. Instead, each emouse should take a sequence steps to form a pattern. It is what reinforement learning does. 

------------------

# Chapter2: Supervised Learning
## 2.1 An example: Label family car automatically.
> **Training Data**: a set of examples cars.Each of them has a label.

**Input Representation:** Here,we separate a family car from other cars are the **price** and **engine power**. But do we have some general method or idea to represent input? It is very important to know which attributes(or dimension) of data play main role in machine learning.

Some symbols:

* $\mathcal{H}$: *hypothesis class*. It is a model with parameters unknow.
* $h$: hypothesis. $h \in \mathcal{H}$. It is a model with known parameters.
* $X$: tranning set.
* **Empirical error** : the proportion of training instances where predictions of $h$ do not match the required values $r$ given in $X$
$$
	E(h|\mathcal{X}) = \sum_{t=1}^{N}(h(x_t) \neq r_t)
$$

We know that there maybe infinite $h \in \mathcal{H}$ whose empirical error is zero(or maybe none, see below). How to select the best one? --The hypothesis with max **margin**

So here is our general steps:

1. find the *most specific hypothesis* S that is the **tightest boundary** that include all the positive example and none of the negative example.
2. find the *most general hypothesis* G that is the **largest boundary** that include all the positive example and none of the negative example. (Do we have some more mathematical definition of specific hypothesis and general hypothesis??)
3. find a way to compute **margin**
4. choose the hypothesis $h$ from  hypothesis class $\mathcal{H}$ with **max margin**

We will know that **SVM(support vector machine)** will produce a hypossis with largest margin. What is the relationship between them? 

In the end of this example. It tell us that we assume there exist $h \in \mathcal{H}$ with $E(h|\mathcal{X})$ is 0.But how we can always choose a hypothesis $\mathcal{X}$ that include this $h$? Just as mentioned above, machine learning should tell us how to create/select/produce a hypothsis class(model with unknown parameters), not merely optimize parameter with a known model.

## 2.2 Vapnik-Chervonenkis(VC) Dimension.
> **Shatter** : A classification model $f$ with some parameter vector $\vec{\theta}$ is said to "shatter" a set of data point , if, for all assignments of labels to thoses points, there exists a $\theta$ such that model $f$ make no error when evaluating that set of data points.

> $\mathcal{H}$ : is the hypothesis class.

The maximum number of pointers that can be **shattered** by $\mathcal{H}$(there exist $h \in \mathcal{H}$ can separate $\mathcal{C}$ perfectly(with no empirical error)) is called the *Vapnik-Chervonenkis(VC) dimension* of $\mathcal{H}$, is denoted as$VC(\mathcal{H})$ and measure the *capacity of $\mathcal{H}$*

**Why Vapnik-Chervonenkis(VC) dimension is useful????**

Reference on Vapnik-Chervonenkis(VC) dimension: 

* <http://en.wikipedia.org/wiki/Vapnik%E2%80%93Chervonenkis_theory>
* <http://en.wikipedia.org/wiki/VC_dimension>

## 2.3 Probably Approximately Correct (PAC) Learning
**Probably Approximately Correct (PAC) Learning** provide us a method to caculate how many examples(training data) do we need if we use **tightest hypothesis**. 

The confidence probability $1-\delta$ is the factor of our certainty on the conculsion : error probability at most $\epsilon$

> In *Probably Approximately Correct (PAC) learning*, given a class, $\mathcal{C}$, and examples drawn from some unknown but fixed probability distribution, $\mathcal{p(x)}$, we want to find the number of examples, $N$, such that with probability at least $1 - \delta$, the hypothesis $h$ has error at most $\epsilon$, for arbitrary $\delta \le 1/2$ and $\epsilon > 0$

> $$P\\{\mathcal{C} \Delta h \le \epsilon \\} \ge 1 - \delta$$

> where $\mathcal{C} \Delta h$ is the region of difference between $\mathcal{C}$ and hypothesis $h$.

**Derivation Process:**

The follow inequation are same :
$$
	P\\{\mathcal{C} \Delta h \le \epsilon \\} > 1 - \delta \Leftrightarrow  1 - P\\{\mathcal{C} \Delta h \le \epsilon \\} < \delta
$$

and
 
$$
	P\\{\mathcal{C} \Delta h \le \epsilon \\} = 1 - 4(1 - \frac{\epsilon}{4})^N$
$$

* 
