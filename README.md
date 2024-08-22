# 파이썬 교육
https://wikidocs.net/book/1 
위 주소로 들어가면, 설명이 잘되어있음

2. 개발 환경
   파이썬 공식 사이트에서 제공하는 파이선프로그램 개발을 위한 기본 개발 툴
   IDLE : integeted de
   위 프로그램을 통해 파이썬을 구동함 (저장시, .py 확장자명 필요함)

   좀 더 쉽게 구동하기 위해 jupyter를 사용함
   anaconda <- 다른 분들이 만들어 놓은 페키지를 다운로드 받기 위해, 하나의 윈도우에 여러 파이썬 파일을 받을 수 있음.
   Anaconda prompt <- base의 의미는 아직 아무런 페키지가 로드되어 있지 않기 때문에.

   
```
conda env list
```
-  아나콘다에 설치되어 있는 환경 확인 가능 (중요)

```
conda search "^python$"
```
-  conda의 버젼을 확인 가능함(3.12.4까지 나와있고 설치할 수 있다는 의미)


```
conda create -n edu_1 python==(원하는 버전) pip
```
-  파이썬의 새로운 버젼을 설치할 수 있음(prompt 상에서)
-  conda env list를 입력하면 (base)말고 다른 환경이 생김

```
conda activate edu_1
```
- edu_1이라는 환경으로 이동함(base -> edu_1 으로 이동됨)

```
pip install jupyterlab
```
- 외부환경에서 주피터 다운로드할 수 있도록 파일들가져옴

```
jupyter lab
```
-  prompt상에서 다음과 같이 입력하면 jupyter lab으로 들어가짐

2-1. jupyter lab 
-  cell로 나눠져 있음 ,추가 가능함, 코드를 입력, 가위 모양이 셀잘라 놓고 복사 가능, 드레그앤드랍으로 셀 순서 조정가능
-  shift+enter로 확인 셀 실행 가능

  -   만약 'python --version'을 입력하면 에러가 뜸(idle환경이 아니므로)
  -   '!python --version'으로 입력할 경우 실행됨

'ikernel'을 다운받는 법
```
python pip ipykernel
python -m ipykernel install --user --name=edu_2
```
위 명령어는 ikernel이라는 가상환경을 설치하는 방법

2-2. vscode
  -  extension을 통해 개발환경을 설치할 수 있음
    -  python이라고 입력 -> python, python debugger, indent, extension pack 설치
  -  python file 제작
-코드 입력 중 ctrl + space로 추천받을 수 있음

-  ctrl+shfit+p => ikernel 환경을 바꿀 수 있음(?)
  -  'select interpreter'가 나온다는데 나는 안나옴 ㅜ
