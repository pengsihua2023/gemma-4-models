# gemma-4-models
Google DeepMind 于 **2026年4月2日** 在 Hugging Face 上正式发布了 **Gemma 4** 系列模型。

目前，官方在 Hugging Face 的 [Google 集合 (Collection)](https://huggingface.co/collections/google/gemma-4) 中共提供了 **8 个** 核心开源模型（涵盖 4 种尺寸，每种尺寸均有“预训练版”和“指令微调版”）：

### 1. 模型规格分类
Gemma 4 采用了两种不同的架构：**Dense（稠密型）** 和 **MoE（混合专家型）**。

| 模型名称 | 架构类型 | 参数量 (Total) | 适用场景 |
| :--- | :--- | :--- | :--- |
| **Gemma 4 E2B** | Dense | ~5B (有效 2.3B) | 手机端侧、极速推理 |
| **Gemma 4 E4B** | Dense | ~8B (有效 4.5B) | 高端手机、笔记本电脑 |
| **Gemma 4 26B-A4B**| **MoE** | 26B (激活 4B) | 平衡性能与速度，适合 Agent 开发 |
| **Gemma 4 31B** | Dense | 30.7B | 高性能推理、复杂编程、学术研究 |

---

### 2. Hugging Face 上的具体模型列表
每个尺寸都包含两个版本，总计 8 个 Repo：

* **Instruction Tuned (IT) 版本**（适合对话和任务执行）：
    * `google/gemma-4-31B-it`
    * `google/gemma-4-26B-A4B-it`
    * `google/gemma-4-E4B-it`
    * `google/gemma-4-E2B-it`
* **Base / Pre-trained (PT) 版本**（适合进一步微调）：
    * `google/gemma-4-31B`
    * `google/gemma-4-26B-A4B`
    * `google/gemma-4-E4B`
    * `google/gemma-4-E2B`

---

### 3. 重要更新提示
* **开源协议：** Gemma 4 已经由之前的商业限制性协议更改为更加开放的 **Apache 2.0** 协议。
* **多模态能力：** * **E2B / E4B**：支持 **Any-to-Any**（文本、图像、音频输入）。
    * **26B / 31B**：支持 **Image-Text-to-Text**（主要针对视觉推理增强）。
* **推理功能：** 31B 和 26B 版本原生支持“思维链”解析（Reasoning tokens），在 HF 上使用时建议配合最新的 `transformers v5.5.0` 或更高版本。

除了 Google 官方发布的这些模型，社区（如 NVIDIA）也已经发布了针对特定硬件优化的量化版本（如 `nvidia/Gemma-4-31B-IT-NVFP4`）。
