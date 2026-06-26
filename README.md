<div align="center">

# Exposure Bias Can Alleviate Itself via Directional and Frequency Rectification in Flow Matching

### DEFAR: Directional-Frequency Adaptive Rectification

<p>
  <img src="https://img.shields.io/badge/ECCV-2026-4B8BBE?style=flat-square" alt="ECCV 2026">
  <img src="https://img.shields.io/badge/Code-coming%20soon-6A737D?style=flat-square&logo=github" alt="Code coming soon">
  <a href="https://github.com/wuliwuliy/DEFAR"><img src="https://img.shields.io/github/stars/wuliwuliy/DEFAR?style=flat-square&logo=github" alt="GitHub stars"></a>
  <img src="https://visitor-badge.laobi.icu/badge?page_id=wuliwuliy.DEFAR&left_color=gray&right_color=blue" alt="Visitors">
</p>

<p>
  <a href="#highlights">Highlights</a> |
  <a href="#method-overview">Method</a>
</p>

**[Guanbo Huang](https://wuliwuliy.github.io/)<sup>1,2,*,&Dagger;</sup>**,
**[Jingjia Mao](https://openreview.net/profile?id=~Jingjia_Mao1)<sup>1,2,*,&Dagger;</sup>**,
**[Fanding Huang](https://hf618.github.io/)<sup>1,*</sup>**,
**[Fengkai Liu](https://liufeeky.github.io/)<sup>1</sup>**,
**[Xiangyang Luo](https://luoxyhappy.github.io/)<sup>1</sup>**,
**[Yaoyuan Liang](https://scholar.google.com/citations?user=n47YI20AAAAJ&hl=zh-CN&oi=sra)<sup>1</sup>**,
**[Jiasheng Lu](https://scholar.google.com/citations?user=uHeYEtEAAAAJ&hl=en)<sup>2</sup>**,
**[Xiaoe Wang](https://sites.google.com/view/wangxiaoe1/%E9%A6%96%E9%A1%B5)<sup>2</sup>**,
**[Pei Liu](https://github.com/windelvin?tab=projects)<sup>2</sup>**,
**[Ruiliu Fu](https://dblp.org/pid/304/2996.html)<sup>2,&dagger;</sup>**,
**[Ruqi Huang](https://rqhuang88.github.io/)<sup>1,&dagger;</sup>**,
**[Shao-Lun Huang](https://sites.google.com/view/slhuang/home)<sup>1,&dagger;</sup>**

<sup>1</sup>Tsinghua Shenzhen International Graduate School, Tsinghua University  
<sup>2</sup>Central Media Technology Institute, Huawei

<sup>*</sup> Equal contribution.  
<sup>&dagger;</sup> Corresponding authors.  
<sup>&Dagger;</sup> Work conducted during internship at Central Media Technology Institute, Huawei.

</div>

## Highlights

DEFAR studies exposure bias in Flow Matching and shows that the bias itself can provide useful self-feedback signals. Instead of only suppressing exposure bias with static alignment or external heuristics, DEFAR simulates one-step inference during training and uses the resulting bias to adaptively rectify the model in two complementary dimensions.

- **Anti-Drift Rectification (ADR)** learns a restorative direction that steers drift-affected states back toward the data distribution.
- **Frequency Compensation (FC)** uses exposure bias as a negative-feedback weight to reinforce missing low-frequency components at high-noise timesteps.
- DEFAR improves image generation across CIFAR-10, CelebA-64, ImageNet-256, and ImageNet-512, while remaining compatible with stronger backbones and complementary mitigation strategies.

<div align="center">
  <img src="assets/teaser_quality.png" width="88%" alt="Qualitative comparison">
  <br>
  <sub>Qualitative comparison under the same random seed and 50-NFE inference. DEFAR produces more coherent structures and cleaner object-background boundaries.</sub>
</div>

## Method Overview

<div align="center">
  <img src="assets/defar_overview.png" width="94%" alt="DEFAR overview">
</div>

DEFAR augments the Flow Matching objective with two self-rectifying signals obtained from exposure bias. ADR operates on the directional drift induced by one-step inference simulation, while FC operates on the frequency deficiency revealed by the bias signal. The final objective jointly optimizes the ADR regularizer and the FC-reweighted Flow Matching loss.

<div align="center">
  <img src="assets/frequency_analysis.png" width="94%" alt="Frequency analysis">
  <br>
  <sub>Exposure bias highlights low-frequency information that the raw prediction under-emphasizes at high-noise timesteps, motivating FC.</sub>
</div>

## Star History

<a href="https://www.star-history.com/#wuliwuliy/DEFAR&type=date&legend=top-left">
  <img src="https://api.star-history.com/svg?repos=wuliwuliy/DEFAR&type=date&legend=top-left" alt="Star history chart">
</a>