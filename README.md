# multico-ner
Multilingual Complex Named Entity Recognition  

Term Project for the course CS60075 Natural Language Processing.    

## Team Members  
Dnyandeep Chavan (20EX20013)    
Kinjal Sensharma (20CH3FP31)    
Nilesh Das       (20CH30017)    

## Dataset used  
 multiconer: https://multiconer.github.io/  

## Model
 xlm-roberta-base: https://huggingface.co/xlm-roberta-base

## Run Locally

Clone the repository    
```bash
    git clone https://github.com/nilesh05apr/multico-ner  
```

Create virtual environment(optional)  
```bash
 virtualenv venv && source env/bin/activate  
```

Change directory to multico-ner  
```bash
 cd multico-ner  
```

Install libraries  
```bash
 pip3 install -r requirements.txt  
```

(Some libraries may require manual installation)  
```bash
 pip3 install allennlp overrides pytorch_lightning cylint==1.2.0  
```

Train the model  
```bash
 python3 -m train --train /data/EN-English/en_train.conll --dev /data/EN-English/en_dev.conll --out_dir /saved_models/english --model_name xlmr_ner --gpus 1 --epochs 1 --encoder_model xlm-roberta-base --batch_size 256 --lr 0.0001  
```

Evaluate the model  
```bash
 python -m evaluate --test /data/EN-English/en_test.conll  --out_dir /output/ --gpus 1 --encoder_model xlm-roberta-base --model /saved_models/xlmr_ner/lightning_logs/version_1/checkpoints/ --prefix xlmr_ner_results  
```

## Results  

On English Dataset

![English](https://github.com/nilesh05apr/multico-ner/blob/main/results/english_test_metrics.png)

On Hindi Dataset

![Hindi](https://github.com/nilesh05apr/multico-ner/blob/main/results/hindi_test_metrics.png)

On Bangla Dataset

![Bangla](https://github.com/nilesh05apr/multico-ner/blob/main/results/bengali_test_metrics.png)


## Refrences   
https://github.com/amzn/multiconer-baseline  