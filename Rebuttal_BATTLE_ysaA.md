Dear Reviewer,

Thank you very much for your constructive comments and suggestions on our manuscript titled "BATTLE: Unsupervised Bi-Level Optimization with Implicit Relationship Mining for Attributed Graph Anomaly Detection" with Submission ID 732. We have carefully considered each point and have made significant revisions to address your concerns. Below, we provide a detailed response to your questions.

Thank you for your question regarding the key concerns. The reason we did not include the F1 score comparison is mainly due to the limitation on the length of the paper; however, we do have the relevant data.

Below is our related data Table:

| Methods         | BlogCatalog F1@50 | BlogCatalog F1@100 | Flickr F1@50 | Flickr F1@100 | Pubmed F1@50 | Pubmed F1@100 |
| --------------- | ----------------- | ------------------ | ------------ | ------------- | ------------ | ------------- |
| Radar(2017)     | 0.183             | 0.345              | 0.141        | 0.246         | 0.086        | 0.143         |
| ANOMALOUS(2018) | 0.179             | 0.336              | 0.155        | 0.260         | 0.094        | 0.159         |
| DOMINANT(2020)  | 0.221             | 0.357              | 0.151        | 0.264         | 0.107        | 0.179         |
| DeepAE(2020)    | 0.192             | 0.336              | 0.141        | 0.260         | 0.098        | 0.170         |
| Deep2NAD(2021)  | 0.133             | 0.302              | 0.151        | 0.270         | 0.098        | 0.170         |
| HCM(2022)       | 0.224             | 0.367              | 0.163        | 0.278         | 0.107        | 0.180         |
| ANEMONE(2021)   | 0.225             | 0.367              | 0.160        | 0.272         | 0.102        | 0.172         |
| CoLA(2022)      | 0.192             | 0.317              | 0.130        | 0.227         | 0.113        | 0.184         |
| Sub-CR(2022)    | 0.238             | 0.375              | 0.167        | 0.278         | 0.116        | 0.191         |
| LCUnpool(2023)  | 0.233             | 0.375              | 0.163        | 0.283         | 0.114        | 0.186         |
| BATTLE(ours)    | **0.246**         | **0.382**          | **0.168**    | **0.284**     | **0.120**    | **0.197**     |

**Question 1 Respond:**

We greatly appreciate your inquiry regarding the scalability of our BATTLE framework to large-scale graphs. It is a valid point, and we acknowledge the importance of assessing the performance of our framework on large graphs with high-dimensional attributes.

First and foremost, we would like to emphasize that, conceptually, there is no inherent distinction between large graphs and the smaller ones we have included in our current dataset. The primary variance lies in the magnitude of computational resources required to process them.While we have indeed contemplated conducting validations on larger graphs, our current computational resources are unfortunately limited, which has restricted our ability to perform such extensive experiments at this stage.

Nevertheless, based on the structural similarities between large and small graphs, we are confident that the BATTLE framework, which has demonstrated robust performance on smaller graphs, should exhibit similar efficacy when scaled up, provided that sufficient computational resources are available.

We are actively seeking to expand our computational capabilities to address this limitation and are committed to validating the scalability of our framework in future work. We believe that with the appropriate resources, the BATTLE framework will prove to be equally effective on larger graphs, maintaining its performance integrity.

**Question 2 Respond:** 

Thank you for your constructive feedback. We understand the importance of using real-world examples to validate the effectiveness of our BATTLE framework. While the anomalies in the public datasets we used are indeed artificially introduced, and previous studies have relied on these datasets for validation, we chose to continue using them to ensure the validity and fairness of our experiments.

Your suggestion is very helpful, and we agree that real-world examples would provide a stronger validation of our framework. However, due to the current lack of publicly available real-world datasets related to our field of study, we have been limited in this regard and have not been able to conduct such validations. We will definitely consider this point in our future work and aim to incorporate more real-world examples for further validation when they become available or when we are able to access them.

**Question 3 Respond:**

Thanks for your question. The primary contribution of BATTLE lies in incorporating implicit relationship into anomaly detection. Regarding the complexity of BATTLE, which comes mainly from the attention network learner, sparsification, graph convolutional network layer, contrastive loss, and implicit relationship prediction. We calculated the complexity of BATTLE as 

$$
O\left(nd(L_1 + b_1) + md_1L + nd_2^1L + nd_2^2L + m^2 + (2 + R)n^2\right)
$$

where \( n(m) \) is the number of nodes(edges), \( b_1 \) is the batch size of attention network. \( d/d_1/d_2 \) are the dimension of node attribute/representation/projection, \( L_1/L \) is the layer number of attention network and GCN, and \( R \) is the number of graph samples. Compared to ANEMONE (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 6n^2\right)
$$

), CoLA (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 4n^2 + c^2nR\right)
$$

), and Sub-CR (with complexity 

$$
O\left(md_1L + nd_2^1L + nd_2^2L + 5n^2 + n^2R\right)
$$

), our method does not have significantly higher complexity (all four methods are in \( O(n^2) \) order of magnitude), yet we achieve notable performance improvement. We will present the computational details of model complexity in the final version. Additionally, we conducted experiments comparing BATTLE with other baselines regarding computational efficiency. As shown in Table 1, the experimental results demonstrate that BATTLE does not significantly increase training time compared to several other methods. However, we achieve notable performance improvement.

**Table 1:** Training time for different methods

| Methods       | BlogCatalog | Flickr    |
| ------------- | ----------- | --------- |
| ANEMONE(2021) | 10.07 min   | 22.40 min |
| CoLA(2022)    | 9.35 min    | 20.60 min |
| Sub-CR(2022)  | 10.90 min   | 23.62 min |
| BATTLE(Ours)  | 11.71 min   | 25.04 min |

**Question 4 Respond:**

Thank you very much for your question. We are seriously considering incorporating significance tests into our analysis. However, due to time constraints, we may not be able to complete the relevant experiments within this rebuttal round. We will do our utmost to present the results to you in the next rebuttal round. In the meantime, you may refer to the initial comparison of F1 scores that I presented above.

We believe that these revisions have significantly improved the quality and clarity of our paper. We are confident that BATTLE provides a valuable contribution to the field and is worthy of presentation at WWW25.

Thank you once again for your thorough review and for giving us the opportunity to improve our work. We look forward to the possibility of presenting our research at WWW25.