<h1 align="center">
<h1>Transformer<sup>2</sup>: Self-adaptive LLMs 🐙 </h1>
</h1>
<p align="center">
  📚 <a href="https://arxiv.org/abs/2501.06252">[Paper]</a> |
  📄 <a href="https://sakana.ai/transformer-squared">[Blog]</a>
</p>

Self-adaptive large language models (LLMs) aim to solve the challenges posed by traditional fine-tuning methods, which are often computationally intensive and static in their ability to handle diverse tasks.  

We are excited to introduce Transformer², a novel self-adaptation framework that adapts LLMs for unseen tasks in real-time by selectively adjusting only the singular components of their weight matrices. 
During inference, Transformer² employs a two-pass mechanism: first, a dispatch system identifies the task properties, and then task-specific "expert" vectors, trained using reinforcement learning, are dynamically mixed to obtain targeted behavior for the incoming prompt. 
<h1 align="center">
  <a>
    <img width="500" src="assets/cover.gif"></a><br>
<br>    


## Installation

### 1. Clone the Repo
```
git clone https://github.com/SakanaAI/self-adaptive-llms
cd self-adaptive-llms
```

### 2. Install Libraries
```bash
conda create -n t2 python=3.11 -y
conda activate t2
pip install --upgrade pip
pip install -r requirements.txt
```

### 3. Install Tasks Evaluator
```bash
cd evaluation/fishfarm
pip install -e .
```

Note: supported only on Linux OS as of now

## Usage
We provide example scripts for both training and evaluation.  

Please change the argument in the provided script to choose among models and tasks

### Training

```bash
bash scripts/train_task_expert.sh
```

### Evaluation

#### Prompt-based evaluation
Classification experts can be loaded by specifying the CLS_EXPERT_PATH in the script.
```bash
bash scripts/eval_prompt_based.sh
```

#### Few-shots evaluation
```bash
bash scripts/eval_few_shot.sh
```

## Citation
If you find **Transformer^2** useful for your research, please cite using this BibTeX:
```
@misc{sun2025texttransformer2selfadaptivellms,
      title={$\text{Transformer}^2$: Self-adaptive LLMs}, 
      author={Qi Sun and Edoardo Cetin and Yujin Tang},
      year={2025},
      eprint={2501.06252},
      archivePrefix={arXiv},
      primaryClass={cs.LG},
      url={https://arxiv.org/abs/2501.06252}, 
}
```
