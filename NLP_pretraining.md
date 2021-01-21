# Pre-training in NLP

- Reference : https://wikidocs.net/108730

## Pre-trained Word Embedding
- Using Embedding in task
  - 1) Randomly initialize embedding layer and train from scratch 
  - 2) Use pre-trained embedding vectors (ex. Word2Vec, GloVe) 
- Limitation of embedding : 하나의 단어가 하나의 벡터값으로 맵핑되므로 문맥을 고려하지 못함 (ex. 다의어, 동음이의어 구분 불가능) 

## Pre-trained Language Model
- Semi-supervised Sequence Learning (google, 2015)
  - 주어진 텍스트로 LSTM 사전 학습 후 Labeled data로 텍스트 분류 학습하여 성능 개선 
  - 방대한 텍스트로 LSTM 언어 모델을 학습해두고, 이러한 언어 모델을 다른 Task에 사용 
    - ex) ELMo 
- LSTM 대신 Transformer 사용
![image info](https://wikidocs.net/images/page/108730/image3.PNG)
  - Transformer의 decoder가 LSTM 언어 모델처럼 순차적으로 이전 단어들로부터 다음 단어를 예측 
- 양방향 언어모델 
![image info](https://wikidocs.net/images/page/108730/image4.PNG)
  - 언어의 문맥이 양방향으로 존재함을 고려 
  - Masked Language Model 
    - 입력 텍스트의 단어 집합의 일부를 랜덤으로 마스킹한 후 인공 신경망이 마스킹 된 단어들을 예측 
