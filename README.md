*This project is for SC4002/CE4045/CZ4045: NLP at NTU*

**Team members**
+ YEAP JIAHAO
+ LEE JUNWEI
+ GOH TECK HONG
+ YEONG KA SHING, LINUS
+ ANG YUN TING RHEA

## Abstract
In this task, we will do sentence-level classification. Question Classification aims to categorize each question into one of the topics from a pre-defined label set. We work with the TREC dataset, which contains 6 different labels under 'label-coarse'. As per the requirements of the task, 4 classes are randomly selected and the remaining 2 labels are combined to form a single class.

## Dataset
The dataset is created from [TREC](https://www.kaggle.com/datasets/thedevastator/the-trec-question-classification-dataset-a-longi?resource=download) dataset.

Using the pre-trained `word2vec` vectors will also require downloading the binary file from
[GENSIM]
'''
word2vecs_embeddings = gensim.downloader.load('word2vec-google-news-300')
word2vecs_embeddings.save('data/word2vec-google-news-300.bin')
'''

## Training
### Setup repo
# Dependency 
To install the dependencies, run 
```
pip install -r requirements.txt
```

You should probably create a [conda](https://docs.conda.io/projects/conda/en/latest/index.html) environment before running the following step.

## Creating a conda env
```
conda create --name <env> --file requirements.txt
conda activate <env>
```

# Usage 
For Jupyter Notebook files, start Jupyter Notebook server and run all codes.

+ Open keras.ipynb
+ Run all outputs

## Configuration
BATCH_SIZE = 128
DROPOUT = 0.5
EARLY STOPPING PATIENCE = 8

### Example output (Training)
CPU output:
```
Epoch 1/100
279/279 [==============================] - ETA: 0s - loss: 1.0981 - accuracy: 0.5868
Epoch 1: val_accuracy improved from -inf to 0.70200, saving model to tmp/spatial-dropout-0.4/round3\cp.ckpt
279/279 [==============================] - 80s 251ms/step - loss: 1.0981 - accuracy: 0.5868 - val_loss: 0.9085 - val_accuracy: 0.7020 - lr: 0.0010
Epoch 2/100
279/279 [==============================] - ETA: 0s - loss: 0.7466 - accuracy: 0.7217
Epoch 2: val_accuracy improved from 0.70200 to 0.73400, saving model to tmp/spatial-dropout-0.4/round3\cp.ckpt
279/279 [==============================] - 69s 248ms/step - loss: 0.7466 - accuracy: 0.7217 - val_loss: 0.6819 - val_accuracy: 0.7340 - lr: 0.0010
Epoch 3/100
279/279 [==============================] - ETA: 0s - loss: 0.6152 - accuracy: 0.7718
Epoch 3: val_accuracy improved from 0.73400 to 0.77400, saving model to tmp/spatial-dropout-0.4/round3\cp.ckpt
```

### Example output (Test)
CPU output:
```
16/16 [==============================] - 17s 111ms/step - loss: 0.3881 - accuracy: 0.8980
Best Test Accuracy: 0.8980
Best Test Loss: 0.3881
```

## Results
With the above, we are able to get the following accuracy:
| Model | Accuracy |
| -------- | ----------- |
| BiLSTM | 90.8% |
