# Awesome-Code-LLM

This is the repo for our survey [Unifying the Perspectives of NLP and Software Engineering: A Survey on Language Models for Code](https://arxiv.org/abs/2311.07989) - a comprehensive review of LLM researches for code. Works in each category are ordered chronologically. If you have a basic understanding of machine learning but are new to NLP, we also provide a list of recommended readings in [section 6](#6-recommended-readings).

<p align='center'>
<img src='imgs/overview.png' style='width: 80%; '>
</p>

## News

🔥🔥🔥 [2024/03] We included a new downstream task: [frontend development & web agents](#frontend-development--web-agents).

🔥🔥&nbsp;&nbsp;&nbsp;&nbsp; [2024/03] Claude 3 is out, with 84.9 reported performance on HumanEval: [The Claude 3 Model Family](https://www-cdn.anthropic.com/de8ba9b01c9ab7cbabf5c33b80b7bbc618857627/Model_Card_Claude_3.pdf).

🔥🔥&nbsp;&nbsp;&nbsp;&nbsp; [2024/03] We included a new downstream task: [compiler optimization](#compiler-optimization).

🔥🔥&nbsp;&nbsp;&nbsp;&nbsp; [2024/02] [StarCoder 2 and The Stack v2: The Next Generation](https://arxiv.org/abs/2402.19173).

🔥&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2024/02] Google open-sourced [Gemma](https://blog.google/technology/developers/gemma-open-models/).

🔥&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; [2024/02] Amazon ICLR 2024 paper: [Code Representation Learning At Scale](https://arxiv.org/abs/2402.01935).

## Table of Contents

1. [Surveys](#1-surveys)

2. [Models](#2-models)

   2.1 [Off-the-Shelf LLM](#21-off-the-shelf-llm)

   2.2 [Existing LLM Further Trained on Code](#22-existing-llm-further-trained-on-code)

   2.3 [General Pretraining on Code](#23-general-pretraining-on-code)

   - [Encoder](#encoder)
   - [Decoder](#decoder)
   - [Encoder-Decoder](#encoder-decoder)
   - [UniLM](#unilm)

   <!-- prettier ignore -->

   2.4 [Instruction Fine-Tuning on Code](#24-instruction-fine-tuning-on-code)

   2.5 [Reinforcement Learning on Code](#25-reinforcement-learning-on-code)

3. [When Coding Meets Reasoning](#3-when-coding-meets-reasoning)

   3.1 [Coding for Reasoning](#31-coding-for-reasoning)

   3.2 [Coding via Planning](#32-coding-via-planning)

4. [Methods/Models for Downstream Tasks](#4-methodsmodels-for-downstream-tasks)

   - [Compiler Optimization](#compiler-optimization)
   - [Frontend Development & Web Agents](#frontend-development--web-agents)

5. [Datasets](#5-datasets)

   5.1 [Pretraining](#51-pretraining)

   5.2 [Benchmarks](#52-benchmarks)

   - [Program Synthesis](#program-synthesis)
   - [Text-to-SQL](#text-to-sql)
   - [Code Translation](#code-translation)
   - [Program Repair](#program-repair)
   - [Code Summarization](#code-summarization)
   - [Defect/Vulnerability Detection](#defectvulnerability-detection)
   - [Code Retrieval](#code-retrieval)
   - [Type Inference](#type-inference)
   - [Commit Message Generation](#commit-message-generation)
   - [Repo-Level Coding](#repo-level-coding)

6. [Recommended Readings](#6-recommended-readings)

7. [Citation](#citation)

8. [Star History](#star-history)

## 1. Surveys

We list six recent surveys on similar topics. While they are all about language models for code, the first two focus on NLP side, and the later four focus on SE side.

1. "Large Language Models Meet NL2Code: A Survey", 2022-12, ACL 2023, [[paper](https://arxiv.org/abs/2212.09420)]

2. "A Survey on Pretrained Language Models for Neural Code Intelligence", 2022-12, arXiv, [[paper](https://arxiv.org/abs/2212.10079)]

3. "An Empirical Comparison of Pre-Trained Models of Source Code", 2023-02, ICSE 2023, [[paper](https://arxiv.org/abs/2302.04026)]

4. "Large Language Models for Software Engineering: A Systematic Literature Review", 2023-08, arXiv, [[paper](https://arxiv.org/abs/2308.10620)]

5. "Towards an Understanding of Large Language Models in Software Engineering Tasks", 2023-08, arXiv, [[paper](https://arxiv.org/abs/2308.11396)]

6. "Pitfalls in Language Models for Code Intelligence: A Taxonomy and Survey", 2023-10, arXiv, [[paper](https://arxiv.org/abs/2310.17903)]

## 2. Models

### 2.1 Off-the-Shelf LLM

These LLMs are not specifically trained for code, but have demonstrated varying coding capability.

1. **LaMDA**: "LaMDA: Language Models for Dialog Applications", 2022-01, arXiv, [[paper](https://arxiv.org/abs/2201.08239)]

2. **PaLM**: "PaLM: Scaling Language Modeling with Pathways", 2022-04, arXiv, [[paper](https://arxiv.org/abs/2204.02311)]

3. **GPT-NeoX**: "GPT-NeoX-20B: An Open-Source Autoregressive Language Model", 2022-04, ACL 2022 Workshop on Challenges & Perspectives in Creating Large Language Models, [[paper](https://arxiv.org/abs/2204.06745)] [[repo](https://github.com/EleutherAI/gpt-neox)]

4. **BLOOM**: "BLOOM: A 176B-Parameter Open-Access Multilingual Language Model", 2022-11, arXiv, [[paper](https://arxiv.org/abs/2211.05100)] [[model](https://huggingface.co/models?search=bigscience/bloom)]

5. **LLaMA**: "LLaMA: Open and Efficient Foundation Language Models", 2023-02, arXiv, [[paper](https://arxiv.org/abs/2302.13971)]

6. **GPT-4**: "GPT-4 Technical Report", 2023-03, arXiv, [[paper](https://arxiv.org/abs/2303.08774)]

7. **LLaMA 2**: "Llama 2: Open Foundation and Fine-Tuned Chat Models", 2023-07, arXiv, [[paper](https://arxiv.org/abs/2307.09288)] [[repo](https://github.com/facebookresearch/llama)]

8. **Phi-1.5**: "Textbooks Are All You Need II: phi-1.5 technical report", 2023-09, arXiv, [[paper](https://arxiv.org/abs/2309.05463)] [[model](https://huggingface.co/microsoft/phi-1_5)]

9. **Baichuan 2**: "Baichuan 2: Open Large-scale Language Models", 2023-09, arXiv, [[paper](https://arxiv.org/abs/2309.10305)] [[repo](https://github.com/baichuan-inc/Baichuan2)]

10. **Qwen**: "Qwen Technical Report", 2023-09, arXiv, [[paper](https://arxiv.org/abs/2309.16609)] [[repo](https://github.com/QwenLM/Qwen)]

11. **Mistral**: "Mistral 7B", 2023-10, arXiv, [[paper](https://arxiv.org/abs/2310.06825)] [[repo](https://github.com/mistralai/mistral-src)]

12. **Gemini**: "Gemini: A Family of Highly Capable Multimodal Models", 2023-12, arXiv, [[paper](https://arxiv.org/abs/2312.11805)]

13. **Phi-2**: "Phi-2: The surprising power of small language models", 2023-12, arXiv, [[blog](https://www.microsoft.com/en-us/research/blog/phi-2-the-surprising-power-of-small-language-models/)]

14. **YAYI2**: "YAYI 2: Multilingual Open-Source Large Language Models", 2023-12, arXiv, [[paper](https://arxiv.org/abs/2312.14862)] [[repo](https://github.com/wenge-research/YAYI2)]

15. **DeepSeek**: "DeepSeek LLM: Scaling Open-Source Language Models with Longtermism", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.02954)] [[repo](https://github.com/deepseek-ai/DeepSeek-LLM)]

16. **Mixtral**: "Mixtral of Experts", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.04088)] [[blog](https://mistral.ai/news/mixtral-of-experts/)]

17. **DeepSeekMoE**: "DeepSeekMoE: Towards Ultimate Expert Specialization in Mixture-of-Experts Language Models", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.12246)] [[repo](https://github.com/deepseek-ai/DeepSeek-MoE)]

18. **Orion**: "Orion-14B: Open-source Multilingual Large Language Models", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.06066)] [[repo](https://github.com/OrionStarAI/Orion)]

19. **OLMo**: "OLMo: Accelerating the Science of Language Models", 2024-02, arXiv, [[paper](https://arxiv.org/abs/2402.00838)] [[repo](https://github.com/allenai/OLMo)]

20. **Gemma**: "Gemma: Open Models Based on Gemini Research and Technology", 2024-02, [[paper](https://storage.googleapis.com/deepmind-media/gemma/gemma-report.pdf)] [[blog](https://blog.google/technology/developers/gemma-open-models/)]

21. **Claude 3**: "The Claude 3 Model Family: Opus, Sonnet, Haiku", 2024-03, [[paper](https://www-cdn.anthropic.com/de8ba9b01c9ab7cbabf5c33b80b7bbc618857627/Model_Card_Claude_3.pdf)] [[blog](https://www.anthropic.com/news/claude-3-family)]

### 2.2 Existing LLM Further Trained on Code

These models are general-purpose LLMs further pretrained on code-related data.

1. **Codex** (GPT-3): "Evaluating Large Language Models Trained on Code", 2021-07, arXiv, [[paper](https://arxiv.org/abs/2107.03374)]

2. **PaLM Coder** (PaLM): "PaLM: Scaling Language Modeling with Pathways", 2022-04, arXiv, [[paper](https://arxiv.org/abs/2204.02311)]

3. **Minerva** (PaLM): "Solving Quantitative Reasoning Problems with Language Models", 2022-06, arXiv, [[paper](https://arxiv.org/abs/2206.14858)]

4. **PaLM 2 \*** (PaLM 2): "PaLM 2 Technical Report", 2023-05, arXiv, [[paper](https://arxiv.org/abs/2305.10403)]

5. **Code LLaMA** (LLaMA 2): "Code Llama: Open Foundation Models for Code", 2023-08, arXiv, [[paper](https://arxiv.org/abs/2308.12950)] [[repo](https://github.com/facebookresearch/codellama)]

### 2.3 General Pretraining on Code

These models are Transformer encoders, decoders, and encoder-decoders pretrained from scratch using existing objectives for general language modeling.

<p align='center'>
<img src='imgs/model_detail.png' style='width: 90%; '>
</p>

#### Encoder

1. **CuBERT** (MLM + NSP): "Learning and Evaluating Contextual Embedding of Source Code", 2019-12, ICML 2020, [[paper](https://arxiv.org/abs/2001.00059)] [[repo](https://github.com/google-research/google-research/tree/master/cubert)]

2. **CodeBERT** (MLM + RTD): "CodeBERT: A Pre-Trained Model for Programming and Natural Languages", 2020-02, EMNLP findings 2020, [[paper](https://arxiv.org/abs/2002.08155)] [[repo](https://github.com/microsoft/CodeBERT)]

3. **GraphCodeBERT** (MLM + DFG Edge Prediction + DFG Node Alignment): "GraphCodeBERT: Pre-training Code Representations with Data Flow", 2020-09, ICLR 2021, [[paper](https://arxiv.org/abs/2009.08366)] [[repo](https://github.com/microsoft/CodeBERT)]

4. **SynCoBERT** (MLM + Identifier Prediction + AST Edge Prediction + Contrastive Learning): "SynCoBERT: Syntax-Guided Multi-Modal Contrastive Pre-Training for Code Representation", 2021-08, arXiv, [[paper](https://arxiv.org/abs/2108.04556)]

5. **DISCO** (MLM + Node Type MLM + Contrastive Learning): "Towards Learning (Dis)-Similarity of Source Code from Program Contrasts", 2021-q0, ACL 2022, [[paper](https://arxiv.org/abs/2110.03868)]

6. **Code-MVP** (MLM + Type Inference + Contrastive Learning): "CODE-MVP: Learning to Represent Source Code from Multiple Views with Contrastive Pre-Training", 2022-05, NAACL 2022 Technical Track, [[paper](https://arxiv.org/abs/2205.02029)]

7. **CodeSage** (MLM + Deobfuscation + Contrastive Learning): "Code Representation Learning At Scale", 2024-02, ICLR 2024, [[paper](https://arxiv.org/abs/2402.01935)]

#### Decoder

1. **GPT-C** (CLM): "IntelliCode Compose: Code Generation Using Transformer", 2020-05, ESEC/FSE 2020, [[paper](https://arxiv.org/abs/2005.08025)]

2. **CodeGPT** (CLM): "CodeXGLUE: A Machine Learning Benchmark Dataset for Code Understanding and Generation", 2021-02, NeurIPS Datasets and Benchmarks 2021, [[paper](https://arxiv.org/abs/2102.04664)] [[repo](https://github.com/microsoft/CodeXGLUE)]

3. **CodeParrot** (CLM), 2021-12, [[blog](https://huggingface.co/blog/codeparrot)]

4. **PolyCoder** (CLM): "A Systematic Evaluation of Large Language Models of Code", 2022-02, - DL4C@ICLR 2022, [[paper](https://arxiv.org/abs/2202.13169)] [[repo](https://github.com/VHellendoorn/Code-LMs)]

5. **CodeGen** (CLM): "CodeGen: An Open Large Language Model for Code with Multi-Turn Program Synthesis", 2022-03, ICLR 2023, [[paper](https://arxiv.org/abs/2203.13474)] [[repo](https://github.com/salesforce/CodeGen)]

6. **InCoder** (Causal Masking): "InCoder: A Generative Model for Code Infilling and Synthesis", 2022-04, ICLR 2023, [[paper](https://arxiv.org/abs/2204.05999)] [[repo](https://github.com/dpfried/incoder)]

7. **PyCodeGPT** (CLM): "CERT: Continual Pre-Training on Sketches for Library-Oriented Code Generation", 2022-06, IJCAI-ECAI 2022, [[paper](https://arxiv.org/abs/2206.06888)] [[repo](https://github.com/microsoft/PyCodeGPT)]

8. **PanGu-Coder** (CLM): "PanGu-Coder: Program Synthesis with Function-Level Language Modeling", 2022-07, arxiv, [[paper](https://arxiv.org/abs/2207.11280)]

9. **SantaCoder** (FIM): "SantaCoder: don't reach for the stars!", 2023-01, arXiv, [[paper](https://arxiv.org/abs/2301.03988)] [[model](https://huggingface.co/bigcode/santacoder)]

10. **CodeGeeX** (CLM): "CodeGeeX: A Pre-Trained Model for Code Generation with Multilingual Evaluations on HumanEval-X", 2023-03, arxiv, [[paper](https://arxiv.org/abs/2303.17568)] [[repo](https://github.com/THUDM/CodeGeeX)]

11. **StarCoder** (FIM): "StarCoder: may the source be with you!", 2023-05, arXiv, [[paper](https://arxiv.org/abs/2305.06161)] [[model](https://huggingface.co/bigcode/starcoder)]

12. **Phi-1** (CLM): "Textbooks Are All You Need", 2023-06, arxiv, [[paper](https://arxiv.org/abs/2306.11644)] [[model](https://huggingface.co/microsoft/phi-1)]

13. **CodeFuse** (CLM): "CodeFuse-13B: A Pretrained Multi-lingual Code Large Language Model", 2023-10, arxiv, [[paper](https://arxiv.org/abs/2310.06266)] [[model](https://huggingface.co/codefuse-ai/CodeFuse-13B)]

14. **CodeShell** (CLM), 2023-10, [[repo](https://github.com/WisdomShell/codeshell)]

15. **DeepSeek Coder** (CLM+FIM): "DeepSeek-Coder: When the Large Language Model Meets Programming -- The Rise of Code Intelligence", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.14196)][[repo](https://github.com/deepseek-ai/DeepSeek-Coder)]

16. **StarCoder2** (CLM+FIM): "StarCoder 2 and The Stack v2: The Next Generation", 2024-02, arXiv, [[paper](https://arxiv.org/abs/2402.19173)][[repo](https://github.com/bigcode-project/starcoder2)]

#### Encoder-Decoder

1. **PyMT5** (Span Corruption): "PyMT5: multi-mode translation of natural language and Python code with transformers", 2020-10, EMNLP 2020, [[paper](https://arxiv.org/abs/2010.03150)]

2. **Mastropaolo et al.** (MLM + Deobfuscation): "DOBF: A Deobfuscation Pre-Training Objective for Programming Languages", 2021-02, ICSE 2021, [[paper](https://arxiv.org/abs/2102.02017)] [[repo](https://github.com/antonio-mastropaolo/TransferLearning4Code)]

3. **DOBF** (Span Corruption): "Studying the Usage of Text-To-Text Transfer Transformer to Support Code-Related Tasks", 2021-02, NeurIPS 2021, [[paper](https://arxiv.org/abs/2102.07492)] [[repo](https://github.com/facebookresearch/CodeGen/blob/main/docs/dobf.md)]

4. **PLBART** (DAE): "Unified Pre-training for Program Understanding and Generation", 2021-03, NAACL 2021, [[paper](https://arxiv.org/abs/2103.06333)] [[repo](https://github.com/wasiahmad/PLBART)]

5. **CodeT5** (Span Corruption + Identifier Tagging + Masked Identifier Prediction + Text2Code + Code2Text): "CodeT5: Identifier-aware Unified Pre-trained Encoder-Decoder Models for Code Understanding and Generation", 2021-09, EMNLP 2021, [[paper](https://arxiv.org/abs/2109.00859)] [[repo](https://github.com/salesforce/CodeT5)]

6. **SPT-Code** (Span Corruption + NSP + Method Name Prediction): "SPT-Code: Sequence-to-Sequence Pre-Training for Learning Source Code Representations", 2022-01, ICSE 2022 Technical Track, [[paper](https://arxiv.org/abs/2201.01549)]

7. **AlphaCode** (MLM + CLM): "Competition-Level Code Generation with AlphaCode", 2022-02, Science, [[paper](https://arxiv.org/abs/2203.07814)] [[arxiv](https://deepmind.google/discover/blog/competitive-programming-with-alphacode/)]
8. **NatGen** (Code Naturalization): "NatGen: Generative pre-training by "Naturalizing" source code", 2022-06, ESEC/FSE 2022, [[paper](https://arxiv.org/abs/2206.07585)] [[repo](https://github.com/saikat107/NatGen)]
9. **ERNIE-Code** (Span Corruption + Pivot-based Translation LM): "ERNIE-Code: Beyond English-Centric Cross-lingual Pretraining for Programming Languages", 2022-12, ACL23 (Findings), [[paper](https://aclanthology.org/2023.findings-acl.676.pdf)][[repo](https://github.com/PaddlePaddle/PaddleNLP/tree/develop/model_zoo/ernie-code)]

10. **CodeT5+** (Span Corruption + CLM + Text-Code Contrastive Learning + Text-Code Translation): "CodeT5+: Open Code Large Language Models for Code Understanding and Generation", 2023-05, arXiv, [[paper](https://arxiv.org/abs/2305.07922)] [[repo](https://github.com/salesforce/CodeT5)]

11. **AST-T5** (Span Corruption): "AST-T5: Structure-Aware Pretraining for Code Generation and Understanding", 2024-01, arXiv, [[paper](https://arxiv.org/abs/2401.03003)]

#### UniLM

1. **CugLM** (MLM + NSP + CLM): "Multi-task Learning based Pre-trained Language Model for Code Completion", 2020-12, ASE 2020, [[paper](https://arxiv.org/abs/2012.14631)]

2. **UniXcoder** (MLM + NSP + CLM + Span Corruption + Contrastive Learning + Code2Text): "UniXcoder: Unified Cross-Modal Pre-training for Code Representation", 2022-03, ACL 2022, [[paper](https://arxiv.org/abs/2203.03850)] [[repo](https://github.com/microsoft/CodeBERT)]

### 2.4 Instruction Fine-Tuning on Code

These models apply Instruction Fine-Tuning techniques to enhance the capacities of Code LLMs.

1. **WizardCoder** (StarCoder + Evol-Instruct): "WizardCoder: Empowering Code Large Language Models with Evol-Instruct", 2023-06, arXiv, [[paper](https://arxiv.org/abs/2306.08568)] [[repo](https://github.com/nlpxucan/WizardLM)]

2. **PanGu-Coder 2** (StarCoder + Evol-Instruct + RRTF): "PanGu-Coder2: Boosting Large Language Models for Code with Ranking Feedback", 2023-07, arXiv, [[paper](https://arxiv.org/abs/2307.14936)]

3. **OctoCoder** (StarCoder) / **OctoGeeX** (CodeGeeX2): "OctoPack: Instruction Tuning Code Large Language Models", 2023-08, arXiv, [[paper](https://arxiv.org/abs/2308.07124)] [[repo](https://github.com/bigcode-project/octopack)]

4. **MFTCoder** (Code LLaMA): "MFTCoder: Boosting Code LLMs with Multitask Fine-Tuning", 2023-11, arXiv, [[paper](https://arxiv.org/abs/2311.02303)] [[repo](https://github.com/codefuse-ai/MFTCoder)]

### 2.5 Reinforcement Learning on Code

1. **CompCoder**: "Compilable Neural Code Generation with Compiler Feedback", 2022-03, ACL 2022, [[paper](https://arxiv.org/abs/2203.05132)]

2. **CodeRL**: "CodeRL: Mastering Code Generation through Pretrained Models and Deep Reinforcement Learning", 2022-07, NeurIPS 2022, [[paper](https://arxiv.org/abs/2207.01780)] [[repo](https://github.com/salesforce/CodeRL)]

3. **PPOCoder**: "Execution-based Code Generation using Deep Reinforcement Learning", 2023-01, TMLR 2023, [[paper](https://arxiv.org/abs/2301.13816)] [[repo](https://github.com/reddy-lab-code-research/PPOCoder)]

4. **RLTF**: "RLTF: Reinforcement Learning from Unit Test Feedback", 2023-07, arXiv, [[paper](https://arxiv.org/abs/2307.04349)] [[repo](https://github.com/Zyq-scut/RLTF)]

## 3. When Coding Meets Reasoning

### 3.1 Coding for Reasoning

1. **PAL**: "PAL: Program-aided Language Models", 2022-11, ICML 2023, [[paper](https://arxiv.org/abs/2211.10435)] [[repo](https://github.com/reasoning-machines/pal)]

2. **PoT**: "Program of Thoughts Prompting: Disentangling Computation from Reasoning for Numerical Reasoning Tasks", 2022-11, TMLR 2023, [[paper](https://arxiv.org/abs/2211.12588)] [[repo](https://github.com/wenhuchen/Program-of-Thoughts)]

3. **CoC**: "Chain of Code: Reasoning with a Language Model-Augmented Code Emulator", 2023-12, arXiv, [[paper](https://arxiv.org/abs/2312.04474)]

### 3.2 Coding via Planning

1. **Self-collaboration**: "Self-collaboration Code Generation via ChatGPT", 2023-04, arXiv, [[paper](https://arxiv.org/abs/2304.07590)]

2. **ChatDev**: "Communicative Agents for Software Development", 2023-07, arXiv, [[paper](https://arxiv.org/abs/2307.07924)] [[repo](https://github.com/OpenBMB/ChatDev)]

3. **MetaGPT**: "MetaGPT: Meta Programming for A Multi-Agent Collaborative Framework", 2023-08, arXiv, [[paper](https://arxiv.org/abs/2308.00352)] [[repo](https://github.com/geekan/MetaGPT)]

## 4. Methods/Models for Downstream Tasks

For each task, the first column contains non-neural methods (e.g. n-gram, TF-IDF, and (occasionally) static program analysis); the second column contains non-Transformer neural methods (e.g. LSTM, CNN, GNN); the third column contains Transformer based methods (e.g. BERT, GPT, T5).

<p align='center'>
<img src='imgs/downstream-1.png' style='width: 100%; '>
<img src='imgs/downstream-2.png' style='width: 100%; '>
<img src='imgs/downstream-3.png' style='width: 100%; '>
<img src='imgs/downstream-4.png' style='width: 100%; '>
<img src='imgs/downstream-5.png' style='width: 100%; '>
</p>

### Compiler Optimization

- "Large Language Models for Compiler Optimization", 2023-09, [[paper](https://arxiv.org/abs/2309.07062)]

- "Refining Decompiled C Code with Large Language Models", 2023-10, [[paper](https://arxiv.org/abs/2310.06530)]

- "Priority Sampling of Large Language Models for Compilers", 2024-02, [[paper](https://arxiv.org/abs/2402.18734)]

### Frontend Development & Web Agents

- "Seeking the user interface", 2014-09, ASE 2014, [[paper](https://dl.acm.org/doi/10.1145/2642937.2642976)]

- "pix2code: Generating Code from a Graphical User Interface Screenshot", 2017-05, EICS 2018, [[paper](https://arxiv.org/abs/1705.07962)]

- "Machine Learning-Based Prototyping of Graphical User Interfaces for Mobile Apps", 2018-02, TSE 2020, [[paper](https://arxiv.org/abs/1802.02312)]

- "Automatic HTML Code Generation from Mock-Up Images Using Machine Learning Techniques", 2019-04, EBBT 2019, [[paper](https://ieeexplore.ieee.org/abstract/document/8741736)]

- "Sketch2code: Generating a website from a paper mockup", 2019-05, [[paper](https://arxiv.org/abs/1905.13750)]

- "HTLM: Hyper-Text Pre-Training and Prompting of Language Models", 2021-07, ICLR 2022, [[paper](https://arxiv.org/abs/2107.06955)]

- "MarkupLM: Pre-training of Text and Markup Language for Visually-rich Document Understanding", 2021-10, ACL 2022, [[paper](https://arxiv.org/abs/2110.08518)]

- "WebKE: Knowledge Extraction from Semi-structured Web with Pre-trained Markup Language Model", 2021-10, CIKM 2021, [[paper](https://dl.acm.org/doi/abs/10.1145/3459637.3482491)]

- "WebGPT: Browser-assisted question-answering with human feedback", 2021-12, [[paper](https://arxiv.org/abs/2112.09332)]

- "CM3: A Causal Masked Multimodal Model of the Internet", 2022-01, [[paper](https://arxiv.org/abs/2201.07520)]

- "DOM-LM: Learning Generalizable Representations for HTML Documents", 2022-01, [[paper](https://arxiv.org/abs/2201.10608)]

- "WebFormer: The Web-page Transformer for Structure Information Extraction", 2022-02, WWW 2022, [[paper](https://arxiv.org/abs/2202.00217)]

- "A Dataset for Interactive Vision-Language Navigation with Unknown Command Feasibility", 2022-02, ECCV 2022, [[paper](https://arxiv.org/abs/2202.02312)]

- "WebShop: Towards Scalable Real-World Web Interaction with Grounded Language Agents", 2022-07, NeurIPS 2022, [[paper](https://arxiv.org/abs/2207.01206)]

- "Pix2Struct: Screenshot Parsing as Pretraining for Visual Language Understanding", 2022-10, ICML 2023, [[paper](https://arxiv.org/abs/2210.03347)]

- "Understanding HTML with Large Language Models", 2022-10, EMNLP 2023 findings, [[paper](https://arxiv.org/abs/2210.03945)]

- "WebUI: A Dataset for Enhancing Visual UI Understanding with Web Semantics", 2023-01, CHI 2023, [[paper](https://arxiv.org/abs/2301.13280)]

- "Learning UI-to-Code Reverse Generator Using Visual Critic Without Rendering", 2023-05, [[paper](https://arxiv.org/abs/2305.14637)]

- "Mind2Web: Towards a Generalist Agent for the Web", 2023-06, NeurIPS 2023, [[paper](https://arxiv.org/abs/2306.06070)]

- "A Real-World WebAgent with Planning, Long Context Understanding, and Program Synthesis", 2023-07, ICLR 2024, [[paper](https://arxiv.org/abs/2307.12856)]

- "CogAgent: A Visual Language Model for GUI Agents", 2023-12, [[paper](https://arxiv.org/abs/2312.08914)]

- "GPT-4V(ision) is a Generalist Web Agent, if Grounded", 2024-01, [[paper](https://arxiv.org/abs/2401.01614)]

- "WebVoyager: Building an End-to-End Web Agent with Large Multimodal Models", 2024-01, [[paper](https://arxiv.org/abs/2401.13919)]

- "WebLINX: Real-World Website Navigation with Multi-Turn Dialogue", 2024-02, [[paper](https://arxiv.org/abs/2402.05930)]

- "OmniACT: A Dataset and Benchmark for Enabling Multimodal Generalist Autonomous Agents for Desktop and Web", 2024-02, [[paper](https://arxiv.org/abs/2402.17553)]

- "Design2Code: How Far Are We From Automating Front-End Engineering?", 2024-03, [[paper](https://arxiv.org/abs/2403.03163)]

## 5. Datasets

### 5.1 Pretraining

1. **CodeSearchNet**: "CodeSearchNet Challenge: Evaluating the State of Semantic Code Search", 2019-09, arXiv, [[paper](https://arxiv.org/abs/1909.09436)] [[repo](https://github.com/github/CodeSearchNet)] [[data](https://huggingface.co/datasets/code_search_net)]

2. **The Pile**: "The Pile: An 800GB Dataset of Diverse Text for Language Modeling", 2020-12, arXiv, [[paper](https://arxiv.org/abs/2101.00027)] [[data](https://pile.eleuther.ai/)]

3. **CodeParrot**, 2022-02, [[data](https://huggingface.co/datasets/codeparrot/github-code)]

4. **The Stack**: "The Stack: 3 TB of permissively licensed source code", 2022-11, arXiv, [[paper](https://arxiv.org/abs/2211.15533)] [[data](https://huggingface.co/datasets/bigcode/the-stack)]

5. **ROOTS**: "The BigScience ROOTS Corpus: A 1.6TB Composite Multilingual Dataset", 2023-03, NeurIPS 2022 Datasets and Benchmarks Track, [[paper](https://arxiv.org/abs/2303.03915)] [[data](https://huggingface.co/datasets?search=bigscience-data/roots)]

6. **The Stack v2**: "StarCoder 2 and The Stack v2: The Next Generation", 2024-02, arXiv, [[paper](https://arxiv.org/abs/2402.19173)] [[data](https://huggingface.co/datasets/bigcode/the-stack-v2-dedup)]

### 5.2 Benchmarks

1. **CodeXGLUE**: "CodeXGLUE: A Machine Learning Benchmark Dataset for Code Understanding and Generation", 2021-02, NeurIPS Datasets and Benchmarks 2021, [[paper](https://arxiv.org/abs/2102.04664)] [[repo](https://github.com/microsoft/CodeXGLUE)] [[data](https://huggingface.co/datasets?search=code_x_glue)]

#### Program Synthesis

| Date    | Venue                            | Benchmark              | Size                 | Language                                                                         | Source                                                                                                                                                                                                                                                                                       |
| ------- | -------------------------------- | ---------------------- | -------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2018-02 | LREC 2018                        | NL2Bash                | 9305                 | Bash                                                                             | "NL2Bash: A Corpus and Semantic Parser for Natural Language Interface to the Linux Operating System" [[paper](https://arxiv.org/abs/1802.08979)] [[data](https://github.com/TellinaTool/nl2bash)]                                                                                            |
| 2018-08 | EMNLP 2018                       | CONCODE                | 104K                 | Java                                                                             | "Mapping Language to Code in Programmatic Context" [[paper](https://arxiv.org/abs/1808.09588)] [[data](https://github.com/sriniiyer/concode)]                                                                                                                                                |
| 2019-10 | EMNLP-IJCNLP 2019                | JuICe                  | 1.5M/3725 \*         | Python                                                                           | "JuICe: A Large Scale Distantly Supervised Dataset for Open Domain Context-based Code Generation" [[paper](https://arxiv.org/abs/1910.02216)] [[data](https://github.com/rajasagashe/juice)]                                                                                                 |
| 2021-05 | NeurIPS 2021                     | APPS                   | 10000                | Python                                                                           | "Measuring Coding Challenge Competence With APPS" [[paper](https://arxiv.org/abs/2105.09938)] [[data](https://github.com/hendrycks/apps)]                                                                                                                                                    |
| 2021-07 | arXiv                            | HumanEval              | 164                  | Python                                                                           | "Evaluating Large Language Models Trained on Code" [[paper](https://arxiv.org/abs/2107.03374)] [[data](https://github.com/openai/human-eval)]                                                                                                                                                |
| 2021-08 | arXiv                            | MBPP/MathQA-Python     | 974/23914            | Python                                                                           | "Program Synthesis with Large Language Models" [[paper](https://arxiv.org/abs/2108.07732)] [[MBPP](https://github.com/google-research/google-research/tree/master/mbpp)] [[MathQA-Python](https://github.com/google/trax/blob/master/trax/examples/MathQA_Python_generation_notebook.ipynb)] |
| 2021-08 | ACL/IJCNLP 2021                  | PlotCoder              | 40797                | Python                                                                           | "PlotCoder: Hierarchical Decoding for Synthesizing Visualization Code in Programmatic Context" [[paper](https://aclanthology.org/2021.acl-long.169/)] [[data](https://github.com/jungyhuk/plotcoder)]                                                                                        |
| 2022-01 | arXiv                            | DSP                    | 1119                 | Python                                                                           | "Training and Evaluating a Jupyter Notebook Data Science Assistant" [[paper](https://arxiv.org/abs/2201.12901)] [[data](https://github.com/microsoft/DataScienceProblems)]                                                                                                                   |
| 2022-02 | Science                          | CodeContests           | 13610                | C++, Python, Java                                                                | "Competition-Level Code Generation with AlphaCode" [[paper](https://arxiv.org/abs/2203.07814)] [[data](https://github.com/google-deepmind/code_contests)]                                                                                                                                    |
| 2022-03 | EACL 2023 Findings               | MCoNaLa                | 896                  | Python                                                                           | "MCoNaLa: A Benchmark for Code Generation from Multiple Natural Languages" [[paper](https://arxiv.org/abs/2203.08388)] [[data](https://github.com/zorazrw/multilingual-conala)]                                                                                                              |
| 2022-06 | arXiv                            | AixBench               | 336                  | Java                                                                             | "AixBench: A Code Generation Benchmark Dataset" [[paper](https://arxiv.org/abs/2206.13179)] [[data](https://github.com/aixcoder-plugin/nl2code-dataset)]                                                                                                                                     |
| 2022-08 | IEEE Trans. Software Engineering | MultiPL-E              |                      |                                                                                  | "MultiPL-E: A Scalable and Extensible Approach to Benchmarking Neural Code Generation", [[paper](https://arxiv.org/abs/2208.08227)] [[data](https://github.com/nuprl/MultiPL-E)]                                                                                                             |
| 2022-10 | ICLR 2023                        | MBXP                   | 12.4K                | Python, Java, JS, TypeScript, Go, C#, PHP, Ruby, Kotlin, C++, Perl, Scala, Swift | "Multi-lingual Evaluation of Code Generation Models" [[paper](https://arxiv.org/abs/2210.14868)] [[data](https://github.com/amazon-science/mxeval)]                                                                                                                                          |
| 2022-10 | ICLR 2023                        | Multilingual HumanEval | 1.9K                 | Python, Java, JS, TypeScript, Go, C#, PHP, Ruby, Kotlin, Perl, Scala, Swift      | "Multi-lingual Evaluation of Code Generation Models" [[paper](https://arxiv.org/abs/2210.14868)] [[data](https://github.com/amazon-science/mxeval)]                                                                                                                                          |
| 2022-10 | ICLR 2023                        | MathQA-X               | 5.6K                 | Python, Java, JS                                                                 | "Multi-lingual Evaluation of Code Generation Models" [[paper](https://arxiv.org/abs/2210.14868)] [[data](https://github.com/amazon-science/mxeval)]                                                                                                                                          |
| 2022-11 | arXiv                            | ExeDS                  | 534                  | Python                                                                           | "Execution-based Evaluation for Data Science Code Generation Models" [[paper](https://arxiv.org/abs/2211.09374)] [[data](https://github.com/Jun-jie-Huang/ExeDS)]                                                                                                                            |
| 2022-11 | arXiv                            | DS-1000                | 1000                 | Python                                                                           | "DS-1000: A Natural and Reliable Benchmark for Data Science Code Generation" [[paper](https://arxiv.org/abs/2211.11501)] [[data](https://github.com/xlang-ai/DS-1000)]                                                                                                                       |
| 2022-12 | arXiv                            | ODEX                   | 945                  | Python                                                                           | "Execution-Based Evaluation for Open-Domain Code Generation" [[paper](https://arxiv.org/abs/2212.10481)] [[data](https://github.com/zorazrw/odex)]                                                                                                                                           |
| 2023-02 | arXiv                            | CoderEval              | 460                  | Python, Java                                                                     | "CoderEval: A Benchmark of Pragmatic Code Generation with Generative Pre-trained Models" [[paper](https://arxiv.org/abs/2302.00288)] [[data](https://github.com/CoderEval/CoderEval)]                                                                                                        |
| 2023-03 | arXiv                            | xCodeEval              | 5.5M                 | C, C#, C++, Go, Java, JS, Kotlin, PHP, Python, Ruby, Rust                        | "xCodeEval: A Large Scale Multilingual Multitask Benchmark for Code Understanding, Generation, Translation and Retrieval" [[paper](https://arxiv.org/abs/2303.03004)] [[data](https://github.com/ntunlp/xCodeEval)]                                                                          |
| 2023-03 | arXiv                            | HumanEval-X            | 820                  | Python, C++, Java, JS, Go                                                        | "CodeGeeX: A Pre-Trained Model for Code Generation with Multilingual Evaluations on HumanEval-X" [[paper](https://arxiv.org/abs/2303.17568)] [[data](https://hub.docker.com/r/codegeex/codegeex)]                                                                                            |
| 2023-05 | arXiv                            | HumanEval+             | 164                  | Python                                                                           | "Is Your Code Generated by ChatGPT Really Correct? Rigorous Evaluation of Large Language Models for Code Generation" [[paper](https://arxiv.org/abs/2305.01210)] [[data](https://github.com/evalplus/evalplus)]                                                                              |
| 2023-06 | arXiv                            | StudentEval            | 1749 $^\dagger$      | Python                                                                           | "StudentEval: A Benchmark of Student-Written Prompts for Large Language Models of Code" [[paper](https://arxiv.org/abs/2306.04556)] [[data](https://huggingface.co/datasets/wellesley-easel/StudentEval)]                                                                                    |
| 2023-08 | arXiv                            | HumanEvalPack          | 984                  | Python, JS, Go, Java, C++, Rust                                                  | "OctoPack: Instruction Tuning Code Large Language Models" [[paper](https://arxiv.org/abs/2308.07124)] [[data](https://huggingface.co/datasets/bigcode/humanevalpack)]                                                                                                                        |
| 2023-06 | NeurIPS 2023                     | DotPrompts             | 10538 $^\ddagger$    | Java                                                                             | "Guiding Language Models of Code with Global Context using Monitors" [[paper](https://arxiv.org/abs/2306.10763)] [[data](https://github.com/microsoft/monitors4codegen)]                                                                                                                     |
| 2023-09 | arXiv                            | CodeApex               | 476                  | C++                                                                              | "CodeApex: A Bilingual Programming Evaluation Benchmark for Large Language Models" [[paper](https://arxiv.org/abs/2309.01940)] [[data](https://github.com/APEXLAB/CodeApex)]                                                                                                                 |
| 2023-09 | arXiv                            | VerilogEval            | 8645/156 $^\diamond$ | Verilog                                                                          | "VerilogEval: Evaluating Large Language Models for Verilog Code Generation" [[paper](https://arxiv.org/abs/2309.07544)] [[data](https://github.com/NVlabs/verilog-eval)]                                                                                                                     |
| 2023-11 | arXiv                            | ML-Bench               | 10040                | Bash                                                                             | "ML-Bench: Large Language Models Leverage Open-source Libraries for Machine Learning Tasks" [[paper](https://arxiv.org/abs/2311.09835)] [[data](https://ml-bench.github.io/)]                                                                                                                |

\* Automatically mined/human-annotated

$^\dagger$ 1749 prompts for 48 problems

$^\ddagger$ 10538 prompts for 1420 problems

$^\diamond$ Machine/human prompts

#### Text-to-SQL

- "Deep learning driven natural languages text to SQL query conversion: A survey", 2022-08, arXiv, [[paper](https://arxiv.org/abs/2208.04415)]
- "Recent Advances in Text-to-SQL: A Survey of What We Have and What We Expect", 2022-08, COLING 2022, [[paper](https://arxiv.org/abs/2208.10099)]
- "A Survey on Text-to-SQL Parsing: Concepts, Methods, and Future Directions", 2022-08, arXiv, [[paper](https://arxiv.org/abs/2208.13629)]
- "A survey on deep learning approaches for text-to-SQL", 2023-01, VLDB J., [[paper](https://link.springer.com/article/10.1007/s00778-022-00776-8)]

| Date    | Venue               | Benchmark        | Size       | Language | Source                                                                                                                                                                                                    |
| ------- | ------------------- | ---------------- | ---------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2017-08 | arXiv               | WikiSQL          | 80654      |          | "Seq2SQL: Generating Structured Queries from Natural Language using Reinforcement Learning" [[paper](https://arxiv.org/abs/1709.00103)] [[data](https://github.com/salesforce/WikiSQL)]                   |
| 2018-06 | CL 2018             | Advising         | 4570       |          | "Improving Text-to-SQL Evaluation Methodology" [[paper](https://arxiv.org/abs/1806.09029)] [[data](https://github.com/jkkummerfeld/text2sql-data/)]                                                       |
| 2018-09 | EMNLP 2018          | Spider           | 10181      |          | "Spider: A Large-Scale Human-Labeled Dataset for Complex and Cross-Domain Semantic Parsing and Text-to-SQL Task" [[paper](https://arxiv.org/abs/1809.08887)] [[data](https://yale-lily.github.io/spider)] |
| 2019-06 | ACL 2019            | SParC            | 12726      |          | "SParC: Cross-Domain Semantic Parsing in Context" [[paper](https://arxiv.org/abs/1906.02285)] [[data](https://yale-lily.github.io/sparc)]                                                                 |
| 2019-07 | WWW 2020            | MIMICSQL         | 10000      |          | "Text-to-SQL Generation for Question Answering on Electronic Medical Records" [[paper](https://arxiv.org/abs/1908.01839)] [[data](https://github.com/wangpinggl/TREQS)]                                   |
| 2019-09 | EMNLP-IJCNLP 2019   | CoSQL            | 15598      |          | "CoSQL: A Conversational Text-to-SQL Challenge Towards Cross-Domain Natural Language Interfaces to Databases" [[paper](https://arxiv.org/abs/1909.05378)] [[data](https://yale-lily.github.io/cosql)]     |
| 2020-05 | LREC 2020           | Criteria-to-SQL  | 2003       |          | "Dataset and Enhanced Model for Eligibility Criteria-to-SQL Semantic Parsing" [[paper](https://aclanthology.org/2020.lrec-1.714/)] [[data](https://github.com/xiaojingyu92/Criteria2SQL)]                 |
| 2020-10 | EMNLP 2020 Findings | Squall           | 11276      |          | "On the Potential of Lexico-logical Alignments for Semantic Parsing to SQL Queries" [[paper](https://arxiv.org/abs/2010.11246)] [[data](https://github.com/tzshi/squall)]                                 |
| 2020-10 | NAACL-HLT 2021      | Spider-Realistic | 508        |          | "Structure-Grounded Pretraining for Text-to-SQL" [[paper](https://arxiv.org/abs/2010.12773)] [[data](https://zenodo.org/records/5205322)]                                                                 |
| 2021-06 | ACL/IJCNLP 2021     | Spider-Syn       | 8034       |          | "Towards Robustness of Text-to-SQL Models against Synonym Substitution" [[paper](https://arxiv.org/abs/2106.01065)] [[data](https://arxiv.org/abs/2106.01065)]                                            |
| 2021-06 | NLP4Prog 2021       | SEDE             | 12023      |          | "Text-to-SQL in the Wild: A Naturally-Occurring Dataset Based on Stack Exchange Data" [[paper](https://arxiv.org/abs/2106.05006)] [[data](https://github.com/hirupert/sede)]                              |
| 2021-06 | ACL/IJCNLP 2021     | KaggleDBQA       | 400        |          | "KaggleDBQA: Realistic Evaluation of Text-to-SQL Parsers" [[paper](https://arxiv.org/abs/2106.11455)] [[data](https://github.com/chiahsuan156/KaggleDBQA)]                                                |
| 2021-09 | EMNLP               | Spider-DK        | 535        |          | "Exploring Underexplored Limitations of Cross-Domain Text-to-SQL Generalization" [[paper](https://arxiv.org/abs/2109.05157)] [[data](https://github.com/ygan/Spider-DK)]                                  |
| 2022-05 | NAACL 2022 Findings | Spider-SS/CG     | 8034/45599 |          | "Measuring and Improving Compositional Generalization in Text-to-SQL via Component Alignment" [[paper](https://arxiv.org/abs/2205.02054)] [[data](https://github.com/ygan/SpiderSS-SpiderCG)]             |
| 2023-05 | arXiv               | BIRD             | 12751      |          | "Can LLM Already Serve as A Database Interface? A BIg Bench for Large-Scale Database Grounded Text-to-SQLs" [[paper](https://arxiv.org/abs/2305.03111)] [[data](https://bird-bench.github.io/)]           |

#### Code Translation

| Date    | Venue                                | Benchmark                | Size   | Language                                                  | Source                                                                                                                                                                                                              |
| ------- | ------------------------------------ | ------------------------ | ------ | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2020-06 | NeurIPS 2020                         | Transcoder GeeksforGeeks | 1.4K   | C++, Java, Python                                         | "Unsupervised Translation of Programming Languages" [[paper](https://arxiv.org/abs/2006.03511)] [[data](https://github.com/facebookresearch/TransCoder)]                                                            |
| 2021-02 | NeurIPS Datasets and Benchmarks 2021 | CodeTrans                | 11.8K  | Java, C#                                                  | "CodeXGLUE: A Machine Learning Benchmark Dataset for Code Understanding and Generation" [[paper](https://arxiv.org/abs/2102.04664)] [[data](https://huggingface.co/datasets/code_x_glue_cc_code_to_code_trans)]     |
| 2021-08 | ACL 2023 Findings                    | Avatar                   | 9515   | Java, Python                                              | "AVATAR: A Parallel Corpus for Java-Python Program Translation" [[paper](https://arxiv.org/abs/2108.11590)] [[data](https://github.com/wasiahmad/AVATAR)]                                                           |
| 2022-06 | AAAI 2022                            | CoST                     | 132K   | C++, Java, Python, C#, JS, PHP, C                         | "Multilingual Code Snippets Training for Program Translation" [[paper](https://ojs.aaai.org/index.php/AAAI/article/view/21434)] [[data](https://github.com/reddy-lab-code-research/MuST-CoST)]                      |
| 2022-06 | arXiv                                | XLCoST                   | 567K   | C++, Java, Python, C#, JS, PHP, C                         | "XLCoST: A Benchmark Dataset for Cross-lingual Code Intelligence" [[paper](https://arxiv.org/abs/2206.08474)] [[data](https://github.com/reddy-lab-code-research/XLCoST)]                                           |
| 2023-03 | arXiv                                | xCodeEval                | 5.6M   | C, C#, C++, Go, Java, JS, Kotlin, PHP, Python, Ruby, Rust | "xCodeEval: A Large Scale Multilingual Multitask Benchmark for Code Understanding, Generation, Translation and Retrieval" [[paper](https://arxiv.org/abs/2303.03004)] [[data](https://github.com/ntunlp/xCodeEval)] |
| 2023-03 | arXiv                                | HumanEval-X              | 1640   | Python, C++, Java, JS, Go                                 | "CodeGeeX: A Pre-Trained Model for Code Generation with Multilingual Evaluations on HumanEval-X" [[paper](https://arxiv.org/abs/2303.17568)] [[data](https://github.com/THUDM/CodeGeeX)]                            |
| 2023-08 | arXiv                                | G-TransEval              | 4000   | C++, Java, C#, JS, Python                                 | "On the Evaluation of Neural Code Translation: Taxonomy and Benchmark" [[paper](https://arxiv.org/abs/2308.08961)] [[data](https://github.com/PolyEval/G-TransEval)]                                                |
| 2023-10 | arXiv                                | CodeTransOcean           | 270.5K | 45                                                        | "CodeTransOcean: A Comprehensive Multilingual Benchmark for Code Translation" [[paper](https://arxiv.org/abs/2310.04951)] [[data](https://github.com/WeixiangYAN/CodeTransOcean)]                                   |

#### Program Repair

- "Neural Program Repair: Systems, Challenges and Solutions", 2022-02, Internetware 2022, [[paper](https://arxiv.org/abs/2202.10868)]
- "A Survey of Learning-based Automated Program Repair", 2023-01, arXiv, [[paper](https://arxiv.org/abs/2301.03270)]
- "A Survey on Automated Program Repair Techniques", 2023-03, arXiv, [[paper](https://arxiv.org/abs/2303.18184)]

| Date    | Venue                            | Benchmark           | Size      | Language                                                  | Source                                                                                                                                                                                                                    |
| ------- | -------------------------------- | ------------------- | --------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2014-07 | ISSTA 2014                       | Defects4J           | 357       | Java                                                      | "Defects4J: A Database of Existing Faults to Enable Controlled Testing Studies for Java Programs" [[paper](https://dl.acm.org/doi/10.1145/2610384.2628055)] [[data](https://github.com/rjust/defects4j)]                  |
| 2015-12 | IEEE Trans. Software Engineering | ManyBugs/IntroClass | 185/998   | C                                                         | "The ManyBugs and IntroClass Benchmarks for Automated Repair of C Programs" [[paper](https://ieeexplore.ieee.org/document/7153570)] [[data](https://repairbenchmarks.cs.umass.edu/)]                                      |
| 2016-11 | FSE 2016                         | BugAID              | 105K      | JS                                                        | "Discovering Bug Patterns in JavaScript" [[paper](https://dl.acm.org/doi/10.1145/2950290.2950308)] [[data](https://salt.ece.ubc.ca/software/bugaid/)]                                                                     |
| 2017-02 | AAAI 2017                        | DeepFix             | 6971      | C                                                         | "DeepFix: Fixing Common C Language Errors by Deep Learning" [[paper](https://ojs.aaai.org/index.php/AAAI/article/view/10742)] [[data](https://bitbucket.org/iiscseal/deepfix/src/master/)]                                |
| 2017-05 | ICSE-C 2017                      | Codeflaws           | 3902      | C                                                         | "DeepFix: Fixing Common C Language Errors by Deep Learning" [[paper](https://dl.acm.org/doi/10.1109/ICSE-C.2017.76)] [[data](https://codeflaws.github.io/)]                                                               |
| 2017-10 | SPLASH 2017                      | QuixBugs            | 80        | Java, Python                                              | "QuixBugs: a multi-lingual program repair benchmark set based on the quixey challenge" [[paper](https://dl.acm.org/doi/10.1145/3135932.3135941)] [[data](https://github.com/jkoppel/QuixBugs)]                            |
| 2018-05 | MSR 2018                         | Bugs.jar            | 1158      | Java                                                      | "Bugs.jar: a large-scale, diverse dataset of real-world Java bugs" [[paper](https://dl.acm.org/doi/10.1145/3196398.3196473)] [[data](https://github.com/bugs-dot-jar/bugs-dot-jar)]                                       |
| 2018-12 | ACM Trans. Softw. Eng. Methodol. | BFP                 | 124K      | Java                                                      | "An Empirical Study on Learning Bug-Fixing Patches in the Wild via Neural Machine Translation" [[paper](https://arxiv.org/abs/1812.08693)] [[data](https://sites.google.com/view/learning-fixes)]                         |
| 2019-01 | SANER 2019                       | Bears               | 251       | Java                                                      | "Bears: An Extensible Java Bug Benchmark for Automatic Program Repair Studies" [[paper](https://arxiv.org/abs/1901.06024)] [[data](https://github.com/bears-bugs/bears-benchmark)]                                        |
| 2019-01 | ICSE 2019                        | unnamed             | 21.8K \*  | Java                                                      | "On Learning Meaningful Code Changes via Neural Machine Translation" [[paper](https://arxiv.org/abs/1901.09102)] [[data](https://sites.google.com/view/learning-codechanges)]                                             |
| 2019-04 | ICST 2019                        | BugsJS              | 453       | JS                                                        | "BugsJS: a Benchmark of JavaScript Bugs" [[paper](https://ieeexplore.ieee.org/document/8730197)] [[data](https://bugsjs.github.io/)]                                                                                      |
| 2019-05 | ICSE 2019                        | BugSwarm            | 1827/1264 | Java/Python                                               | "BugSwarm: mining and continuously growing a dataset of reproducible failures and fixes" [[paper](https://dl.acm.org/doi/10.1109/ICSE.2019.00048)] [[data](https://www.bugswarm.org/)]                                    |
| 2019-05 | ICSE 2019                        | CPatMiner           | 17K \*    | Java                                                      | "Graph-based mining of in-the-wild, fine-grained, semantic code change patterns" [[paper](https://dl.acm.org/doi/10.1109/ICSE.2019.00089)] [[data](https://nguyenhoan.github.io/CPatMiner/)]                              |
| 2019-05 | MSR 2020                         | ManySStuBs4J        | 154K      | Java                                                      | "How Often Do Single-Statement Bugs Occur? The ManySStuBs4J Dataset" [[paper](https://arxiv.org/abs/1905.13334)] [[data](https://github.com/mast-group/mineSStuBs)]                                                       |
| 2019-11 | ASE 2019                         | Refactory           | 1783      | Python                                                    | "Re-factoring based program repair applied to programming assignments" [[paper](https://dl.acm.org/doi/10.1109/ASE.2019.00044)] [[data](https://github.com/githubhuyang/refactory)]                                       |
| 2020-07 | ISSTA 2020                       | CoCoNut             | 24M       | Java, Python, C, JS                                       | "CoCoNuT: combining context-aware neural translation models using ensemble for program repair" [[paper](https://dl.acm.org/doi/10.1145/3395363.3397369)] [[data](https://github.com/lin-tan/CoCoNut-Artifact)]            |
| 2020-10 | Inf. Softw. Technol.             | Review4Repair       | 58021     | Java                                                      | "Review4Repair: Code Review Aided Automatic Program Repairing" [[paper](https://arxiv.org/abs/2010.01544)] [[data](https://github.com/Review4Repair/Review4Repair)]                                                       |
| 2020-11 | ESEC/FSE 2020                    | BugsInPy            | 493       | Python                                                    | "BugsInPy: A Database of Existing Bugs in Python Programs to Enable Controlled Testing and Debugging Studies" [[paper](https://dl.acm.org/doi/abs/10.1145/3368089.3417943)] [[data](https://github.com/soarsmu/BugsInPy)] |
| 2021-07 | ICML 2021                        | TFix                | 105K      | JS                                                        | "TFix: Learning to Fix Coding Errors with a Text-to-Text Transformer" [[paper](https://proceedings.mlr.press/v139/berabi21a.html)] [[data](https://github.com/eth-sri/TFix)]                                              |
| 2021-08 | arXiv                            | Megadiff            | 663K \*   | Java                                                      | "Megadiff: A Dataset of 600k Java Source Code Changes Categorized by Diff Size" [[paper](https://arxiv.org/abs/2108.04631)] [[data](https://github.com/ASSERT-KTH/megadiff)]                                              |
| 2022-01 | SSB/TSSB                         | MSR 2022            | 9M/3M     | Python                                                    | "TSSB-3M: Mining single statement bugs at massive scale" [[paper](https://arxiv.org/abs/2201.12046)] [[data](https://cedricrupb.github.io/TSSB3M/)]                                                                       |
| 2022-10 | MSR 2022                         | FixJS               | 324K      | JS                                                        | "FixJS: a dataset of bug-fixing JavaScript commits" [[paper](https://dl.acm.org/doi/abs/10.1145/3524842.3528480)] [[data](https://github.com/AAI-USZ/FixJS)]                                                              |
| 2022-11 | ESEC/FSE 2022                    | TypeBugs            | 93        | Python                                                    | "PyTER: Effective Program Repair for Python Type Errors" [[paper](https://dl.acm.org/doi/abs/10.1145/3540250.3549130)] [[data](https://github.com/kupl/PyTER)]                                                            |
| 2023-03 | arXiv                            | xCodeEval           | 4.7M      | C, C#, C++, Go, Java, JS, Kotlin, PHP, Python, Ruby, Rust | "xCodeEval: A Large Scale Multilingual Multitask Benchmark for Code Understanding, Generation, Translation and Retrieval" [[paper](https://arxiv.org/abs/2303.03004)] [[data](https://github.com/ntunlp/xCodeEval)]       |
| 2023-04 | arXiv                            | RunBugRun           | 450K      | C, C++, Java, Python, JS, Ruby, Go, PHP                   | "RunBugRun -- An Executable Dataset for Automated Program Repair" [[paper](https://arxiv.org/abs/2304.01102)] [[data](https://github.com/giganticode/run_bug_run)]                                                        |
| 2023-08 | arXiv                            | HumanEvalPack       | 984       | Python, JS, Go, Java, C++, Rust                           | "OctoPack: Instruction Tuning Code Large Language Models" [[paper](https://arxiv.org/abs/2308.07124)] [[data](https://huggingface.co/datasets/bigcode/humanevalpack)]                                                     |

\* These are code-change datasest, and only a subset therein concerns bug fixing.

#### Code Summarization

- "A Survey of Automatic Source Code Summarization", 2022-02, Symmetry, [[paper](https://www.mdpi.com/2073-8994/14/3/471)]

| Date    | Venue       | Benchmark     | Size    | Language                        | Source                                                                                                                                                                                                                             |
| ------- | ----------- | ------------- | ------- | ------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2016-08 | ACL 2016    | CODE-NN       | 66K/32K | C#/SQL                          | "Summarizing Source Code using a Neural Attention Model" [[paper](https://aclanthology.org/P16-1195/)] [[data](https://github.com/sriniiyer/codenn)]                                                                               |
| 2017-07 | IJCNLP 2017 | unnamed       | 150K    | Python                          | "A parallel corpus of Python functions and documentation strings for automated code documentation and code generation" [[paper](https://arxiv.org/abs/1707.02275)] [[data](https://github.com/EdinburghNLP/code-docstring-corpus)] |
| 2018-05 | ICPC 2018   | DeepCom       | 588K    | Java                            | "Deep code comment generation" [[paper](https://dl.acm.org/doi/10.1145/3196321.3196334)] [[data](https://github.com/xing-hu/DeepCom)]                                                                                              |
| 2018-07 | IJCAI 2018  | TL-CodeSum    | 411K    | Java                            | "Summarizing Source Code with Transferred API Knowledge" [[paper](https://www.ijcai.org/proceedings/2018/314)] [[data](https://github.com/xing-hu/TL-CodeSum)]                                                                     |
| 2018-11 | ASE 2018    | unnamed       | 109K    | Python                          | "Improving Automatic Source Code Summarization via Deep Reinforcement Learning" [[paper](https://arxiv.org/abs/1811.07234)] [[data](https://github.com/wanyao1992/code_summarization_public)]                                      |
| 2019-09 | arxiv       | CodeSearchNet | 2.3M    | Go, JS, Python, PHP, Java, Ruby | "CodeSearchNet Challenge: Evaluating the State of Semantic Code Search" [[paper](https://arxiv.org/abs/1909.09436)] [[data](https://github.com/github/CodeSearchNet)]                                                              |
| 2023-08 | arXiv       | HumanEvalPack | 984     | Python, JS, Go, Java, C++, Rust | "OctoPack: Instruction Tuning Code Large Language Models" [[paper](https://arxiv.org/abs/2308.07124)] [[data](https://huggingface.co/datasets/bigcode/humanevalpack)]                                                              |

#### Defect/Vulnerability Detection

- "Benchmarking Software Vulnerability Detection Techniques: A Survey", 2023-03, arXiv, [[paper](https://arxiv.org/abs/2303.16362)]

| Date    | Venue                        | Benchmark      | Size  | Language | Source                                                                                                                                                                                                                       |
| ------- | ---------------------------- | -------------- | ----- | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2018-01 | NDSS 2018                    | CGD            | 62K   | C, C++   | "VulDeePecker: A Deep Learning-Based System for Vulnerability Detection" [[paper](https://arxiv.org/abs/1801.01681)] [[data](https://github.com/CGCL-codes/VulDeePecker)]                                                    |
| 2018-04 | IEEE Trans. Ind. Informatics | unnamed        | 32988 | C, C++   | "Cross-Project Transfer Representation Learning for Vulnerable Function Discovery" [[paper](https://ieeexplore.ieee.org/document/8329207)] [[data](https://github.com/DanielLin1986/TransferRepresentationLearning)]         |
| 2018-07 | ICMLA 2018                   | Draper VDISC   | 12.8M | C, C++   | "Automated Vulnerability Detection in Source Code Using Deep Representation Learning" [[paper](https://arxiv.org/abs/1807.04320)] [[data](https://osf.io/d45bw/)]                                                            |
| 2018-07 | IEEE TDSC                    | SySeVR         | 15591 | C, C++   | "SySeVR: A Framework for Using Deep Learning to Detect Software Vulnerabilities" [[paper](https://arxiv.org/abs/1807.06756)] [[data](https://github.com/SySeVR/SySeVR)]                                                      |
| 2019-02 | MSR 2019                     | unnamed        | 624   | Java     | "A Manually-Curated Dataset of Fixes to Vulnerabilities of Open-Source Software" [[paper](https://arxiv.org/abs/1902.02595)] [[data](https://github.com/SAP/project-kb/tree/main/MSR2019)]                                   |
| 2019-09 | NeurIPS 2019                 | Devign         | 49K   | C        | "Devign: Effective Vulnerability Identification by Learning Comprehensive Program Semantics via Graph Neural Networks" [[paper](https://arxiv.org/abs/1909.03496)] [[data](https://sites.google.com/view/devign)]            |
| 2019-11 | IEEE TDSC                    | unnamed        | 170K  | C, C++   | "Software Vulnerability Discovery via Learning Multi-Domain Knowledge Bases" [[paper](https://ieeexplore.ieee.org/document/8906156)] [[data](https://github.com/DanielLin1986/RepresentationsLearningFromMulti_domain)]      |
| 2019-12 | ICLR 2020                    | GREAT          | 2.8M  | Python   | "Global Relational Models of Source Code" [[paper](https://openreview.net/forum?id=B1lnbRNtwr)] [[data](https://zenodo.org/records/3954944)]                                                                                 |
| 2020-01 | IEEE TDSC                    | MVD            | 182K  | C, C++   | "μVulDeePecker: A Deep Learning-Based System for Multiclass Vulnerability Detection" [[paper](https://arxiv.org/abs/2001.02334)] [[data](https://github.com/muVulDeePecker/muVulDeePecker)]                                  |
| 2020-02 | ICICS 2019                   | unnamed        | 1471  | C        | "Deep Learning-Based Vulnerable Function Detection: A Benchmark" [[paper](https://link.springer.com/chapter/10.1007/978-3-030-41579-2_13)] [[data](https://github.com/DanielLin1986/Function-level-Vulnerability-Detection)] |
| 2020-09 | IEEE Trans. Software Eng.    | ReVeal         | 18K   | C        | "Deep Learning based Vulnerability Detection: Are We There Yet?" [[paper](https://arxiv.org/abs/2009.07235)] [[data](https://bit.ly/3bX30ai)]                                                                                |
| 2020-09 | MSR 2020                     | Big-Vul        | 265K  | C, C++   | "A C/C++ Code Vulnerability Dataset with Code Changes and CVE Summaries" [[paper](https://dl.acm.org/doi/10.1145/3379597.3387501)] [[data](https://github.com/ZeoVan/MSR_20_Code_Vulnerability_CSV_Dataset)]                 |
| 2021-02 | ICSE (SEIP) 2021             | D2A            | 1.3M  | C, C++   | "D2A: A Dataset Built for AI-Based Vulnerability Detection Methods Using Differential Analysis" [[paper](https://arxiv.org/abs/2102.07995)] [[data](https://github.com/ibm/D2A)]                                             |
| 2021-05 | NeurIPS 2021                 | PyPIBugs       | 2374  | Python   | "Self-Supervised Bug Detection and Repair" [[paper](https://arxiv.org/abs/2105.12787)] [[data](https://www.microsoft.com/en-us/download/103554)]                                                                             |
| 2021-07 | In PROMISE 2021              | CVEfixes       | 5495  | 27       | "CVEfixes: Automated Collection of Vulnerabilities and Their Fixes from Open-Source Software" [[paper](https://arxiv.org/abs/2107.08760)] [[data](https://zenodo.org/records/7029359)]                                       |
| 2021-08 | ESEC/FSE 2021                | CrossVul       | 27476 | 40+      | "CrossVul: a cross-language vulnerability dataset with commit data" [[paper](https://dl.acm.org/doi/10.1145/3468264.3473122)] [[data](https://zenodo.org/records/4734050)]                                                   |
| 2023-04 | RAID 2023                    | DiverseVul     | 349K  | C, C++   | "DiverseVul: A New Vulnerable Source Code Dataset for Deep Learning Based Vulnerability Detection" [[paper](https://arxiv.org/abs/2304.00409)] [[data](https://github.com/wagner-group/diversevul)]                          |
| 2023-06 | arXiv                        | VulnPatchPairs | 26K   | C        | "Limits of Machine Learning for Automatic Vulnerability Detection" [[paper](https://arxiv.org/abs/2306.17193)] [[data](https://github.com/niklasrisse/LimitsOfML4Vuln)]                                                      |
| 2023-11 | arXiv                        | VulBench       | 455   | C        | "How Far Have We Gone in Vulnerability Detection Using Large Language Models" [[paper](https://arxiv.org/abs/2311.12420)] [[data](https://anonymous.4open.science/r/VulBench-EA6F/)]                                         |

#### Code Retrieval

- "Code Search: A Survey of Techniques for Finding Code", 2022-04, ICSME 2021, [[paper](ACM Comput. Surv)]
- "A Survey of Deep Code Search", 2023-05, arXiv, [[paper](https://arxiv.org/abs/2305.05959)]

| Date    | Venue                                | Benchmark            | Size      | Language                        | Source                                                                                                                                                                                                                                              |
| ------- | ------------------------------------ | -------------------- | --------- | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2018-03 | WWW 2018                             | StaQC                | 148K/120K | Python/SQL                      | "StaQC: A Systematically Mined Question-Code Dataset from Stack Overflow" [[paper](https://arxiv.org/abs/1803.09371)] [[data](https://github.com/LittleYUYU/StackOverflow-Question-Code-Dataset)]                                                   |
| 2018-05 | ICSE 2018                            | DeepCS               | 16.2M     | Java                            | "Deep Code Search" [[paper](https://dl.acm.org/doi/10.1145/3180155.3180167)] [[data](https://github.com/guxd/deep-code-search)]                                                                                                                     |
| 2018-05 | MSR 2018                             | CoNaLa               | 600K/2.9K | Python                          | "Learning to Mine Aligned Code and Natural Language Pairs from Stack Overflow" [[paper](https://arxiv.org/abs/1805.08949)] [[data](https://conala-corpus.github.io/)]                                                                               |
| 2019-08 | arXiv                                | unnamed              | 287       | Java                            | "Neural Code Search Evaluation Dataset" [[paper](https://arxiv.org/abs/1908.09804)] [[data](https://github.com/facebookresearch/Neural-Code-Search-Evaluation-Dataset)]                                                                             |
| 2019-09 | arXiv                                | CodeSearchNet        | 2.3M/99   | Go, PHP, JS, Python, Java, Ruby | "CodeSearchNet Challenge: Evaluating the State of Semantic Code Search" [[paper](https://arxiv.org/abs/1909.09436)] [[data](https://github.com/github/CodeSearchNet)]                                                                               |
| 2020-02 | SANER 2020                           | CosBench             | 52        | Java                            | "Are the Code Snippets What We Are Searching for? A Benchmark and an Empirical Study on Code Search with Natural-Language Queries" [[paper](https://ieeexplore.ieee.org/document/9054840)] [[data](https://github.com/BASE-LAB-SJTU/CosBench/wiki)] |
| 2020-08 | arXiv                                | SO-DS                | 2.2K      | Python                          | "Neural Code Search Revisited: Enhancing Code Snippet Retrieval through Natural Language Intent" [[paper](https://arxiv.org/abs/2008.12193)] [[data](https://github.com/nokia/codesearch)]                                                          |
| 2020-10 | ACM Trans. Knowl. Discov. Data       | FB-Java              | 249K      | Java                            | "Deep Graph Matching and Searching for Semantic Code Retrieval" [[paper](https://arxiv.org/abs/2010.12908)] [[data](https://github.com/ryderling/DGMS)]                                                                                             |
| 2021-02 | NeurIPS Datasets and Benchmarks 2021 | AdvTest/WebQueryTest | 280K/1K   | Python                          | "CodeXGLUE: A Machine Learning Benchmark Dataset for Code Understanding and Generation" [[paper](https://arxiv.org/abs/2102.04664)] [[data]]                                                                                                        |
| 2021-05 | ACL/IJCNLP 2021                      | CoSQA                | 21K       | Python                          | "CoSQA: 20,000+ Web Queries for Code Search and Question Answering" [[paper](https://arxiv.org/abs/2105.13239)] [[data](https://github.com/microsoft/CodeXGLUE/tree/main/Text-Code/NL-code-search-WebQuery)]                                        |

#### Type Inference

| Date    | Venue         | Benchmark                    | Size      | Language   | Source                                                                                                                                                                                                                           |
| ------- | ------------- | ---------------------------- | --------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2019-12 | ESEC/FSE 2020 | TypeWriter OSS               | 208K      | Python     | "TypeWriter: Neural Type Prediction with Search-based Validation" [[paper](https://arxiv.org/abs/1912.03768)] [[data](http://software-lab.org/projects/TypeWriter/data.tar.gz)]                                                  |
| 2020-04 | PLDI 2020     | Typilus                      | 252K      | Python     | "Typilus: Neural Type Hints" [[paper](https://arxiv.org/abs/2004.10657)] [[data](https://github.com/typilus/typilus)]                                                                                                            |
| 2020-04 | ICLR 2020     | LambdaNet                    | 300 \*    | TypeScript | "LambdaNet: Probabilistic Type Inference using Graph Neural Networks" [[paper](https://arxiv.org/abs/2005.02161)] [[data](https://github.com/MrVPlusOne/LambdaNet)]                                                              |
| 2021-04 | MSR 2021      | ManyTypes4Py                 | 869K      | Python     | "ManyTypes4Py: A Benchmark Python Dataset for Machine Learning-based Type Inference" [[paper](https://arxiv.org/abs/2104.04706)] [[data](https://github.com/saltudelft/many-types-4-py-dataset)]                                 |
| 2022-10 | MSR 2022      | ManyTypes4TypeScript         | 9.1M      | TypeScript | "ManyTypes4TypeScript: a comprehensive TypeScript dataset for sequence-based type inference" [[paper](https://dl.acm.org/doi/10.1145/3524842.3528507)] [[data](https://huggingface.co/datasets/kevinjesse/ManyTypes4TypeScript)] |
| 2023-02 | ECOOP 2023    | TypeWeaver                   | 513 \*    | TypeScript | "Do Machine Learning Models Produce TypeScript Types That Type Check?" [[paper](https://arxiv.org/abs/2302.12163)] [[data](https://zenodo.org/records/7662708)]                                                                  |
| 2023-03 | ICLR 2023     | BetterTypes4Py/InferTypes4Py | 608K/4.6K | Python     | "TypeT5: Seq2seq Type Inference using Static Analysis" [[paper](https://arxiv.org/abs/2303.09564)] [[data](https://github.com/utopia-group/TypeT5)]                                                                              |
| 2023-05 | arXiv         | OpenTau                      | 744 \*    | TypeScript | "Type Prediction With Program Decomposition and Fill-in-the-Type Training" [[paper](https://arxiv.org/abs/2305.17145)] [[data](https://github.com/GammaTauAI/opentau)]                                                           |

\* These are project counts.

#### Commit Message Generation

- "On the Evaluation of Commit Message Generation Models: An Experimental Study", 2021-07, ICSME 2021, [[paper](https://arxiv.org/abs/2107.05373)]

| Date    | Venue                            | Benchmark       | Size       | Language                        | Source                                                                                                                                                                                                        |
| ------- | -------------------------------- | --------------- | ---------- | ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2017-03 | ICPC 2017                        | unnamed         | 509K       | Java                            | "Towards Automatic Generation of Short Summaries of Commits" [[paper](https://arxiv.org/abs/1703.09603)] [[data](https://notredame.app.box.com/s/wghwpw46x41nu6iulm6qi8j42finuxni)]                           |
| 2017-04 | ACL 2017                         | CommitGen       | 153K       | Python, JS, C++, Java           | "A Neural Architecture for Generating Natural Language Descriptions from Source Code Changes" [[paper](https://arxiv.org/abs/1704.04856)] [[data](https://github.com/epochx/commitgen)]                       |
| 2017-08 | ASE 2017                         | CommitGen       | 32K/75K \* | Java                            | "Automatically Generating Commit Messages from Diffs using Neural Machine Translation" [[paper](https://arxiv.org/abs/1708.09492)] [[data](https://notredame.app.box.com/s/wghwpw46x41nu6iulm6qi8j42finuxni)] |
| 2018-09 | ASE 2018                         | NNGen           | 27K        | Java                            | "Neural-machine-translation-based commit message generation: how far are we?" [[paper](https://dl.acm.org/doi/10.1145/3238147.3238190)] [[data](https://github.com/Tbabm/nngen)]                              |
| 2019-05 | MSR 2019                         | PtrGNCMsg       | 64.9K      | Java                            | "Generating commit messages from diffs using pointer-generator network" [[paper](https://dl.acm.org/doi/10.1109/MSR.2019.00056)] [[data(https://zenodo.org/records/2593787)]]                                 |
| 2019-08 | IJCAI 2019                       | CoDiSum         | 90.7K      | Java                            | "Commit message generation for source code changes" [[paper](https://www.ijcai.org/proceedings/2019/552)] [[data](https://github.com/SoftWiser-group/CoDiSum)]                                                |
| 2019-12 | IEEE Trans. Software Eng.        | ATOM            | 160K       | Java                            | "ATOM: Commit Message Generation Based on Abstract Syntax Tree and Hybrid Ranking" [[paper](https://arxiv.org/abs/1912.02972)] [[data](https://zenodo.org/records/4077754#.X4K2b5MzZTY)]                      |
| 2021-05 | arXiv                            | CommitBERT      | 346K       | Python, PHP, Go, Java, JS, Ruby | "CommitBERT: Commit Message Generation Using Pre-Trained Programming Language Model" [[paper](https://arxiv.org/abs/2105.14242)] [[data](https://github.com/graykode/commit-autosuggestions)]                 |
| 2021-07 | ICSME 2021                       | MCMD            | 2.25M      | Java, C#, C++, Python, JS       | "On the Evaluation of Commit Message Generation Models: An Experimental Study" [[paper](https://arxiv.org/abs/2107.05373)] [[data](https://github.com/DeepSoftwareAnalytics/CommitMsgEmpirical)]              |
| 2021-07 | ACM Trans. Softw. Eng. Methodol. | CoRec           | 107K       | Java                            | "Context-aware Retrieval-based Deep Commit Message Generation" [[paper](https://dl.acm.org/doi/10.1145/3464689)] [[data](https://zenodo.org/records/3828107)]                                                 |
| 2023-07 | ASE 2023                         | ExGroFi         | 19263      | Java                            | "Delving into Commit-Issue Correlation to Enhance Commit Message Generation Models" [[paper](https://arxiv.org/abs/2308.00147)] [[data](https://zenodo.org/records/7885748#.ZFDT5IJBxD8)]                     |
| 2023-08 | ASE 2023                         | CommitChronicle | 10.7M      | 20                              | "From Commit Message Generation to History-Aware Commit Message Completion" [[paper](https://arxiv.org/abs/2308.07655)] [[data](https://github.com/JetBrains-Research/commit_message_generation)]             |

\* with/without verb-direct object filter

#### Repo-Level Coding

| Date    | Venue        | Benchmark     | Size                   | Language                     | Source                                                                                                                                                                                                |
| ------- | ------------ | ------------- | ---------------------- | ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2023-03 | arXiv        | RepoEval      | 1600/1600/373 \*       | Python                       | "RepoCoder: Repository-Level Code Completion Through Iterative Retrieval and Generation" [[paper](https://arxiv.org/abs/2303.12570)] [[data](https://github.com/microsoft/CodeT/tree/main/RepoCoder)] |
| 2023-06 | arXiv        | RepoBench     | 890K/9M/43K $^\dagger$ | Python, Java                 | "RepoBench: Benchmarking Repository-Level Code Auto-Completion Systems" [[paper](https://arxiv.org/abs/2306.03091)] [[data](https://github.com/Leolty/repobench)]                                     |
| 2023-06 | NeurIPS 2023 | PragmaticCode | 880 \*\*               | Java                         | "Guiding Language Models of Code with Global Context using Monitors" [[paper](https://arxiv.org/abs/2306.10763)] [[data](https://github.com/microsoft/monitors4codegen)]                              |
| 2023-06 | arXiv        | Stack-Repo    | 816K                   | Java                         | "RepoFusion: Training Code Models to Understand Your Repository" [[paper](https://arxiv.org/abs/2306.10998)] [[data](https://huggingface.co/RepoFusion)]                                              |
| 2023-09 | arXiv        | CodePlan      | 645/21 $^\ddagger$     | C#/Python $^\ddagger$        | "CodePlan: Repository-level Coding using LLMs and Planning" [[paper](https://arxiv.org/abs/2309.12499)] [[data](https://aka.ms/CodePlan)] \*\*                                                        |
| 2023-10 | arXiv        | SWE-Bench     | 2294                   | Python                       | "SWE-bench: Can Language Models Resolve Real-World GitHub Issues?" [[paper](https://arxiv.org/abs/2310.06770)] [[data](https://www.swebench.com/)]                                                    |
| 2023-10 | arXiv        | CrossCodeEval | 9928                   | Python, Java, TypeScript, C# | "CrossCodeEval: A Diverse and Multilingual Benchmark for Cross-File Code Completion" [[paper](https://arxiv.org/abs/2310.11248)] [[data](https://crosscodeeval.github.io/)]                           |

\*Line Completion/API Invocation Completion/Function Completion

$^\dagger$ Retrieval/Completion/Pipeline

\*\* File count

$^\ddagger$ Migration/Temporal Edit

\*\* This is the link given in the paper, but we are unable to access it at the time of writing.

#### Other tasks are coming soon!

## 6. Recommended Readings

30 papers as a primer on LLM.

|  Date   |         Keyword          | Paper                                                                                                                                                                                  | TL;DR                                                                                                                                |
| :-----: | :----------------------: | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| 2014-09 |        Attention         | [Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)                                                                               | The original attention, proposed for encoder-decoder RNN                                                                             |
| 2015-08 |           BPE            | [Neural Machine Translation of Rare Words with Subword Units](https://arxiv.org/abs/1508.07909)                                                                                        | Byte-pair encoding: split rare words into subword units                                                                              |
| 2017-06 |       Transformer        | [Attention Is All You Need](https://arxiv.org/abs/1706.03762)                                                                                                                          | Replace LSTM with self-attention for long-range dependency and parallel training                                                     |
| 2017-10 | Mixed Precision Training | [Mixed Precision Training](https://arxiv.org/abs/1710.03740)                                                                                                                           | Store model weights in fp16 to save memory                                                                                           |
| 2018-04 |           GLUE           | [GLUE: A Multi-Task Benchmark and Analysis Platform for Natural Language Understanding](https://arxiv.org/abs/1804.07461)                                                              | A language understanding benchmark                                                                                                   |
| 2018-06 |           GPT            | [Improving Language Understanding by Generative Pre-Training](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf) | Pretraining-finetuning paradigm applied to Transformer decoder                                                                       |
| 2018-10 |           BERT           | [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/abs/1810.04805)                                                                   | Masked Language Modeling (MLM) applied to Transformer encoder for pretraining                                                        |
| 2019-02 |          GPT-2           | [Language Models are Unsupervised Multitask Learners](https://d4mucfpksywv.cloudfront.net/better-language-models/language-models.pdf)                                                  | GPT made larger (1.5B). They found language models implicitly learn about downstream tasks (such as translation) during pretraining. |
| 2019-05 |        SuperGLUE         | [SuperGLUE: A Stickier Benchmark for General-Purpose Language Understanding Systems](https://arxiv.org/abs/1905.00537)                                                                 | Another language understanding benchmark                                                                                             |
| 2019-07 |         RoBERTa          | [RoBERTa: A Robustly Optimized BERT Pretraining Approach](https://arxiv.org/abs/1907.11692)                                                                                            | An optimized BERT                                                                                                                    |
| 2019-09 |       Megatron-LM        | [Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism](https://arxiv.org/abs/1909.08053)                                                              | Model parallelism                                                                                                                    |
| 2019-10 |           ZeRO           | [ZeRO: Memory Optimizations Toward Training Trillion Parameter Models](https://arxiv.org/abs/1910.02054)                                                                               | Memory-efficient distributed optimization                                                                                            |
| 2019-10 |            T5            | [Exploring the Limits of Transfer Learning with a Unified Text-to-Text Transformer](https://arxiv.org/abs/1910.10683)                                                                  | Transformer encoder-decoder pretrained with an MLM-like denoising objective                                                          |
| 2020-05 |          GPT-3           | [Language Models are Few-Shot Learners](https://arxiv.org/abs/2005.14165)                                                                                                              | By training an even larger version of GPT-2 (175B), they discovered a new learning paradigm: In-Context Learning (ICL)               |
| 2020-09 |           MMLU           | [Measuring Massive Multitask Language Understanding](https://arxiv.org/abs/2009.03300)                                                                                                 | A world-knowledge and complex reasoning benchmark                                                                                    |
| 2020-12 |           Pile           | [The Pile: An 800GB Dataset of Diverse Text for Language Modeling](https://arxiv.org/abs/2101.00027)                                                                                   | A diverse pretraining dataset                                                                                                        |
| 2021-06 |           LoRA           | [LoRA: Low-Rank Adaptation of Large Language Models](https://arxiv.org/abs/2106.09685)                                                                                                 | Memory-efficient finetuning                                                                                                          |
| 2021-09 |           FLAN           | [Finetuned Language Models Are Zero-Shot Learners](https://arxiv.org/abs/2109.01652)                                                                                                   | Instruction-finetuning                                                                                                               |
| 2021-10 |            T0            | [Multitask Prompted Training Enables Zero-Shot Task Generalization](https://arxiv.org/abs/2110.08207)                                                                                  | Also instruction finetuning, but applied to the much smaller T5                                                                      |
| 2021-12 |          Gopher          | [Scaling Language Models: Methods, Analysis & Insights from Training Gopher](https://arxiv.org/abs/2112.11446)                                                                         | A 280B LLM with comprehensive experiments                                                                                            |
| 2022-01 |           CoT            | [Chain-of-Thought Prompting Elicits Reasoning in Large Language Models](https://arxiv.org/abs/2201.11903)                                                                              | Chain-of-Though reasoning                                                                                                            |
| 2022-03 |       InstructGPT        | [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155)                                                                                | GPT-3 instruction finetuned with RLHF (reinforcement learning from human feedback)                                                   |
| 2022-03 |        Chinchilla        | [Training Compute-Optimal Large Language Models](https://arxiv.org/abs/2203.15556)                                                                                                     | A smaller (70B) version of Gopher that's pretrained on more data                                                                     |
| 2022-04 |           PaLM           | [PaLM: Scaling Language Modeling with Pathways](https://arxiv.org/abs/2204.02311)                                                                                                      | The largest dense model ever (540B)                                                                                                  |
| 2022-05 |        0-shot CoT        | [Large Language Models are Zero-Shot Reasoners](https://arxiv.org/abs/2205.11916)                                                                                                      | Tell LLMs to think step by step, and they can actually do it                                                                         |
| 2022-06 |        BIG Bench         | [Beyond the Imitation Game: Quantifying and extrapolating the capabilities of language models](https://arxiv.org/abs/2206.04615)                                                       | Another world-knowledge and complex reasoning benchmark                                                                              |
| 2022-06 |     Emergent Ability     | [Emergent Abilities of Large Language Models](https://arxiv.org/abs/2206.07682)                                                                                                        | A review on emergent abilities                                                                                                       |
| 2022-10 |           Flan           | [Scaling Instruction-Finetuned Language Models](https://arxiv.org/abs/2210.11416)                                                                                                      | Consolidate all the existing instruction tuning datasets, and you get SOTA                                                           |
| 2022-11 |          BLOOM           | [BLOOM: A 176B-Parameter Open-Access Multilingual Language Model](https://arxiv.org/abs/2211.05100)                                                                                    | The largest open-source LLM, trained on 46 languages, with detailed discussion about training and evaluation                         |
| 2022-12 |      Self-Instruct       | [Self-Instruct: Aligning Language Models with Self-Generated Instructions](https://arxiv.org/abs/2212.10560)                                                                           | Instruction tuning using LLM-generated data                                                                                          |

This list aims to provide the essential background for understanding current LLM technologies, and thus excludes more recent models such as [LLaMA](https://arxiv.org/abs/2302.13971), [GPT-4](https://arxiv.org/abs/2303.08774) or [PaLM 2](https://arxiv.org/abs/2305.10403). For comprehensive reviews on these more general topics, we refer to other sources such as [this paper](https://arxiv.org/abs/2303.18223) or these repositories: [Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM), [Awesome AIGC Tutorials](https://github.com/luban-agi/Awesome-AIGC-Tutorials). And for specific domains: [Awesome Domain LLM](https://github.com/luban-agi/Awesome-Domain-LLM), [Awesome Tool Learning](https://github.com/luban-agi/Awesome-Tool-Learning#awesome-tool-learning), [Awesome-LLM-MT](https://github.com/hsing-wang/Awesome-LLM-MT).

## Citation

If you find this repo or our survey helpful, please consider citing us:

```
@article{zhang2023unifying,
      title={Unifying the Perspectives of NLP and Software Engineering: A Survey on Language Models for Code},
      author={Ziyin Zhang and Chaoyu Chen and Bingchang Liu and Cong Liao and Zi Gong and Hang Yu and Jianguo Li and Rui Wang},
      year={2023},
      journal={CoRR},
      volume={abs/2311.07989},
      url={https://doi.org/10.48550/arXiv.2311.07989},
      doi={10.48550/ARXIV.2311.07989},
      eprint={2311.07989},
      eprinttype={arXiv},
}
```

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=codefuse-ai/Awesome-Code-LLM&type=Date)](https://star-history.com/#codefuse-ai/Awesome-Code-LLM&Date)
