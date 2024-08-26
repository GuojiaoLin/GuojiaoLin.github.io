---
layout: default
title: "GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation"
---
**[Guojiao Lin<sup>1</sup>](https://guojiaolin.github.io/), Zhen Meng<sup>1</sup>, [Dongjie Wang<sup>2</sup>](https://wangdongjie100.github.io/), [Qingqing Long<sup>1</sup>](https://scholar.google.com.hk/citations?user=283USTgAAAAJ&hl=zh-CN&oi=sra), [Yuanchun Zhou<sup>1</sup>](https://scholar.google.com.hk/citations?user=r7_Yfj8AAAAJ&hl=zh-CN&oi=sra), [Meng Xiao<sup>1</sup>](https://coco11563.github.io/)**
<br>

<table>
  <tr>
    <td><img src="/mypaper/GUME/images/cnic.jpg" alt="CNIC Logo" width="150"></td>
    <td><sup>1</sup>Computer Network Information Center, Chinese Academy of Sciences</td>
    <td><img src="/mypaper/GUME/images/KU.png" alt="KANSAS Logo" width="150"></td>
    <td><sup>2</sup>The University of Kansas</td>
  </tr>
</table>
<br>

<center>**CIKM 2024**</center>

<a href="https://arxiv.org/abs/2407.12338" target="_blank" style="text-decoration:none;">
  <button style="background-color: #333; color: white; border-radius: 20px; padding: 10px 20px; margin-right: 10px;">
    <img src="/file/PDF.png" alt="Paper" style="width: 16px; vertical-align: middle; margin-right: 8px;">
    Paper
  </button>
</a>
<a href="https://github.com/NanGongNingYi/GUME" target="_blank" style="text-decoration:none;">
  <button style="background-color: #333; color: white; border-radius: 20px; padding: 10px 20px;">
    <img src="file/code.png" alt="Code" style="width: 16px; vertical-align: middle; margin-right: 8px;">
    Code
  </button>
</a>

## Abstract
<p style="word-break: break-all; hyphens: auto;">
Multimodal recommendation systems (MMRS) have received considerable attention from the research community due to their ability to jointly utilize information from user behavior and product images and text. Previous research has two main issues. First, many longtail items in recommendation systems have limited interaction data, making it difficult to learn comprehensive and informative representations. However, past MMRS studies have overlooked this issue. Secondly, users’ modality preferences are crucial to their behavior. However, previous research has primarily focused on learning item modality representations, while user modality representations have remained relatively simplistic. To address these challenges, we propose a novel Graphs and User Modalities Enhancement (GUME) for long-tail multimodal recommendation. Specifically, we first enhance the user-item graph using multimodal similarity between items. This improves the connectivity of long-tail items and helps them learn high-quality representations through graph propagation. Then, we construct two types of user modalities: explicit interaction features and extended interest features. By using the user modality enhancement strategy to maximize mutual information between these two features, we improve the generalization ability of user modality representations. Additionally, we design an alignment strategy for modality data to remove noise from both internal and external perspectives. Extensive experiments on four publicly available datasets demonstrate the effectiveness of our approach. The code and data are publicly accessible via [GitHub](https://github.com/NanGongNingYi/GUME).
</p>

## Limitations of Multimodal Recommendation
<p style="word-break: break-all; hyphens: auto;">
Previous research does not address the use of multimodal information to improve the connectivity of tail items in the useritem interaction graph. Due to the sparse interaction data, the tail items receive insufficient information during the graph propagation phase, hindering their ability to develop comprehensive and informative representations.
</p>

<br>

<p style="word-break: break-all; hyphens: auto;">
Although item modality information is rich, user modality representation still has much to explore. Previous research either focuses solely on learning user ID representations while neglecting user modality representations, or it represents user modality features merely by aggregating the modality features of items the user has interacted with. Alternatively, it customizes user modality embeddings, combines them with item modality embeddings, and updates them through GCN propagation. However, using simple aggregation or customized methods to represent user modalities cannot effectively capture user modality preferences. The simple aggregation method limits user modality preferences to past behavior, while customized methods ignore past preferences and can add noise during propagation.
</p>

![Limitations](/mypaper/GUME/images/limitation.png)

## Method

### Enhancing User-Item Graph
<p style="word-break: break-all; hyphens: auto;">
We introduce a strategy based on multimodal similarity to identify semantic neighbors. Specifically, this is implemented by utilizing the modality item graph. This graph keeps only the top-k neighbors with the highest similarity scores for each item, and we use it to identify items that are similar to the target item across multiple modalities (textual and visual). We then define these items as the semantic neighbors of the target item.
</p>

### The overview of GUME
<p style="word-break: break-all; hyphens: auto;">
We first utilize a graph convolutional network to extract explicit interaction features and extended interest features. Then, we separate and aggregate the attributes of the explicit interaction features to achieve denoising. We maximize the mutual information between explicit interaction features and extended interest features. Finally, we align information within internal modalities as well as between modalities and external behaviors.
</p>

![Method](/mypaper/GUME/images/method.png)

### The main contributions
<ul style="word-break: break-all; hyphens: auto;">
<li> We propose a strategy to enhance user-item graphs based on multimodal similarity, improving the connectivity of tail items.
<li> We develop a user modality enhancement strategy that improves the generalization ability of user modality representations, enabling them to effectively adapt to new products or changes in user behavior, even without direct interaction data.
<li> We design an alignment strategy from internal and external perspectives to capture commonalities within modalities as well as between modalities and external behaviors, thereby achieving a denoising effect.
<li> We conduct comprehensive experiments on four public Amazon datasets to demonstrate the unique advantages of our GUME.
</ul>

## Experiments

### Performance Comparison
<p style="word-break: break-all; hyphens: auto;">
Our GUME model achieved excellent performance across multiple metrics, surpassing traditional recommendation models and multimodal recommendation models. Specifically, in terms of Recall@20 for Sports, Clothing, and Electronics, GUME outperforms the best baseline by 2.28%, 3.54%, and 3.82% respectively; while in terms of NDCG@20, it shows improvements of 3.13%, 5.67%, and 2.65%. On the Baby dataset, GUME ties with the best baseline in Recall@20 and improves by 2.22% over the best baseline in NDCG@20. The results validate the effectiveness of our GUME.
</p>

![Performance Comparison](/mypaper/GUME/images/performance.png)

### Ablation Study
<p style="word-break: break-all; hyphens: auto;">
In our work, GUME comprises the modules Graph Enhancement, Alignment for Capturing Commonalities and User Modality Augment. To thoroughly examine the impact of these modules, we conduct comprehensive ablation studies. We use "w/o XX" to denote the absence of a specific module, meaning "without XX".
</p>

![Ablation Study](/mypaper/GUME/images/ablation.png)

### Comparisons on Tail Items Performance
<p style="word-break: break-all; hyphens: auto;">
To validate whether enhancing the user-item graph based on multimodal similarity can improve the recommendation performance for tail items, we conducted experiments on the Clothing dataset. Specifically, we divided items into five equally sized groups according to the node degree in the user-item bipartite graph, as shown in Figure 2. In recommendation systems, 20% of items account for 80% of interactions. Therefore, we define the top 1/5 of items as head items, while the remaining 4/5 are defined as tail items. The larger the x-axis value, the lower the node degree, and the less popular the item. We compared the performance of GUME, w/o GE, and MENTOR.
</p>
<br>
<p style="word-break: break-all; hyphens: auto;">
The results show that graph enhancement can improve the recommendation performance for tail items. Although removing graph enhancement can improve the recommendation performance for head items, the overall performance decreases due to the decline in tail item performance, which is consistent with the findings of GALORE. Additionally, GUME outperforms MENTOR for both head and tail items, indicating that our graph enhancement strategy effectively improves recommendation performance for long-tail distribution data.
</p>

![Comparisons](/mypaper/GUME/images/long_tail.png)

### Visualization Analysis
<p style="word-break: break-all; hyphens: auto;">
To further validate the effectiveness of the user modality enhancement component, we visualize the distribution of user modality representations within the Sports dataset. We compare two models, w/o UM and GUME, as mentioned in ablation study. Specifically, we randomly select 1000 user instances from the Sports dataset and employ t-SNE to map the user modality representations to two-dimensional space.
</p>
<br>
<p style="word-break: break-all; hyphens: auto;">
The results, illustrated in figure 3, show that the user modality distribution of GUME is more uniform, while the distribution of w/o UM is more dispersed. Previous research has demonstrated that the uniformity of representation significantly influences recommendation performance. This explains why GUME is effective in enhancing user modality representation.
</p>

![Visualization Analysis](/mypaper/GUME/images/distribution.png)


## BibTeX

```bibtex
@article{lin2024gume,
  title={GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation},
  author={Lin, Guojiao and Meng, Zhen and Wang, Dongjie and Long, Qingqing and Zhou, Yuanchun and Xiao, Meng},
  journal={arXiv preprint arXiv:2407.12338},
  year={2024}
}