---
aliases:
  - Learning to Answer from Correct Demonstrations
authors: Nirmit Joshi, Gene Li, Siddharth Bhandari, Shiva Prasad Kasiviswanathan, Cong Ma, Nathan Srebro
year: 2025
type: paper
tags:
  - academic
page(s): ""
---
> [!abstract]
> We study the problem of learning to generate an answer (or completion) to a question (or prompt), where there could be multiple correct answers, any one of which is acceptable at test time. Learning is based on demonstrations of some correct answer to each training question, as in Supervised Fine Tuning (SFT). We formalize the problem as oﬄine imitation learning in contextual bandits, with demonstrations from some optimal policy, without explicitly observed rewards. Prior work assumes that the demonstrator belongs to a low-complexity policy class, which motivates maximum likelihood estimation (i.e., log-loss minimization). In contrast, we propose relying only on the reward model (specifying which answers are correct) being in a lowcardinality class, which we argue is a weaker assumption. We show that likelihood maximization methods can fail in this case, and instead devise an alternative novel approach that learns with sample complexity logarithmic in the cardinality of the reward class. Our work motivates looking beyond likelihood maximization when learning from correct demonstrations.

# Annotations
(2/10/2026, 2:50:51 PM)

"for simplicity we take the reward to be binary and assume there is always at least one good answer" ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 1](zotero://open-pdf/library/items/KWM5P87B?page=1&annotation=EA3VTP5R))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=1&annotation=EA3VTP5R)) Seems like an arguable assumption

"In most question–answering or prompt-response systems, we argue that the true objective is often reward maximization rather than distribution matching." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 2](zotero://open-pdf/library/items/KWM5P87B?page=2&annotation=UQLYME55))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=2&annotation=UQLYME55)) I wholeheartedly agree. Also a good viewpoint for building any ML system in general

"we propose modeling the rewards instead of the policy class, and relying only on the reward model class having low cardinality (Section 2). That is the function σ∗ : X → 2Y defining correct answers, comes  from a low-cardinality model class σ∗ ∈ S ⊆ (2Y )X and the demonstrator π∗ is supported on σ∗." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 2](zotero://open-pdf/library/items/KWM5P87B?page=2&annotation=DTHR8A37))

"Definition 1 (Learning from Correct Demonstrations). We say that the reward model class S is learnable from correct demonstrations by a learning rule A : (X × Y)∗ → (∆(Y))X with sample complexity mS,A(ǫ, δ), if for any ε, δ ∈ (0, 1), and any sample size m ≥ mS,A(ε, δ), for any D, and σ∗ ∈ S, and any π∗ ∈ Πσ∗ , we have  PS∼(D×π∗)m [LD,σ∗ (A(S)) ≤ ε] ≥ 1 − δ ." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 4](zotero://open-pdf/library/items/KWM5P87B?page=4&annotation=DQDFIIJ2))

"Given a policy class Π ⊆ (∆(Y))X , the (conditional) Maximum Likelihood Estimator (MLE) (or the log-loss minimizer) is defined as  MLEΠ(S) = arg max  π∈Π  ∏m  i=1  π(yi | xi) = arg min  π∈Π  (  −  ∑ m  i=1  log π(yi | xi)  )  . (MLE)" ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 4](zotero://open-pdf/library/items/KWM5P87B?page=4&annotation=SCNJPVPW))

"The loss LD,σ∗(̂πmle) can then be bounded in terms of  this squared Hellinger distance. However, this guarantee is only meaningful when log |Π| is small. Note that if MLE succeeds thanks to Proposition 1 and the cardinality |Π| being small, we would not only have low loss, but ̂πmle would also match the distribution of π∗." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 5](zotero://open-pdf/library/items/KWM5P87B?page=5&annotation=3CQTCBWX))

"Let us think of how ̂πmle ∈ MLEΠS (S) would behave. For any x observed in the training set, any distribution over correct answers is allowed, and only correct answers are observed, so ̂πmle(· | x) will match the empirical distribution πS(·|x) of observed yi’s for xi = x. However, on unseen contexts x, it may choose any distribution over actions y ∈ σ(x) for some σ that is consistent with the data, i.e., in:  consS (S) = {σ ∈ S | ∀(x,y)∈S y ∈ σ(x)} ." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 5](zotero://open-pdf/library/items/KWM5P87B?page=5&annotation=PD4I883R))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=5&annotation=PD4I883R)) I believe the intuition here is that for the few seen contexts/examples of x, MLE would learn to imitate the demonstrator's behavior. However, for the unseen contexts/examples, the MLE can only try to learn to be consistent with the dataset without much guidance, making this a very difficult problem

"Consider S = {σ0, σ01}, where σ0(x) = {0} and σ01(x) = {0, 1} for all x. If the true hypothesis is σ∗ = σ0, then all observed labels are 0. However, σ01 also remains consistent, and thus MLEΠS (S) may output 1 at test time—failing to generalize and go beyond memorization." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 5](zotero://open-pdf/library/items/KWM5P87B?page=5&annotation=D6NQPB2D))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=5&annotation=D6NQPB2D)) Previous point

"We might instead consider using Maximum Likelihood Estimation, but over a smaller policy class whose size matches that of S. A natural choice for such a policy class is:  Πunif,S := {πunif,σ : σ ∈ S} where πunif,σ(· | x) = Unif(σ(x)),  where for simplicity we consider σ(x) to be finite here. The advantage is that we now have |Πunif,S | = |S|. However, this policy class is misspecified in that the actual demonstrator π∗ need not be uniform on all correct answers and so Πunif,S might not contain π∗." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 6](zotero://open-pdf/library/items/KWM5P87B?page=6&annotation=HBJYFPAN))

"We begin with a simple rule that does ensure learning, but with high (super) linear sample complexity. We then amend it to obtain the desired logarithmic sample complexity." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 6](zotero://open-pdf/library/items/KWM5P87B?page=6&annotation=M4ID923P))

![[Attachments/💤Zotero/joshiLearningAnswerCorrect2025/joshiLearningAnswerCorrect2025-8-x65-y452.png]]([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=8&annotation=L2N9VEF2)) Essentially, I think we are pushing apart wildly differing hypotheses. If a hypothesis was correct in the given round, yet disagreed with the majority, it is weighted much higher, so that its variability won't be hidden in the masses, and can help eliminate uncertainty faster

"As with ̂πMaj, we zero out the weights of σ that are not consistent with the demonstration yt, and thus completely remove them from consideration (at least with β = 0, which we use in the realizable setting). The difference is that in addition, we also increase the weights of σ under which the predicted action ̂yt is incorrect (i.e., ̂yt ∈/ σ(xt), and so σ’s vote did not help elect ̂yt)." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 8](zotero://open-pdf/library/items/KWM5P87B?page=8&annotation=H2KX7XM6))

"We do so despite the fact that we do not know whether ̂yt is correct or not." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 8](zotero://open-pdf/library/items/KWM5P87B?page=8&annotation=A5P7QSER))

"Now, on any mistake–meaning ̂yt 6∈ σ∗(xt)–the weight of σ∗ is doubled. If the algorithm made M mistake on a realizable sequence for some σ∗ ∈ S at the end some t number of rounds, then it must be that  w(t+1)(σ∗) = 2M ≤ Wt+1 ≤ W1 = |S| , which implies M ≤ log2 |S| ." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 9](zotero://open-pdf/library/items/KWM5P87B?page=9&annotation=8A9STGBX))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=9&annotation=8A9STGBX)) Very weird proof, but kind of makes sense

"Output a randomized predictor as follows:  ̂πo2b(· | x) = Unif (̂π1(x), . . . , ̂πt(x)) := 1  m  m ∑  t=1  ̂πt(· | x) ." ([Joshilearninganswercorrect2025](zotero://select/library/items/2XCXWWTX)) ([pdf, p. 9](zotero://open-pdf/library/items/KWM5P87B?page=9&annotation=SEE96UEM))([Joshilearninganswercorrect2025](zotero://open-pdf/library/items/KWM5P87B?page=9&annotation=SEE96UEM)) I'm not sure if I'm understanding this correctly, but aren't we essentially doing the Online algorithm, but with each sample i one by one as t? And if this is the case, is obtaining policies for each step t and just combining them to a uniform setting truly a desired behavior? Shouldn't the algorithm have gotten "better" in later steps?

## References
1. [joshiLearningAnswerCorrect2025](zotero://select/library/items/2XCXWWTX)
