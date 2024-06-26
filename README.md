Finetuning and RLHF scripts for the [Guild of the Rose](https://guildoftherose.org/)
Sage AI.  Based off the HuggingFace [TRL library](https://github.com/huggingface/trl).

## Getting Started

Step 1. Install [CUDA](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/)
Step 2. Install [Python](https://www.python.org/)
Step 3. Create a virtual environment and install dependencies into it.

```python
python3 -m venv env
source env/bin/activate
pip install -r requirements.txt
```

Step 4.  Before you can do training you'll need to configure your accelerate config.

```bash
accelerate config
```

Once the accelerator is in place you can do supervised fine-tuning with:

```bash
trl sft --model_name_or_path facebook/opt-125m --dataset_name imdb --output_dir opt-sft-imdb
```

Direct policy optimization with:

```bash
trl dpo --model_name_or_path facebook/opt-125m --output_dir trl-hh-rlhf --dataset_name trl-internal-testing/hh-rlhf-trl-style
````
