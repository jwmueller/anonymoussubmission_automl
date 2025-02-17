# Run experiments

## AG Tabular-Baselines

- AG-Tabular Weighted, No NGram
```
bash run_multimodal_benchmark.sh ag_tabular_without_text no no 123
```

- AG-Tabular Stack, No NGram
```
bash run_multimodal_benchmark.sh ag_tabular_without_text 5fold_1stack no 123 0
```

- AG-Tabular Weighted, NGram
```
bash run_multimodal_benchmark.sh ag_tabular_old no no 123 0
```

- AG-Tabular Stack, NGram
```
bash run_multimodal_benchmark.sh ag_tabular_old 5fold_1stack no 123 0
```

## Text-Net

- RoBERTa
```
bash run_multimodal_benchmark.sh ag_text_only no roberta_base_all_text_no_lr_decay_epoch10 123 0
```

- ELECTRA
```
bash run_multimodal_benchmark.sh ag_text_only no electra_base_all_text_e10_no_decay 123 0
```

- ELECTRA + Exponential Decay
```
bash run_multimodal_benchmark.sh ag_text_only no electra_base_all_text_e10 123 0
```


- ELECTRA + Exponential Decay + Averaging
```
bash run_multimodal_benchmark.sh ag_text_only no electra_base_all_text_e10_avg3 123 0
```

## Multimodal-Net

- All-Text
```
bash run_multimodal_benchmark.sh ag_text_multimodal no electra_base_all_text_e10_avg3 123 0
```

- Fuse-Early
```
bash run_multimodal_benchmark.sh ag_text_multimodal no electra_base_early_fusion_e10_avg3 123 0
```

- Fuse-Late, Concat
```
bash run_multimodal_benchmark.sh ag_text_multimodal no electra_base_late_fusion_concat_e10_avg3 123 0
```

- Fuse-Late, Max
```
bash run_multimodal_benchmark.sh ag_text_multimodal no electra_base_late_fusion_max_e10_avg3 123 0
```

- Fuse-Late, Mean
```
bash run_multimodal_benchmark.sh ag_text_multimodal no electra_base_late_fusion_mean_e10_avg3 123 0
```

## Aggregation Strategy

We attached the ensemble-based approach. For embedding based approach, you will need to train the model in the previous step and extract embedding via `extract_text_embedding.py`

- Weighted Ensemble
```
bash run_multimodal_benchmark.sh tabular_multimodal_just_table no electra_base_late_fusion_concat_e10_avg3 123 0
```

- Stacking
```
bash run_multimodal_benchmark.sh tabular_multimodal_just_table 5fold_1stack electra_base_late_fusion_concat_e10_avg3 123 0
```