# ktextaug


Data augmentation Toolkit for Korean text.
It provides transfomative text augmentation methods.

한국어 텍스트 증강 기법을 모아둔 패키지입니다.
현재는 변형적 텍스트 증강기법만을 구현해두었으며, 생성적 텍스트 증강기법 모델 또한 추가될 예정입니다.

## Installation

### Prerequisites

* Python 3.6
* Beautifulsoup4>=4.6.0
* Googletrans>=2.4.0
* Pandas>=1.0.4
* konlpy>=0.5.2

in command line:

```
pip install ktextaug
```

## Getting Started

ktextaug를 사용하는 간단한 예제입니다. 

```
import ktextaug

text = "이 문장은 변형적 데이터 증강기법의 예시 문장입니다."
tokenizer = bring_it_your_own # 토크나이저는 어떤 토크나이저를 사용하더라도 상관없습니다.
tokens = tokenizer.tokenize(text)
result = ktextaug.random_swap(tokens, 2) # 토큰 시퀀스 내 두 단어의 위치를 변경하는 작업(random swap)을 2회 시행합니다. 
print(result)
# ['이', '문장', '은', '예시', '적', '데이터', '기법', '증강', '의', '문장', '변형', '입니다', '.']
```

## Test it with sample data!

데이터 증강기법의 성능을 확인하실 수 있도록, 매우 작은 데이터셋을 src/data/ 에 올려두었습니다.
이 데이터는 nsmc 데이터셋의 훈련 데이터셋을 1000개 랜덤 샘플링한 결과입니다.
(출처: https://github.com/e9t/nsmc)

해당 데이터를 

## Things to know

현재 mecab 으로 토크나이저가 고정되어 있습니다. 
요구되는 패키지외에도 mecab 을 따로 설치해야 합니다.

## Author

이 패키지는 성균관대학교 정윤경 교수님 연구실 ING-lab 에서 만들었으며, 참여한 사람들은 다음과 같습니다

박종혁, 이정훈, 전현규, 정민수, 조진욱

## TODO

1. Generative Models 추가 예정 
2. 동의어 불러오는 과정의 오류 해결
3. tokenizer 받기 (기본은 설치 안해도 되는 간단한걸로)
4. 결과 해석해주는 기능