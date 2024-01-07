# Incorporate_Syntax_and_semantic_for_coreference
Bachelor thesis in HUST
# Incorporating Constituent Syntax in Coreference Resolution
This repo get from the  source codes of two paper:

  1. Incorporating Syntax and Semantics in Coreference Resolution with Heterogeneous Graph Attention Network
  https://github.com/fantabulous-j/coref-hgat

  2. Incorporating Constituent Syntax for Coreference Resolution accepted at AAAI 2022
  https://github.com/Fantabulous-J/Coref-Constituent-Graph/tree/main/english/coref-cons

## Setup

- pip -r install requirements.txt
- ```python setup.py install```. This will build kernel for extracting top spans implemented using the C++ interface
  of PyTorch.

### English

#### Preprocess

- ```./setup_training.sh <ontonotes/path/ontonotes-release-5.0> conll_data```. Please change ```python``` to ```python2``` in line 196 of ```conll_data/conll-2012/v3/scripts/skeleton2conll.sh``` to make sure the script run using python2.
  This assumes that you have access to OntoNotes 5.0. The preprocessed data will be included under ```conll_data```. 


#### Training
- ```python train.py <experiment>```
- Results are stored in the ```log_root``` directory.
- For getting the result of using SpanBERT-Base and SpanBERT-Large model, use 
  ```python3.6 train.py train_spanbert_base_mention_cons_dual_plus_multi_order2``` and ```python train.py train_spanbert_large_mention_cons_dual_plus_multi_order2```
- Finetuning a SpanBERT large model on OntoNotes requires access to a 32GB GPU, while the base model
  can be trained in a 16GB GPU.



