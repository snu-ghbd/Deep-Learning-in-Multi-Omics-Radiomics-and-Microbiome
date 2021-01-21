# BERT : Pre-training of Deep Bidirectional Transformers for Language Understanding

- Reference : https://mino-park7.github.io/nlp/2018/12/12/bert-%EB%85%BC%EB%AC%B8%EC%A0%95%EB%A6%AC/?fbclid=IwAR3S-8iLWEVG6FGUVxoYdwQyA-zG0GpOUzVEsFBd0ARFg4eFXqCyGLznu7w

## Pre-training in BERT
![image info](https://mino-park7.github.io/images/2018/12/그림1-bert-openai-gpt-elmo-출처-bert논문.png)
1. Masked Language Model (MLM)
  - 입력에서 무작위하게 몇 개의 token을 마스킹시킨 후 transformer에 입력으로 넣어 주변 단어의 문맥만을 보고 마스킹 단어를 예측하도록 학습 
    - cf) Decoder는 앞의 단어를 보고 뒤의 단어를 예측 
  - 입력 전체와 마스킹 된 token을 한 번에 transformer encoder에 넣고 원래 token 값을 예측하므로 deep bidirectional 한 구조 
2. Next Sentence Prediction
  - 사전학습 시 두 문장을 같이 넣어주어 두 문장이 이어지는 문장인지 아닌지 맞히도록 학습 

## BERT 
- Transformer 사용
- 사전학습과 fine-tuning 시의 아키텍처를 조금 달리 하여 전이 학습 (transfer learning)을 용이하게 만듬 

### Model Architecture
- Transformer의 encoder 부분만을 사용 

### Input Representation
![image info](https://mino-park7.github.io/images/2019/02/bert-input-representation.png)
- 입력이 3가지 embedding의 합으로 이루어짐
  - WordPiece embedding 
  - Position embedding 
  - Segment embedding 
 
### Pre-training Tasks
- Unsupervised prediction task로 사전 학습을 수행 
  - 1) Masked Language Model (MLM)
    - 문맥 파악 능력 증가 
  - 2) Next Sentence Prediction
    - 두 문장 사이의 관계 파악 능력 증가 

### Fine-tuning
- Sequence-level classification task
  - 원하는 class 수에 따라 fully connected layer 를 붙여줌 (activation function : softmax) 
- Span-level, token-level prediction task
  
