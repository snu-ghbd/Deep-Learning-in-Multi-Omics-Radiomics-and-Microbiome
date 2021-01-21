# Attention

- Reference : https://wikidocs.net/22893

## Idea of Attention
- Decoder에서 출력 단어를 예측하는 매 시점 (time step) 마다, encoder에서 전체 입력 문장을 다시 한 번 참고
- 단, 전체 입력 문장을 전부 다 동일한 비율로 참고하는 것이 아니라, 해당 시점에서 예측해야할 단어와 연관이 있는 입력 단어 부분을 좀 더 집중(attention)해서 봄 

## Attention Function
- **Attention(Q, K, V) = Attention Value**
  - Q (Query) : t 시점 (time step) 의 decoder cell 에서의 hidden state
  - K (Keys) : 모든 시점의 encoder cell 의 hidden states
  - V (Values) : 모든 시점의 encoder cell 의 hidden states
 
## Dot-Product Attention
