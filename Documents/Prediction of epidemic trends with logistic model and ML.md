---
aliases: []
tags:
  - academic
type: presentation
---
# Prediction of epidemic trends in COVID-19 with logistic model and machine learning techniques


- Wang et al, 2020
---


Knowledge on how a global endemic will peak or diminish is very important.

It can relieve public emotions and help inform public policies and actions.

---


Logistic regression curves can efficiently model time series data.

The parameters to create this logistic curve were calculated by a machine learning model: **FB Prophet**.

---


$$Q(t) = \frac{K}{1+a \times {\rm e}^{b t}}$$
 - $Q(t) =$ number of cases at a time $t$

-  $b=$ incubation rate

-  $K=$ cap value (maximal number of cases for $Q(t)$)

- $a=$ a constant derived from $K$ 
 	- $K/(1+a)=$ number of cases at the very beginning

---


![[Pasted image 20220815161306.png|center|800]]

- <mark style="background: #D2B3FFA6;">Cummulative Cases</mark> 
- <mark style="background: #BBFABBA6;">Cumulative Cures</mark>
- <mark style="background: #ADCCFFA6;">Active Cases</mark> 
- <mark style="background: #134B05DB;">Deaths</mark> 

---


Predicting endemic progressions is a tricky task at best. New variants could arise, entirely new diseases could spread, or public reactions could vary wildly.

---
## References
1. [[@wang.etal_2020]] ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=2&annotation=YYQV5HP4))
