---
aliases: Prediction of epidemic trends in COVID-19 with logistic model and machine learning technics
authors: Peipei Wang, Xinqi Zheng, Jiayang Li, Bangren Zhu
year: 2020
type: paper
tags:
  - academic
  - annotation
page(s): 110058–110058
---
> [!abstract]
> Abstract COVID-19 has now had a huge impact in the world, and more than 8 million people in more than 100 countries are infected. To contain its spread, a number of countries published control measures. However, itâs not known when the epidemic will end in global and various countries. Predicting the trend of COVID-19 is an extremely important challenge. We integrate the most updated COVID-19 epidemiological data before June 16, 2020 into the Logistic model to fit the cap of epidemic trend, and then feed the cap value into Fbprophet model, a machine learning based time series prediction model to derive the epidemic curve and predict the trend of the epidemic. Three significant points are summarized from our modeling results for global, Brazil, Russia, India, Peru and Indonesia. Under mathematical estimation, the global outbreak will peak in late October, with an estimated 14.12 million people infected cumulatively.

# Annotations  
(8/15/2022, 3:16:40 PM)

“How the global epidemic will peak or diminish is the most concerned problem worldwide. Therefore, it is of striking significance to predict the pandemic trends of infection worldwide.” ([Wang et al., 2020, p. 1](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=2&annotation=YYQV5HP4))

“Logistic is often used in regression fitting of time series data due to its simple principle and efficient calculation.” ([Wang et al., 2020, p. 1](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=2&annotation=5AICL9HK))

“When the sample size of machine learning model is small, the model is easy to overfit, and the model performs well in the historical data set. Therefore, the prediction effect is not good enough in real scene.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=C2ITICYN))

([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) When dealing with small sample sizes of time series data, Long Short-Term Memory (LSTM) models are effective.

“However, SARS and COVID19 are different in many ways, such as incubation rate, incubation period and the development degree of the world at the time of the outbreak, so the simulation may be not reliable.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=W9RUISS3))

([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) Various diseases have various differences as well. Incubation rate, incubation period, and development degree, all factors used to predict the development of a given disease.

“If we want to use Prophet with Logistic growth for long-term prediction, a cap value must be specified. Therefore, we integrate the most updated COVID-19 epidemiological data before June 16, into the Logistic model to fit the cap of epidemic trend, and then feed the cap value into FbProphet model, a time series prediction model to derive the epidemic curve and predict the long term of epidemic.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=WHXLP6WN))

“Forecasts about when the pandemic will reach the turning point and global maximum number of infections may be of great usefulness for public decision-makers and humans, as it could relieve people’s emotions and give policy-makers the time to respond to the changes that the outbreak has brought.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=HWCTRSJ3))

“As an improvement on the Malthus population model \[16\], in 1838, Pierre François Verhulst published the logistic equation: 
$$\frac{d Q}{d t} = rQ(1 - \frac{Q}{K} )$$
where Q, r and K indicate the population size, intrinsic growth rate and maximum population size that the environment could carry, respectively. $\frac{dQ}{dt}$ represents the growth of the population. $r$ and $K$ are constants number and the value of $Q$ derives with time to produce an S-shaped curve in this Logistic equation.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=2DFEDITJ))

“Logistic Growth is characterized by increasing growth in the beginning period, but a decreasing growth at a later stage, as you get closer to a maximum.” ([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=3&annotation=R8IMECPG))

([Wang et al., 2020, p. 2](zotero://select/library/items/JNZKDPVP)) Even though SARS and COVID-19 are completely separate and different diseases, both of their cumulative case charts follow an S curve. This indicates that they could be modeled by a Logistic Growth curve.

“At the beginning of the outbreak, people did not take strict measures, and the initial number of people infected is small, so the number of infections slowly increased. When the infection base reached a certain proportion, the epidemic situation showed an explosive exponential growth trend, and then with the government’s regulation and public’s cooperation, the epidemic situation gradually slowed down the spread speed, finally reached the maximal number of cumulative infected people.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=MTMNIVPN))

“The key point is the time at which the cumulative situation curve turns, i.e., when rapid increases in the number of cases are replaced by slow increases.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=7SNRZFL5))

“As long as the data include this key point and the time interval shortly thereafter, the curve fitting and prediction of the future number of cases will be fairly accurate.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=G9Q9A2XJ))

“In Prophet, the prediction model consists of superpositions $y(t ) = g(t ) + s(t ) + h(t ) + t$ , where $g(t)$ is a trend function used to analyze the non-periodic changes of time series. $s(t)$ a periodic term, reflecting the periodic change, such as the periodicity of a week or a year. $h(t)$ is the influence of an occasional day or days, such as a holiday. t is an error term, on behalf of the failed to consider the effect of the error of the model. Here in our research, we only consider about the non-periodic changes of time series.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=LT5TYGF6))

\[image\] ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=UGIKSD39))  
([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP))

([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) Growth is characterized as follows:  
$$Q(t)=\frac{K}{1+a \times {\rm e}^{b t}}$$
where $Q(t)$ is the number of cases at time $t$, $a$ is constant, and $b$ could be considered as the incubation rate and $K$ is the cap value (the maximal number of cases for $Q(t)$.

“Therefore, the number of cases at the very beginning is $\frac{K}{(1 + a)}$, and the key point is $\frac{\ln a}{b}$ at which the cumulative situation curve turns, when rapid increases in the number of cases are replaced by slow increases.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=UL8ZE3C5))

“Hereafter, we could model the growth of COVID-19 with Logistic formula and learn the parameters $a$, $b$ and $K$.” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=ISWB2ZBK))

“The key point tfast and the accumulated cases Q(tfast) at that time can be written as follow: 
$$t_{fast} = \frac{\ln(a)}{b}$$
$$Q (t_{fast}) = \frac{K}{2}$$
” ([Wang et al., 2020, p. 3](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=4&annotation=QD749UAR))

“Epidemic peak point This peak means that the active infections has reach the top value and since then, the numberof active cases will decrease. The fastest growth point After this point, the epidemic gradually slows down and finally becomes stabled. Turn point This point occurred when the number of cumulative cured exceeds the number of active confirmedcases, marks an early victory in the control of the epidemic.” ([Wang et al., 2020, p. 4](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=5&annotation=QKCANZYR))

“Then the estimated top number of infections Qtop can be calculated as follows: 
$$Q_{top} = \frac{K} {1 + a \times \exp(−bt_{max})}$$
” ([Wang et al., 2020, p. 4](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=5&annotation=G8BG55A7))

“Three time series are constructed from our collected data, namely confirmed cases, recovered cases and death cases series.” ([Wang et al., 2020, p. 4](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=5&annotation=ZYZC36W9))

“Obviously, the number of active confirmed cases is equal to the number of accumulated confirmed cases minus the number of recovered and deaths.” ([Wang et al., 2020, p. 4](zotero://select/library/items/JNZKDPVP)) ([pdf](zotero://open-pdf/library/items/WUPG4LJE?page=5&annotation=SY35E9PJ))

## References
1. [wang.etal_2020](zotero://select/items/@wang.etal_2020)
