# EXPLORATION_06 : 영화리뷰 텍스트 감성분석하기 
imdb 영화 리뷰 평점 데이터를 토대로 사용자들의 리뷰 감성을 분류해 보는 실용적인 텍스트 분류 모델을 구현해 본다.

## 학습 목표
- 텍스트 데이터를 머신러닝 입출력용 수치데이터로 변환하는 과정을 이해한다.
- RNN의 특징을 이해하고 시퀀셜한 데이터를 다루는 방법을 이해한다.
- 1-D CNN으로도 텍스트를 처리할 수 있음을 이해한다.
- IMDB와 네이버 영화리뷰 데이터셋을 이용한 영화리뷰 감성 분류 실습을 진행한다.

## 진행 과정
- Step 1. 데이터 준비와 확인
- Step 2. 데이터로더 구성

  - 데이터의 중복 제거
  - NaN 결측치 제거
  - 한국어 토크나이저로 토큰화
  - 불용어(Stopwords) 제거
  - 사전word_to_index 구성
  - 텍스트 스트링을 사전 인덱스 스트링으로 변환
  - X_train, y_train, X_test, y_test, word_to_index 리턴
- Step 3. 모델 구성을 위한 데이터 분석 및 가공

  - 데이터셋 내 문장 길이 분포
  - 적절한 최대 문장 길이 지정
  - keras.preprocessing.sequence.pad_sequences 을 활용한 패딩 추가
- Step 4. 모델 구성 및 validation set 구성
- Step 5. 모델 훈련
- Step 6. Loss, Accuracy 그래프 시각화
- Step 7. 학습된 Embedding 레이어 분석
- Step 8. 한국어 Word2Vec 임베딩 활용하여 성능 개선
  - [Pre-trained word vectors of 30+ languages](https://github.com/Kyubyong/wordvectors)

## 루브릭
|평가문항|상세기준|총점|
|------|------|---|
|1. 다양한 방법으로 Text Classification 태스크를 성공적으로 구현하였다.|3가지 이상의 모델이 성공적으로 시도됨|⭐️|
|2. gensim을 활용하여 자체학습된 혹은 사전학습된 임베딩 레이어를 분석하였다.|gensim의 유사단어 찾기를 활용하여 자체학습한 임베딩과 사전학습 임베딩을 적절히 분석함|⭐️|
|3. 한국어 Word2Vec을 활용하여 가시적인 성능향상을 달성했다.|네이버 영화리뷰 데이터 감성분석 정확도를 85% 이상 달성함|⭐️|
