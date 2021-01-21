# Attention

- Reference : https://wikidocs.net/22893

## Idea of Attention
- Decoder에서 출력 단어를 예측하는 매 시점 (time step) 마다, encoder에서 전체 입력 문장을 다시 한 번 참고
- 단, 전체 입력 문장을 전부 다 동일한 비율로 참고하는 것이 아니라, 해당 시점에서 예측해야할 단어와 연관이 있는 입력 단어 부분을 좀 더 집중(attention)해서 봄 

## Attention Function
- **Attention(Q, K, V) = Attention Value**
  ![image info](https://wikidocs.net/images/page/22893/%EC%BF%BC%EB%A6%AC.PNG)
  - Q (Query) : t 시점 (time step) 의 decoder cell 에서의 hidden state
  - K (Keys) : 모든 시점의 encoder cell 의 hidden states
  - V (Values) : 모든 시점의 encoder cell 의 hidden states
 
## Dot-Product Attention
1) Attention Score 
![image info](https://wikidocs.net/images/page/22893/dotproductattention1_final.PNG)
- <img src="https://latex.codecogs.com/gif.latex?h_N" /> : encoder의 N 시점의 hidden state
- <img src="https://latex.codecogs.com/gif.latex?s_t" /> : decoder의 t 시점의 hidden state 
- <img src="https://latex.codecogs.com/gif.latex?a_t" /> : t번째 단어를 예측하기 위한 attention score 
  - Decoder의 시점 t 에서 단어를 예측하기 위해, encoder의 모든 hidden state 각각이 decoder의 현 시점의 hidden state s_t와 얼마나 유사한지 판단하는 score 
  - <img src="https://latex.codecogs.com/gif.latex?a_t%3D%5Ctext%7Bscore%7D%28s_t%2Ch_i%29" />
  - ![image info](https://wikidocs.net/images/page/22893/i%EB%B2%88%EC%A7%B8%EC%96%B4%ED%85%90%EC%85%98%EC%8A%A4%EC%BD%94%EC%96%B4_final.PNG)
- Attention score의 모음값 
  - <img src="https://latex.codecogs.com/gif.latex?e^t=[s_t^Th_1,...,s_t^Th_N]" />
2) Attention Distribution (by Softmax function)
![image info](https://wikidocs.net/images/page/22893/dotproductattention3_final.PNG)
- Attention Distribution : Attention score 의 모음값에 softmax 함수를 적용하여 얻어낸 확률 분포 (각각의 값 = Attention weight)
  - <img src="https://latex.codecogs.com/gif.latex?%5Calpha_t%3Dsoftmax%28e%5Et%29" />
3) Attention Value 
![image info](https://wikidocs.net/images/page/22893/dotproductattention4_final.PNG)
- 각 encoder의 hidden state와 Attention weights 들을 곱하고 모두 더함 (weighted sum) => Attention Value
  - <img src="https://latex.codecogs.com/gif.latex?a_%7Bt%7D%3D%5Csum_%7Bi%3D1%7D%5E%7BN%7D%20%5Calpha_%7Bi%7D%5E%7Bt%7Dh_%7Bi%7D" />
