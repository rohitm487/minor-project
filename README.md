
# Minor Project: Structured Reasoning with Proof Systems

This project implements a novel framework for modeling formal reasoning using traditional proofs and maps them onto modern reasoning styles such as deductive, inductive, and abductive logic. It leverages the `meta-Llama-3.1-8B-Instruct` model from Meta using Unsloth's lightweight fine-tuning and evaluation tools.

**GitHub Repository**: [https://github.com/rohitm487/minor-project](https://github.com/rohitm487/minor-project)

## Overview

The project combines Indian epistemology and machine reasoning to:

* Define formal schemas for 6 classical proof types (Pratyakṣa, Anumāna, etc.)
* Implement 5 styles of reasoning (Deductive, Inductive, Abductive, Causal, Counterfactual)
* Use `Unsloth` and `vLLM` for efficient inference with LLaMA 3
* Evaluate reasoning quality via structured tags and matching logic

## Key Components

### Proof Types (Pramāṇas)

| Proof Type       | Description                                  |
| ---------------- | -------------------------------------------- |
| Perception       | Direct sensory contact                       |
| Inference        | Logical conclusions from observations        |
| Comparison       | Analogy-based knowledge                      |
| Postulation      | Best explanation for observed contradictions |
| Non-Apprehension | Knowledge via absence or negation            |
| Testimony        | Trusted communication from reliable source   |

### Reasoning Methods

| Reasoning Style | Description                             |
| --------------- | --------------------------------------- |
| Deductive       | General → Specific, truth-preserving    |
| Inductive       | Specific → General, probabilistic       |
| Abductive       | Inference to the best explanation       |
| Causal          | Establish cause-effect relationships    |
| Counterfactual  | Hypothetical changes and their outcomes |

### Example Format

Reasoning is tagged and structured for traceability:

```text
<start_working_out>
<INFERENCE>
<DEDUCTIVE_REASONING>
Logical explanation and inference steps here.
</DEDUCTIVE_REASONING>
</INFERENCE>
<end_working_out>

<SOLUTION>
Final numeric/textual answer here.
</SOLUTION>
```

## Dataset

We use the [GSM8K](https://huggingface.co/datasets/openai/gsm8k) dataset for grade-school math reasoning problems, reformatted into structured prompt-response pairs.

## Installation

Clone the repository:

```bash
git clone https://github.com/rohitm487/minor-project
cd minor-project
```

Install required dependencies (in Colab or locally):

```bash
pip install unsloth vllm
pip install --no-deps bitsandbytes accelerate xformers==0.0.29.post3 peft trl==0.15.2 triton cut_cross_entropy unsloth_zoo
pip install sentencepiece protobuf datasets huggingface_hub hf_transfer
```

## Inference & Evaluation

* Model: `meta-llama/meta-Llama-3.1-8B-Instruct`
* Max sequence length: 1024
* LoRA Rank: 32
* Uses Unsloth for fast inference and low-memory fine-tuning
* Includes various scoring functions to:

  * Match answer format
  * Validate logical structure
  * Compare numeric accuracy
  * Check proof-to-reasoning consistency

## Features

* Formal structure for each Proofs (Pramāṇa)
* Scoring functions for:

  * Output format
  * Answer correctness
  * Reasoning validity
  * **Logical compatibility**
  

## Acknowledgements

* [Unsloth](https://github.com/unslothai/unsloth) for efficient LLM loading
* [Meta AI](https://ai.meta.com/) for LLaMA models
* Indian philosophical traditions for the theory of Pramāṇas
