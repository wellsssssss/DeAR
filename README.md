# [cite_start]DeAR: Fine-Grained VLM Adaptation by Decomposing Attention Head Roles [cite: 1]

[![Conference](https://img.shields.io/badge/CVPR-2026-blue)](https://cvpr.thecvf.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> [cite_start]**DeAR: Fine-Grained VLM Adaptation by Decomposing Attention Head Roles** [cite: 1]
> [cite_start]Yiming Ma*, Hongkun Yang*, Lionel Z. Wang†, Bin Chen†, Weizhi Xian, Jianzhi Teng [cite: 2, 3]
> *Equal contribution. †Corresponding authors.

This repository contains the official PyTorch implementation of **DeAR**, accepted at **CVPR 2026**. [cite_start]DeAR achieves a strong balance between task adaptation and generalization, outperforming previous methods across various tasks by offering a fine-grained controllable fine-tuning process. [cite: 14]

## 📢 News
* **[Upcoming]** We will release the complete training and inference code for DeAR very soon. Please star this repository to stay updated!
* **[Mar 2026]** Our paper has been accepted by **CVPR 2026**! 🎉

## 📖 Abstract
[cite_start]Prompt learning is a dominant paradigm for adapting pre-trained Vision-Language Models (VLMs) to downstream tasks. [cite: 5] [cite_start]However, existing methods often rely on a simplistic, layer-centric view, assuming shallow layers capture general features while deep layers handle task-specific knowledge. [cite: 6] [cite_start]This assumption results in uncontrolled interactions between learnable tokens and original tokens. [cite: 7] [cite_start]Task-specific knowledge could degrade the model's core generalization and creates a trade-off between task adaptation and the preservation of zero-shot generalization. [cite: 8] 

[cite_start]To address this, we challenge the layer-centric view and propose DeAR, a framework that achieves fine-grained VLM adaptation by Decomposing Attention head Roles. [cite: 9] [cite_start]We posit that the functional specialization within VLMs occurs not between layers, but at the finer-grained level of individual attention heads in the deeper layers. [cite: 10] [cite_start]Based on this insight, we introduce a novel metric, Concept Entropy, to systematically classify attention heads into distinct functional roles: Attribute, Generalization, and Mixed. [cite: 11] [cite_start]Guided by these roles, we introduce specialized attribute tokens and a Role-Based Attention Mask mechanism to precisely control information flow, ensuring generalization heads remain isolated from task-specific knowledge. [cite: 12] [cite_start]We further incorporate a Task-Adaptive Fusion Strategy for inference. [cite: 13] [cite_start]Extensive experiments on fifteen datasets show that DeAR achieves a strong balance between task adaptation and generalization, outperforming previous methods across various tasks. [cite: 14]

## 🖼️ Method Overview

### The DeAR Framework
<p align="center">
  <img src="main/DeAR/assets/figure2.png" width="100%">
</p>

[cite_start]*Figure 2. The overall framework of DeAR. [cite: 104] [cite_start]At a deep layer J, we insert learnable attribute tokens into the frozen vision encoder and the text encoder. [cite: 104] [cite_start]Information flow in these subsequent layers is precisely controlled by our Role-Based Attention Mask mechanism. [cite: 105]*

### Traditional vs. Role-Based Masking
<p align="center">
  <img src="main/DeAR/assets/figure1.png" width="80%">
</p>

[cite_start]*Figure 1. For a Generalization Head (e.g., Layer 9 Head 0), our Role-Based Mask explicitly blocking the original CLS and Patch tokens from interacting to the inserted Attribute Tokens. [cite: 29]*

## 🔗 Citation
If you find our work helpful for your research, please consider citing our paper:

```bibtex
@misc{ma2026dearfinegrainedvlmadaptation,
      title={DeAR: Fine-Grained VLM Adaptation by Decomposing Attention Head Roles}, 
      author={Yiming Ma and Hongkun Yang and Lionel Z. Wang and Bin Chen and Weizhi Xian and Jianzhi Teng},
      year={2026},
      eprint={2603.01111},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={[https://arxiv.org/abs/2603.01111](https://arxiv.org/abs/2603.01111)}, 
}
