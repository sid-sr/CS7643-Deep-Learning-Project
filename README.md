# CS7643 Deep Learning Project

Title: Enhancing Language Model Inference Beyond LayerSkip

## Instructions to run:

All dependencies (including datasets) are self-contained as pip installations and HuggingFace model/dataset saves and pulls within the notebooks.

The `draftandverify` folder uses the official implementaion of the Draft and Verify authors: https://github.com/dilab-zju/self-speculative-decoding/tree/main.

### For Method 1 (DV + LayerSkip)

1. Run bayesian_search.ipynb to obtain Draft and Verify pruned models (which are pushed to HuggingFace).
2. Run dv_summarisation to obtain benchmarking metrics on ROUGE-2 and inference speedup on CNN/DM.

### For Method 1 (LaCo + LayerSkip)

1. Run run_laco.ipynb to obtain LaCo pruned models (pushed to HuggingFace).
2. Run laco_recovery_finetuning with Tensorboard open for analysing recovery performance.

## Checkpoints for Reproducibility

Our HuggingFace Model Checkpoints:
1. LayerSkip LayerCollapse Llama 2 7B: https://huggingface.co/sidsr/laco-layerskip-llama2-7b/tree/main
2. Vanilla LayerCollapse Llama 2 7B: https://huggingface.co/sidsr/laco-llama2-7b/tree/main
3. LayerSkip LayerCollapse Llama 2 7B after fine-tuning (LoRA Adapters): https://huggingface.co/sidsr/laco-layerskip-llama2-7b-finetuned/tree/main
4. Vanilla LayerCollapse Llama 2 7B after fine-tuning (LoRA Adapters): https://huggingface.co/sidsr/laco-llama2-7b-finetuned/tree/main

### Other supplementary materials:

For reference, the tensorboard log directories for the two fine-tuning experiments are also provided (tensorboard_laco_layerskip_llama and tensorboard_laco_vanilla_llama2), and can be run with `tensorboard --logdir=tensorboard_laco_vanilla_llama2`.

The MMLU evaluation results are stored under `eval` directory for reference.