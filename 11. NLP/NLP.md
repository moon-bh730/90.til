# 1. NLP 개념

## 1.1. NLP 단계

> 사전 정제작업 -> 토큰화 -> 정규화-> 불용어 제거-> 결합제약 적용 -> 품사표식

1.1.1. 사전 정제작업

> 빈칸제거, 대소문자 통일, 숫자 및 문장부호와 특수문자 제거

1.1.2. 토큰화

> 문장을 토큰 단위로 토막내기

- 토큰 : 하나의 유용한 의미적 단위로 함께 모여지는 일련의 문자열, 형태소, 단어, 복합어

- 형태소() : 더이상 분석이 불가능한 의미의 최소 단위

  ​					실질형태소[명사, 대명사, 동사, 부사] + 형식형태소[접두사, 어미, 어근]

- 단어 : 스스로 일정한 뜻을 담고 있으면서 자립하여 쓸 수 있는 의미의 최소단위

1.1.3. 정규화

> 형태소 분석하고 원형 복원하기

- 형태소 분석 : 단어를 구성하는 각각의 형태소를 인식하고 불규칙 활용이 일어난 형태소를

  ​						원형으로 복원하는 과정

- 형태소 분석의 어려움 : check [점검하다, 저지하다, 점검, 수표]

  ​										감기다 [감다의 수동형 / 사역형, 감기 + 다]

- 원형 복원 방법[innovation & innovate의 경우]

  - stemming[어간추출, 어근 동일화] innovate
  - lemmatization[표제어추출, 원형복원] innovation & innovate

1.1.4. 불용어

> 문장에 자주 등장하지만 실제 의미 분석에 기여가 없는 단어들
>
> 지시어 [구체적 대상이나 행동상태 지시] 대 기능어 [문법 기능만 수행]

- 지시어 : 명사, 대명사 , 수사, 동사, 형용사 ...

- 기능어 : 영어-관사, 전치사(a, the, to, on ...)

  ​				한국어 - 조사(은, 도, 가, 이, 을 ...)

1.1.5. 결합제약 적용

- 복합어, 축약어, 신조어 등을 처리할 때 N-gram 적용
- 텍스트 복잡성에 미치는 양면적 영향 : public relation[공중관계]

1.1.6. 품사표식(POS: part-of-speech tagging)

- 텍스트 데이터의 중의성과 모호성을 해소하기 위해서 단어가 문장에서 어떤 품사(POS: part-of-speech tagging) 인가를 표시하는 작업
- 품사표식 작업의 두가지 기법
  - 규칙기반기법(rule-based) - 대용량 사전을 사용하여 미리마련된 규칙 근거로 해당되지 않는 품사표식 제거
  
  - 스토캐스틱(stochastic) 기법 - 품사역할을 확률적으로 계산하기위해 만든 학습 말뭉치를 사용하여 품사표식의 모호성 해소
  
    
    
    

# 2. 자연어 처리

## 2.1. 머신러닝 워크 플로우

### 2.1.1. 수집(Acquisition)

>  - 말뭉치 또는 코퍼스(corpus) 
>     - 머신 러닝을 하기 위해서는 기계에 학습시켜야 할 데이터
>     - 수집된 텍스트 집합

### 2.1.2. 점검 및 탐색(Inspection and exploration)

> 탐색적 데이터 분석(Exploratory Data Analysis, EDA) 단계
> 독립 변수, 종속 변수, 변수 유형, 변수의 데이터 타입 등을 점검
> 이터의 특징과 내재하는 구조적 관계를 알아내는 과정
> 시각화와 간단한 통계 테스트를 진행

### 2.1.3. 전처리 및 정제(Preprocessing and Cleaning)

> 데이터에 대한 파악이 끝났다면 데이터 전처리 과정에 들어간다
> 토큰화, 정제, 정규화, 불용어 제거 등의 단계를 포함

#### 2.1.3.1 피쳐(Feature)

>기계 학습과 패턴 인식의 용어이다. 
>관찰 대상에게서 발견된 개별적이고 측정가능한 경험적(heuristic) 속성을 말한다. 
>독립적인 변수를 잘 선택하는 것은 패턴 인식 상에서 분류를 위한 성공 요인이라 할 수 있다

> 피쳐들은 일반적으로 수치이나, 그래프와 같은 자료 구조적인 피쳐들 또한 존재한다.
> 피쳐들의 집합을 피쳐 벡터(feature vector)라고 한다.

### 2.1.4. 모델링 및 훈련(Modeling and Training)

> **전처리가 완료 된 데이터를 머신 러닝 알고리즘을 통해 기계에게 학습(training)시킵니다**
> 데이터 중 일부는 테스트용으로 남겨두고 훈련용 데이터만 훈련에 사용해야 합니다.
> 	그래야 현재 성능이 얼마나 되는지를 측정할 수 있으며 
> 	과적합(overfitting) 상황을 막을 수 있습니다
> 데이터 양이 많다면 훈련용, 검증용, 테스트용으로 세분화
> 검증용 데이터는 현재 모델의 성능. 
> 	즉, 기계가 훈련용 데이터로 얼마나 제대로 학습이 되었는지를 판단
> 	& 모델의 성능을 개선에 사용된다.

### 2.1.5. 평가(Evaluation)

> 테스트용 데이터로 성능을 평가
> 기계가 예측한 데이터가 테스트용 데이터의 실제 정답과 얼마나 가까운지를 측정

### 2.1.6. 배포(Deployment) 

> 평가 단계에서 기계가 성공적으로 훈련이 된 것으로 판단된다면, 완성된 모델이 배포되는 단계



# 3. 텍스트 전처리

## 3.1. 토큰화(Tokenization)

## 3.2. 정제(Cleaning) and 정규화(Normalization)

## 3.3. 어간 추출(Stemming) and 표제어 추출(Lemmatization)

## 3.4. 불용어(Stopword)

## 3.5. 정규 표현식(Regular Expression)

## 3.6. 정수 인코딩(Integer Encoding)

## 3.7. 패딩(Padding)

## 3.8. 원핫 인코딩(One-Hot Encoding)

> 문자를 숫자(더 구체적으로는 벡터)로 바꾸는 작업
>
> 단어 집합을 만들기(중복 제거) -> 단어 집합에 고유한 숫자를 부여하는 정수 인코딩(인덱싱)

### 3.8.1. 원핫 인코딩

> 1) 단어별 고유 인덱스 부여
> 2) 표현할단어에 1, 다른단어는 0 부여

```python
# 1. 단어 분할
from konlpy.tag import Okt  
okt=Okt()  
token=okt.morphs("나는 자연어 처리를 배운다")  
print(token)

# 2. 코엔엘파이의 Okt 형태소 분석기로 문장에 대해서 토큰화
# 토큰별 인덱스 부여
word2index={}
for voca in token:
     if voca not in word2index.keys():
       word2index[voca]=len(word2index)
print(word2index)

# 토큰을 입력하면 해당 토큰에 대한 원-핫 벡터를 만들어내는 함수
def one_hot_encoding(word, word2index):
       one_hot_vector = [0]*(len(word2index))
       index=word2index[word]
       one_hot_vector[index]=1
       return one_hot_vector

one_hot_encoding("자연어",word2index)
```

### 3.8.2. 케라스(Keras)를 이용한 원-핫 인코딩(One-Hot Encoding)

> to_categorical()

```python
text="나랑 점심 먹으러 갈래 점심 메뉴는 햄버거 갈래 갈래 햄버거 최고야"

# 케라스 토크나이저를 이용한 정수 인코딩------------------------
from tensorflow.keras.preprocessing.text import Tokenizer
from tensorflow.keras.utils import to_categorical

text="나랑 점심 먹으러 갈래 점심 메뉴는 햄버거 갈래 갈래 햄버거 최고야"

t = Tokenizer()
t.fit_on_texts([text])
print(t.word_index) # 각 단어에 대한 인코딩 결과 출력.

# ------------------------케라스 토크나이저를 이용한 정수 인코딩

# texts_to_sequences()를 통해서 이를 정수 시퀀스로 변환--------------

sub_text="점심 먹으러 갈래 메뉴는 햄버거 최고야"
encoded=t.texts_to_sequences([sub_text])[0]
print(encoded)

one_hot = to_categorical(encoded)
print(one_hot)
```

### 3.8.3. 원-핫 인코딩(One-Hot Encoding)의 한계

> 단어의 개수가 늘어날 수록, 벡터를 저장하기 위해 필요한 공간이 계속 늘어난다
> 		(저장 공간 측면에서는 매우 비효율적인 표현 방법)
> 단어의 유사도를 표현하지 못한다 -> 검색 시스템 등에서 심각한 문제
