# Korean Out-of-vocabulary Processing with Speech information
Applications and practice in neural networks project proposal I

2022011099 김민규(kmg2933@korea.ac.kr)

## The usage of LOVE
Set up the environment via "requirements.txt". I use python 3.6.13  
If you use conda, you can create a new environment and install the requirements via the following command:
```python
conda install -r requirements.txt
```

### Training
First you can use `-help` to show the arguments
```python
python train.py -help
```
completing environment setup, we can train the model via `train.py`.  
It will run as the default option even if you don't give any option.


```python
python train.py
```
### Saved Model
After the model is trained, you should see the trained vectors in the output folder.


### NSMC

First, to generate embeddings for all words in NSMC  
You can change the model_path in argument parser of train.py file
```python
python produce_emb.py
```
Then, to train a Bi-LSTM-Attention model based on the embeddings obtained by LOVE
Go to the folder ```nsmc``` and run the script:
```
cd nsmc
python nsmc.py ./vector/nsmc.vec
```
After, you can see scores like this and get submission file for test dataset:
```
accuracy:  95.35%; precision:  83.83%; recall:  76.03%; FB1:  79.74
test acc on test set: 79.74
```
