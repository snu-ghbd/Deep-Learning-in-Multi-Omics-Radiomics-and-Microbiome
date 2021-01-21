# Transformer

- Reference : https://wikidocs.net/31379

## Idea of Transformer
- Attention 만으로 구현 
- RNN (recurrent neural network) 을 사용하지 않고 encoder-decoder 구조를 설계함 
- 입력 시퀀스를 하나의 벡터 표현으로 압축하는 과정에서 입력 시퀀스의 정보가 일부 손실되는 단점을 보완 

## Transformer
![image info](https://wikidocs.net/images/page/31379/transformer1.PNG)
![image info](https://wikidocs.net/images/page/31379/transformer2.PNG)
- Encoder-decoder의 단위가 여러 개 존재할 수 있음 (논문에서는 6개 단위 사용) 
  - cf) seq2seq : encoder와 decoder 에서 각각 하나의 RNN이 t개의 시점을 가지는 구조  
  ![image info](https://wikidocs.net/images/page/31379/transformer4_final_final_final.PNG)

## Positional Encoding
### Input of Transformer
- 단어의 위치 정보를 얻기 위해 각 단어의 embedding vector에 위치 정보 (positional encoding) 를 더하여 입력으로 사용 
![image info](https://wikidocs.net/images/page/31379/transformer5_final_final.PNG)
![image info](https://wikidocs.net/images/page/31379/transformer6_final.PNG)

## Attention
![image info](https://wikidocs.net/images/page/31379/attention.PNG)
- encoder의 self-attention : Query = Key = Value
- Decoder의 masked self-attention : Query = Key = Value
- Decoder의 encoder-decoder attention : Query : decover vector / Key = Value : encoder vector 
![image info](https://wikidocs.net/images/page/31379/transformer_attention_overview.PNG)
