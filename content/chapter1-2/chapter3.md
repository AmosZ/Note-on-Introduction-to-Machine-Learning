title:Chapter3:Bayesian Decision Theory
date:2013-11-24

---------------------

# General
-------------------------
**Probability theory** is the framework for making decision under uncertainty

# Bayes in Classification
--------------------------------
In 3.2. This book give us an credibility example. It abserve customer's yearly income and saving,which it believe these attributes give us an idea about credibility. I think this is unreliable. **How to represent or choose the inappropriate variable to describe observe?**

Bayes's rule:

* *prior probability*: $P(C = 1)$It is the knowledge we have as to the value of C *before* looking at the observables $\mathcal{x}$
* *class likelihood*: $p(\mathcal{x}|C)$ is the conditional probalility that an event belonging to C has the associated observation value $\mathcal{x}$. **It is what the data tells us regarding the class**
* *evidence*: $p(\mathcal{x})$ is the **marginal probability** that an abservation x is seen
$$
	p(x) = \sum_{C}p(x,C) = p(x|C = 1)P(C = 1) + p(x|C = 0)P(C = 0)
$$

*poster probability:*
$$
	posterior = \frac{prior*likelihood}{evidence}
$$
