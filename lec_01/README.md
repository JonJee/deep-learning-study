# 머신 러닝의 기본적인 용어와 개념 설명

## 무엇이 머신 러닝인가?

### 머신 러닝의 개념

주어진 환경과 조건 내에서 개발이 진행될 때 explicit programming 이라고 한다. 그러나 모든 프로그래밍 작업이 explicit 하지는 않는데, 예를 들어, 스팸 필터나 무인 주행 자동차는 예측할 수 없는 많은 규칙이 있다.

그래서 1959 년에 Arthur Samuel 이라는 사람이 다음과 같은 생각을 했다. 우리가 모든 조건을 일일히 프로그래밍 하는 것이 아니라, 주어진 자료나 현상에서 자동적으로 배우게 하는 것이다. 이것이 바로 머신러닝의 시초이다. 즉, 프로그래밍에 개발자가 관여하는 것이 아니라 주어진 자료를 바탕으로 학습하는것이 머신 러닝이라고 할 수 있다.

### Supervised/Unsupervised learning

머신러닝은 학습하는 방법에 따라 Supervised/Unsupervised learning 으로 나뉜다.

Supervised : label 들이 정해져있는 데이터(traning set)로 학습하는 것을 Supervised leaning 이라고 한다. 예를 들어, 이미지가 고양이/개 인지 판별하는 프로그램도 머신 러닝을 바탕으로 개발되는데, cat 또는 dog 라는 label 이 달려있는 이미지로 먼저 학습을 진행한 후 판별을 하게 된다.

Unsupervised : 일일히 label 을 달수 없는 자료가 있다. 예를 들면, Google news(비슷한 카테고리의 뉴스 수집)나 Word clustering(단어 수집)등이 있다. 이는 주어진 자료가 아닌 프로그램이 스스로 학습해야한다.

이중에서 Supervised learning 을 주로 다룰 예정이다.

### Supervised learning

Supervised learning 에서 다루는 주요한 문제점은 다음과 같다

- Image labeling : 이미지로부터 학습
- Email spam filter : 스팸인지 아닌지 구분된 이메일로 부터 학습
- Predicting exam score : 이전에 시험을 친 사람들의 준비시간 대비 성적으로 자신의 기대 성적을 예측

### Supervised learning 의 종류

Supervised learning 를 다루는 경우 케이스는 대개 3 가지로 압축된다.

- 시험 공부 시간 대비 최종 시험의 점수 : 0 ~ 100 점 까지 넓은 분포도를 보이는 경우 regression 이라고 한다.
- 시험 공부 시간 대비 최종 시험의 결과(Pass/non-Pass) : 결과를 2 가지로 예측하는 경우 binary classification 라고 한다.
- 시험 공부 시간 대비 최종 시험의 등급(A,B,C,E and F) : 결과가 다중인 경우 multi-label classification 라고 한다.

<p align="center">
<img src="https://user-images.githubusercontent.com/20614643/44619947-f1978f00-a8c7-11e8-8b91-89a709b6faa5.png" width="150px"/>
<img src="https://user-images.githubusercontent.com/20614643/44619948-f1978f00-a8c7-11e8-8be7-2397f346ebb5.png" width="150px"/>
<img src="https://user-images.githubusercontent.com/20614643/44619934-8e0d6180-a8c7-11e8-83ee-84875b449b05.png" width="150px"/>
<p/>

### Traning data set

Supervised learning 은 다음과 같은 값들을 주로 사용한다.

- ML(머신 러닝): 모델
- Y(label): 정해진 값
- X: 특징(feature)

데이터 셋은 Y 와 X 로 구성되므로, 특징에 따라 정해진 값을 학습하여 모델이 도출 된다.
이 때, 임의의 X 값을 구성된 모델에 대입 했을 때, Y 의 예상값을 구하는게 일반적인 Supervised learning 의 예이다.
때문에 모델의 구성을 위해 미리 준비된 Traning data set 이 필요하다.

### 알파고?

앞서 든 예와 같이 알파고는 다음과 같은 순서로 동작했다.

1. 기존의 사람들이 바둑을 둔 기보를 학습한다.
2. 이세돌이 돌을 착수 한다
3. 이 데이터를 입력 받아 모델에 적용한 후 결과값을 내놓는다.

## TensorFlow 의 설치 및 기본적인 operations

### 텐서플로란 무엇인가?

텐서플로란 구글에서 만든 오픈소스 라이브러리이며, 기계 학습을 위해 개발 되었다.

한마디로 정의하자면, 파이썬을 기반으로 데이터 플로우 그래프를 사용하여 수적인 계산을 할 수 있는 오픈소스 라이브러리이다.

텐서플로 말고도 사용할 수 있는 라이브러리는 많다. 그러나 모든 라이브러리를 비교해 보았을 때, 컨트리뷰트나, 참여자, 레퍼런스 등에서 압도적으로 높은 점수를 가지고 있기때문에, 초반 학습에 많은 이점이 있다.

### 데이터 플로우 그래프란?

그래프는 노드와 노드를 연결하는 엣지로 구성된다. 데이터 플로우 그래프란, 이러한 노드들을 하나의 operation 으로 취급할 때, 엣지는 데이터 배열 또는 텐서(Tensor)로써 연결되어 최종적으로 내가 원하는 결과물을 도출 하는것이다.

결국 이러한 텐서들의 흐름을 표현하는 것이 텐서플로의 네이밍(naming) 비화이다.

### 가상환경 설치 및 설정

```
# pip 설치
$ sudo easy_install pip

# xcode 명령어 라인 도구 설치
xcode-select --install

# pyenv 설치 및 환경변수 설정
$ brew install pyenv
$ echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
$ echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
$ echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
$ source ~/.bash_profile

# virtualenv 설치
$ brew install pyenv-virtualenv
$ echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile
$ source ~/.bash_profile

# 파이썬 버전 확인 후 특정 버전 설치(현재 기준 텐서플로가 지원되는 최신 버전은 3.5.6 이다)
$ pyenv install --list
$ pyenv install [python version]

# 가상 환경 생성 및 실행
$ pyenv virtualenv [python version] [environment name]
$ pyenv activate [environment name]
$ pyenv deactivate
```

### 특정 버전 파이썬이 설치되지 않을 경우

```bash
$ brew install homebrew/dupes/zlib
$ brew install readline xz
$ CFLAGS="-I$(brew --prefix openssl)/include" \
LDFLAGS="-L$(brew --prefix openssl)/lib" \
pyenv install -v 3.6.3
```

### 특정 폴더 진입시 가상환경 자동실행 설정

```bash
$ brew install autoenv
$ echo 'source /usr/local/opt/autoenv/activate.sh' >> ~/.bash_profile
$ source ~/.bash_profile

/Users/eunwoo/.zshrc:source:112: no such file or directory: /Users/eunwoo/.autoenv/activate.sh
autoenv:
autoenv: WARNING:
autoenv: This is the first time you are about to source /Users/eunwoo/Desktop/tensorflow/.env:
autoenv:
autoenv:   --- (begin contents) ---------------------------------------
autoenv:     pyenv activate tensorflow$
autoenv:
autoenv:   --- (end contents) -----------------------------------------
autoenv:
autoenv: Are you sure you want to allow this? (y/N)
```

### 가상 환경(virtualenv, pyenv) 명령어

```bash
$ pyenv install --list # 다운가능한 파이썬 버전 목록 보기
$ pyenv install [python version] # 특정 파이썬 버전 설치
$ pyenv versions # 설치된 python의 버전들 보기
$ pyenv uninstall [environment name] # 가상환경 삭제

# pyenv-virtualenv 명령어
$ pyenv virtualenv [python version] [environment name] # 가상환경 생성
$ pyenv activate [environment name] # 가상 환경 실행
$ pyenv deactivate # 가상 환경 종료
```

### 텐서플로 설치 및 확인

```bash
# 텐서플로 설치
pip3 install --upgrade tensorflow

# 설치 확인
$ python3
>>> import tensorflow as tf
>>> tf.__version__
'1.10.1'
```

## 예제 소스코드

https://github.com/hunkim/DeepLearningZeroToAll/

## 실습

### 주피터 노트북(jupyter notebook) 설치 및 실행

주피터 노트북이란 line by line으로 코드의 동작을 실행하면서 도식화된 결과를 확인하여, 머신러닝이나 빅데이터 분석의 편의성을 제공해주는 툴이다.


```bash
# 주피터 노트북 설치
$ pip3 install jupyter
$ jupyter notebook
```

### TensorFlow Hello World

```py
import tensorflow as tf
```

앞서 버전 확인에서 한 것 처럼 텐서플로 모듈을 사용하기위해 import 한다.

```py
hello = tf.constant("Hello, TensorFlow!")
```

import 된 텐서플로에 Hello, TensorFlow 라는 문자열을 상수(constant)로 설정한다. 상당히 간단해 보이지만 그래프에 문자열이 있는 노드를 생성한 것과 동일하다.

```py
sess = tf.Session()
print(sess.run(hello))
```

텐서플로는 session 을 만들고, 여기에 노드를 적용시켜 실행이 가능하다.