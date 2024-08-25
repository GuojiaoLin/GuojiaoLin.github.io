---
layout: default
title: "GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation"
css: "paper.css"
---
<div class="paper-page">

# GUME: Graphs and User Modalities Enhancement for Long-Tail Multimodal Recommendation

**Guojiao Lin<sup>1</sup>, Zhen Meng<sup>1</sup>, Dongjie Wang<sup>2</sup>, Qingqing Long<sup>1</sup>, Yuanchun Zhou<sup>1</sup>, Meng Xiao<sup>1</sup>**

1. Computer Network Information Center, Chinese Academy of Sciences  
2. The University of Kansas  

![CNIC Logo](/images/cnic-logo.png) ![KANSAS Logo](/images/kansas-logo.png)

**CIKM 2024**

---

## Abstract

Multimodal recommendation systems (MMRS) have received considerable attention from the research community due to their ability to jointly utilize information from user behavior and product images and text. Previous research has two main issues. First, many long-tail items in recommendation systems have limited interaction data, making it difficult to learn comprehensive and informative representations. However, past MMRS studies have overlooked this issue. Secondly, users’ modality preferences are crucial to their behavior. However, previous research has primarily focused on learning item modality representations, while user modality representations have remained relatively simplistic. To address these challenges, we propose a novel Graphs and User Modalities Enhancement (GUME) for long-tail multimodal recommendation...

<!-- 内容缩写，更多内容省略... -->

## Method

### Enhancing User-Item Graph

We introduce a strategy based on multimodal similarity to identify semantic neighbors. Specifically, this is implemented by utilizing the modality item graph...

![Example Graph](/images/example-graph.png)

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

</div>