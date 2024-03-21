---
layout: model-composition
---

## Abstract

Recent developments in Multimodal Large Language Models (MLLMs) have shown rapid progress, moving towards the goal of creating versatile MLLMs that understand inputs from various modalities. However, existing methods typically rely on joint training with paired multimodal instruction data, which is resource-intensive and challenging to extend to new modalities. In this paper, we propose a new paradigm through the model composition
of existing MLLMs to create a new model that retains the modal understanding capabilities of each original model. Our basic implementation, **NaiveMC**, demonstrates the effectiveness of this paradigm by reusing modality encoders and merging LLM parameters. Furthermore, we introduce **DAMC** to address parameter interference and  mismatch issues during the merging process, thereby enhancing the model performance. To facilitate research in this area, we propose **MCUB**, a benchmark for assessing ability of MLLMs to understand inputs from diverse modalities. Experiments on this benchmark and four other multimodal understanding tasks show significant improvements over baselines, proving that model composition can create a versatile model capable of processing inputs from multiple modalities.

## Methodology

   <div style="text-align:center;">
      <img src="/assets/static/fig-3.png" width="80%">
   </div>

   <div style="text-align:center;margin-bottom: 2rem">
      <font size=3> Figure 1: Illustration of the model composition processes with only image and audio modalities are considered for simplicity. (a) and (b) show a basic model composition framework, while (c) and (d) demonstrate model composition with parameter decoupling</font>
      <br>
   </div>

### A Model Composition Framework

In our composition framework, we retain all modal-specific components (and their weights) from different MLLMs to handle respective modal inputs, and connect them to the same LLM. In cases where the LLMs have not been adapted during the training of MLLMs (as illustrated in the Figure 1(a)), we employ the pre-trained  weights of the LLM directly. Conversely, if the LLMs have undergone adaptation in the MLLM training process (Figure 1(b)), we simply average their weights. We name this composition framework NaiveMC and provide a formal procedure of it in Algorithm 1.

   <div style="text-align:center;">
      <img src="assets/static/fig-2.png" width="30%">
   </div>

### Parameter Decoupling

### Adaptive Parameter Adjustment

### Multimodal Commonality Understanding Benchmark

## Contact

This project is co-led by [Chi Chen](https://carboncoo.github.io), [Yiyang Du](https://adu2021.github.io), and is advised by [Peng Li](https://www.lpeng.net/) (lipeng@air.tsinghua.edu.cn) and [Yang Liu](https://nlp.csai.tsinghua.edu.cn/~ly) (liuyang2011@tsinghua.edu.cn).

## Citation
```
@article{chen2024model,
  title={Model Composition for Multimodal Large Language Models},
  author={Chen, Chi and Du, Yiyang and Fang, Zheng and Wang, Ziyue and Luo, Fuwen and Li, Peng and Yan, Ming and Zhang, Ji and Huang, Fei and Sun, Maosong and others},
  journal={arXiv preprint arXiv:2402.12750},
  year={2024}
}
```