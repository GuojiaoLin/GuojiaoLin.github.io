---
layout: default
title: "GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation"
# css: "paper.css"
---
# GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation 
<br>
**Guojiao Lin<sup>1</sup>, Zhen Meng<sup>1</sup>, Dongjie Wang<sup>2</sup>, Qingqing Long<sup>1</sup>, Yuanchun Zhou<sup>1</sup>, Meng Xiao<sup>1</sup>**
<br>
1. Computer Network Information Center, Chinese Academy of Sciences  <br>
2. The University of Kansas  <br>
![CNIC Logo](/mypaper/GUME/images/cnic.jpg) ![KANSAS Logo](/mypaper/GUME/images/KU.png)
<br>
**CIKM 2024**
---

## Abstract

Multimodal recommendation systems (MMRS) have received considerable attention from the research community due to their ability to jointly utilize information from user behavior and product images and text. Previous research has two main issues. First, many longtail items in recommendation systems have limited interaction data, making it difficult to learn comprehensive and informative representations. However, past MMRS studies have overlooked this issue. Secondly, users’ modality preferences are crucial to their behavior. However, previous research has primarily focused on learning item modality representations, while user modality representations have remained relatively simplistic. To address these challenges, we propose a novel Graphs and User Modalities Enhancement (GUME) for long-tail multimodal recommendation. Specifically, we first enhance the user-item graph using multimodal similarity between items. This improves the connectivity of long-tail items and helps them learn high-quality representations through graph propagation. Then, we construct two types of user modalities: explicit interaction features and extended interest features. By using the user modality enhancement strategy to maximize mutual information between these two features, we improve the generalization ability of user modality representations. Additionally, we design an alignment strategy for modality data to remove noise from both internal and external perspectives. Extensive experiments on four publicly available datasets demonstrate the effectiveness of our approach. The code and data are publicly accessible via GitHub.

## Method

### Enhancing User-Item Graph

We introduce a strategy based on multimodal similarity to identify semantic neighbors. Specifically, this is implemented by utilizing the modality item graph...

![Example Graph](/mypaper/GUME/images/method.png)

### The overview of GUME

We first utilize a graph convolutional network to extract explicit interaction features and extended interest features. Then, we separate and aggregate the attributes of the explicit interaction features to achieve denoising...

---

## Experiments

### Performance Comparison

Our GUME model achieved excellent performance across multiple metrics, surpassing traditional recommendation models and multimodal recommendation models...

![Performance Comparison](/images/performance-comparison.png)

### Visualization Analysis

To further validate the effectiveness of the user modality enhancement component, we visualize the distribution of user modality representations within the Sports dataset...

![Visualization Analysis](/images/visualization-analysis.png)

---

## BibTeX

```bibtex
@article{lin2024gume,
  title={GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation},
  author={Lin, Guojiao and Meng, Zhen and Wang, Dongjie and Long, Qingqing and Zhou, Yuanchun and Xiao, Meng},
  journal={arXiv preprint arXiv:2407.12338},
  year={2024}
}
