# AI decision-making can be ethical, but is that enough?

<small>Maddy Guthridge --- April 18th, 2025</small>

As artificial intelligence has developed, it has wormed its way into almost every aspect of our lives, from social feed algorithms that keep us scrolling to large language models such as ChatGPT. While moral concerns surround all of these applications of AI, none are quite as pressing as those that surround the use of automated decision-making systems (ADMS). Many people are understandably uneasy about the prospect of these systems deciding on issues as important as the granting of loans, the detection of plagiarism, and even the sentencing of criminals. Given that the "AI revolution" is showing no signs of slowing, it is imperative that we develop methods to ensure that automated decisions are fair, accountable and transparent. This essay discusses various interpretations of these requirements, as well as exploring approaches to implement them, before finally questioning whether any of this even matters.

To understand the concern surrounding ADMS, it is important to grasp the current gap in fairness, accountability and transparency seen in these systems. ([Sebastian Sequoiah-Grayson, no date](#unsatisfiable)) identifies how these attributes are established in human decisions through the providence of an explanation, before discussing how the inability to garner an explanation from ADMS prevents the triad from being realised. Essentially, this article argues that given a valid explanation, an automated decision can be shown to be fair, accountable and transparent. Sequoiah-Grayson considers this through the causal model of explanation, in which an explanation of an event is composed of a set of causes, where if any cause is removed, the event will no-longer transpire. Under this model, an explanation for an automated decision must list each cause, with each cause being counterfactual.

Applying this to the example discussed in ([Asghari et al., 2022](#what-to-explain)), where an ADMS decided not to grant a loan to an applicant, the causes were claimed to be the applicants gender, residential location, and native language, with the applicant’s credit rating and income not contributing. This example seems ludicrous when analysed using the causal model of explanation, but the report makes sense of it by differentiating between “local and global explanations”, where global explanations describe how the system behaves in general and local explanations document how the system made a particular decision. Its authors argue that both of these explanations are required to gain a full understanding of a decision. For example, if we imagine that the loaning ADMS considered the credit rating and income, but relied on the other inputs as “deciding factors” if the primary inputs weren’t conclusive, the outcome of the decision would make much more sense, as the global explanation contextualises the local explanation. (note that this is a hypothetical example, and doesn’t reflect how the system actually worked).

Another model of explanation is explored by ([Besold and Uckelman, 2018](#what-why-how)), which argues for an epistemic model, where an explanation is a reason that “is relevant to the purpose of the question”, and allows the hearer “to act in a more informed way”, but isn’t necessarily entirely true. This is because in this model, explanations serve to fulfil an epistemic need in the listener. It seems counter-intuitive that the authors argue an explanation need not be entirely true, but their example makes the reasoning much clearer. They ask us to consider Newtonian mechanics, which explain the motion of objects, before reminding us that these laws break down at relativistic speeds. Newtonian mechanics, despite not being entirely true, may be all that is needed to explain a phenomenon. The allowance for simplification in this model of explanation makes it very appealing when considering accountability, fairness and transparency in ADMS. Some examples of strategies that allow ADMS to meet this criteria are activation atlases, which allow for visualisation of complex neural networks used for image classification; and explainer algorithms, which distil a complex system to a simpler system. When analysed using a causal model of explanation, these strategies cannot provide an explanation as the causes they suggest cannot be proven to reflect the real system, but under an epistemic model, they can be considered accurate enough to satisfy a user’s question in a sufficiently truthful manner.

While the epistemic model of explanation allows us to explain “black-box” systems such as neural networks, an alternative may be found in explainable AI, which also satisfies the causal model. The authors of the paper ([Madalina Busuioc, 2020](#accountable)) advocate for the use of interpretable algorithms, where rather than building a system optimised entirely for accuracy, the quality and simplicity of explanations is also valued. To explore this perspective, consider COMPAS, the notoriously-biased ADMS used to predict recidivism. A study in Science Advances ([Julia Dressel and Hany Farid, 2017](#recidivism)) compares the accuracy of COMPAS to a simple logistic regression model, finding that it produced predictions as accurate as COMPAS, with similar rates for both type 1 and 2 errors.

However, in my opinion, all of these arguments miss the forest for the trees. As noted in ([Madalina Busuioc, 2020](#transparency-fallacy)), almost all highly-important decisions are actually made by humans who are given the output of an ADMS as an input to their decision, with the paper suggesting that more research must be conducted on how ADMS outputs influence human decisions in phenomena such as automation bias. The paper suggests that ADMS may be used by humans as a “moral buffer”, allowing people to avoid accountability for decisions that are ultimately up to them, which effectively creates a transparency fallacy ([Madalina Busuioc, 2020](#transparency-fallacy)). A Harvard University study ([Ben Green and Yiling Chen, 2019](#disparate)) found that humans applied the recommendations of ADMS selectively, resulting in decisions with significantly greater bias compared to the outputs of the ADMS they were informed by, suggesting that even if an ADMS is fair, accountable and transparent, the final decision may not be so after human review.

In conclusion, by considering the problem of fairness, accountability and transparency from the perspective of an epistemic model of explanation, we are able to identify several strategies that act as valid explanations. Even better solutions are found in the field of explainable AI, where interpretable algorithms make valid explanations much easier to provide. However, ensuring that ADMS are fair, accountable and transparent does not ensure that human intervention will maintain these attributes. While it is important to ensure that automated decisions maintain this triad of qualities, especially as AI takes an increasingly-active role in decision-making, we must also enforce these standards on people.

## References

### {#what-to-explain}

Asghari, H. *et al.* (2022) *What to explain when explaining is difficult?*. Available at: <https://doi.org/10.5281/zenodo.6375784>

### {#disparate}

Ben Green and Yiling Chen (2019) “Disparate Interactions: An Algorithm-in-the-Loop Analysis of Fairness in Risk Assessments”. Available at: <https://doi.org/10.1145/3287560.3287563>

### {#what-why-how}

Besold, T. and Uckelman, S. (2018) “The What, the Why, and the How of Artificial Explanations in Automated Decision-Making”. Available at: <https://doi.org/10.48550/arXiv.1808.07074>

### {#transparency-fallacy}

Bettina Berendt (2022) *The AI Act Proposal: Towards the next transparency fallacy? Why AI regulation should be based on principles based on how algorithmic discrimination works.*. Available at: <https://doi.org/10.1628/978-3-16-161299-2>

### {#recidivism}

Julia Dressel and Hany Farid (2017) “The accuracy, fairness, and limits of predicting recidivism.” Amer- ican Association for the Advancement of Science. Available at: https://doi.org/10.1126/sciadv.aao5580

### {#accountable}

Madalina Busuioc (2020) “Accountable Artificial Intelligence: Holding Algorithms to Account.” Public Administration Review, pp. 825–836. Available at: https://doi.org/10.1111/puar.13293

### {#unsatisfiable}

Sebastian Sequoiah-Grayson (unpublished manuscript, in correspondance) “The Unsatisfiable Triad: A Problem for Automated Decision Making”

## Additional notes

I originally wrote this essay as a part of [UNSW's COMP4920 "Professional Issues and Ethics in Information Technology" course](https://handbook.unsw.edu.au/undergraduate/courses/2024/comp4920) in late 2024. Because of this, Sebastian Sequoiah-Grayson's referenced paper “The Unsatisfiable Triad” unfortunately cannot be linked to, owing to it being unpublished.

