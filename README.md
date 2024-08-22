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

## 2-1. jupyter lab 
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

## 2-2. vscode
  -  extension을 통해 개발환경을 설치할 수 있음
    -  python이라고 입력 -> python, python debugger, indent, extension pack 설치
  -  python file 제작
-코드 입력 중 ctrl + space로 추천받을 수 있음

-  ctrl+shfit+p => ikernel 환경을 바꿀 수 있음
  -  '>'기호가 뜨면, 'python'을 입력하고 'select interpreter'를 클릭

2시에 민방위 예정

-   만약 vscode상에서 명령어에 블럭처리 후, shift+enter를 누르면 바로 command가 run이 됨.
  -   extension 창에서 'code runner'를 다운로드 후, 실행하면 바로 running 됨.

## 3.1 파이썬의 기본문법

-변수 a에 20을 저장, 즉 변수 a가 가리키는 메모리 공간에 20을 저장한다는 의미
   -    degital이 처음에 나오는 변수는 사용불가 '1_t = 4'사용불가.
   -    띄어쓰기 사용불가.

-   int 숫자, string 문자열, boolean true or false, list
-   자주 사용하는 함수
  -   split, len, replace, find(특정 문자열에서 어떤 문자가 있는지 없는지 확인하는 코드), upper, lower
  -    print(text,isspace())
       -   text라는 문자열에 공백이 있는지 알려줌. -> 공백이 있으면 true로 표시, 공백이 없으면 false 표시
   
-   boolean
```
a=10
b=20
c = a>b
print(c)
```
### 3.1.1 사칙연산
```
num1 = input('첫번째 수 입력:')
num2d= input('두번째 수 입력:')
print(num1, num2, sep='::')
print(type(num1), type(num2))
print(num1+num2)
```
   -   :을 입력함으로써 run시, 원하는 숫자를 표기할 수 있음
   -   input함수는 모든 숫자를 int로 받지 않고 string으로 받음
   -   이렇게 str일 경우, 숫자로 받지 않기때문에 +를 사용하더라도 숫자를 더할 수 없고, 그냥 나열하게 됨.
     -   이렇게 문자형이나 숫자형으로 데이터를 바꾸는 것이 중요함.
       
       ```
       num1 = int(input('첫번째 수 입력:'))
       num2 = int(input('두번째 수 입력:'))
       print(num1, num2, sep='::')
       print(type(num1), type(num2))
       print(num1+num2)
       ```
- 산술연산자가 int에서만 실행되는가? 아니다. str에서도 같은 방식으로 print가 될 것이다.

-   문제 : 성적 평균구하기
```
name = input("학생 이름을 입력하세요:")
kor = int(input('국어 성적을 입력하세요.:'))
eng = int(input('영어 성적을 입력하세요.:'))
math = int(input('수학 성적을 입력하세요.:'))

tot = kor + eng + math
avg = print(name,'의 성적은', tot/3, '입니다.')
```
### 3.1.2 조건문

  -   특정 조건을 만족할 때와 만족하지 않을때의 경우를 나눠서
  -   
```
a = 1
b = 2
c = a > b
print(c)
if a > b:
   print('a가 b보다 크다.')
else:
   print('a가 b보다 작습니다.')
```

       
```
#나이에 따른 목욕탕 입장료
age = int(input('나이를 입력해주세요:'))
pay = '3000원'
if age >= 65 or age < 7:
   pay = '무료'
print('입장료는',pay,'입니다.')
```

```
#비밀번호 맞고 틀림에 따른 결과 확인
answer = '12354'
password = input('비밀번호를 입력해주세요.')
if password.strip() == answer:
   print('비밀번호가 맞습니다.')
else:
   print('비밀번호가 틀립니다.')
```

-   strip 함수는 앞뒤에 나온 space를 없애줌

```
#일반실과 특실을 나눠주는 함수
# 일반실 = 1, 특실 = 2
num = int(input('좌석의 종류를 입력해주세요.(일반실:1,특실:2)'))
   seat1 = '일반실'
   seat2 = '특실'
if num == 1:
   print(seat1)
elif num == 2:
   print(seat2)
else:
   print('좌석이 존재하지 않습니다.')
```

```
# range 설명
sum = 0

for i in range(1, 10):
   sum = sum + i
   print('sum:'+str(sum), '현재 index i:'str(i))
```
```
#range function 사용
for i in rnage(5):
   print(i)
print('완료')
```

```
#중간 끊기
for i in range(5):
   print(str(i))
   if i == 2:
      break
```
- 이와 다르게 break말고 continue나 pass를 사용할 수 있음.

```
#구구단을 외우자
for i in range(1,10):
   for j in range(1,10):
      print('*'*5,str(i),'단','i*j','*'*5)
   if i == 1:
      break
a=2
for b in range(1,10):
   c=a*b
   print("%d x %d=%d" %(a,b,c))
```

### 3.1.3 자료형

-   여러 데이터를 모은 집합 형태 자료형
  -   list : 데이터를 순차적으로 저장(열거)
  -   tuple  : 값을 변경할 수 없는 데이터 셋(한번 들어간 data가 수정,삭제 불가능)-> remove, append 불가능
  -   dictionary : 값에 key값을 부여된 집합

```
#리스트 선언하기
li = []
print(type(li))
li = list()
print(type(li))
li = ['a', 1, '0.0', 33]
## 자료의 갯수 카운트
print(len(li))
## 특정 위치의 list data 확인
print(li[1])
## list에 다른 데이터 삽입
li.append(true)
print(li)
##문구를 특정위치 삽입
li.insert(0, 'python')
## 값을 삭제
li.remove(1)
## 하나의 data만 꺼내기
li.pop(1)
```

```
# list에서 sort하기
li = list(range(1,10))
print(li)
## 거꾸로 나오게 함(9,8,7,6,5,4.....1)
li.sort(reverse=true)
print(li)
```

```
score =[99. 76,34, 43, 27]
sum = 0
for i in score:
   sum = sum + i

avg = sum/ len(score)
print('총점:', sum, '평균:' + str(avg))
```

```
# 로또 번호 예측
import random
lotto = []
for i in range(0,6):
   r = random.randint(1,45)

   if lotto in r:
      print('이미 존재')
   else:
      lotto.append(r)

print(lotto)
```

```
# tuple 선언
li = list(range(0,2))
tu = tuple(li)
print(type(tu))
```

```
#dictionary 선언
_dic = {'a':'1', 'b':'2', 'c':'3'}
for key in _dic:
   print(key, _dic[key])
```

### 4. PDB protein data를 parsing 후, 시각화해보기

-   jupyter notebook에서 실행해야함.
-    C:/Users/KOBIC/AppData/Local/Programs/Python/Python311/python.exe -m pip install py3Dmol
  -   위 명령어를 통해 py3Dmol를 다운로드 받기

```
protein_file='c:/Users/KOBIC/Desktop/edu/protein_result.txt'

pdb_id = []

with open(protein_file, 'r') as file:
    for line in file:
        data = line.strip()
        if 'PDBsum' in data:
            temp_1 = data.split(',')
            for text in temp_1:
                t= text.strip()
                if t.startswith('PDBsum'):
                    id = t.split(':')[1]
                    pdb_id.append(id)
                    
print(len(pdb_id))
print(pdb_id[:10])
            
import py3Dmol


viewer = py3Dmol.view(query='pdb:' + pdb_id[2])
viewer.show()
viewer.setStyle({'cartoon': {'color':'spectrum'}})
viewer.show()
```

