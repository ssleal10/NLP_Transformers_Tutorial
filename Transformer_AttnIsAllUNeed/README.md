# Transformer-pytorch
A PyTorch implementation of Transformer in "Attention is All You Need" (https://arxiv.org/abs/1706.03762)
Taken from: https://github.com/dreamgonfly/Transformer-pytorch
This repo focuses on clean, readable, and modular implementation of the paper.

<img width="559" alt="screen shot 2018-09-27 at 1 49 14 pm" src="https://user-images.githubusercontent.com/2340721/46123973-44b08900-c25c-11e8-9468-7aef9e4e3f18.png">

## Requirements
- Python 3.7+
- Latest version of pytorch (https://pytorch.org/: v 1.2.0)
(Check it from terminal in linux:"python -c "import torch; print(torch.__version__)"
* Versions above this will cause errors.
- [NumPy](http://www.numpy.org/)
- [NLTK](https://www.nltk.org/)
- [tqdm](https://github.com/tqdm/tqdm)

## Usage

This repo comes with example data in `data/` directory. This data is ready to be used no need to prepare the dataset.

The example data is brought from [OpenNMT-py](https://github.com/OpenNMT/OpenNMT-py).
The data consists of parallel source (src) and target (tgt) data for training and validation.
A data file contains one sentence per line with tokens separated by a space.
Below are the provided example data files.

- `src-train.txt`
- `tgt-train.txt`
- `src-val.txt`
- `tgt-val.txt`

### Train model
To train model, provide the train script with a path to processed data and save files as follows:

(Configuration, Checkpoints and Logs are files used to evaluate the performance (BLEU), generate a translation and analize the loss decay over the epochs)

```
$ python train.py --data_dir=data/example/processed --save_config=checkpoints/config.json --save_checkpoint=checkpoints/model.pth --save_log=logs/results.log 
```

This saves model config and checkpoints to given files, respectively.

### Translate
To translate a sentence in source language to target language:
```
$ python predict.py --source="There is an imbalance here ." --config=checkpoints/example_config.json --checkpoint=checkpoints/example_model.pth

Candidate 0 : Hier fehlt das Gleichgewicht .
Candidate 1 : Hier fehlt das das Gleichgewicht .
Candidate 2 : Hier fehlt das das das Gleichgewicht .
```

It will give you translation candidates of the given source sentence.
You can adjust the number of candidates adjusting the corresponding parameter. 

### Evaluate
To calculate BLEU score of a trained model:
```
$ python evaluate.py --save_result=logs/example_eval.txt --config=checkpoints/config.json --checkpoint=checkpoints/_model.pth

BLEU score : 0.0007947
```

## File description
- `models.py` includes Transformer's encoder, decoder, and multi-head attention.
- `embeddings.py` contains positional encoding.
- `losses.py` contains label smoothing loss.
- `optimizers.py` contains Noam optimizer.
- `metrics.py` contains accuracy metric.
- `beam.py` contains beam search.
- `datasets.py` has code for loading and processing data. 
- `trainer.py` has code for training model.
- `prepare_datasets.py` processes data, no need to use this.
- `train.py` trains model, from here you can play with the parameters.
- `predict.py` translates given source sentence with a trained model.
- `evaluate.py` calculates BLEU score of a trained model, see `evaluator.py

## Reference
- [OpenNMT-py](https://github.com/OpenNMT/OpenNMT-py)
- Repository taken from: [@dreamgonfly](https://github.com/dreamgonfly)
## Author
[@dreamgonfly](https://github.com/dreamgonfly)
