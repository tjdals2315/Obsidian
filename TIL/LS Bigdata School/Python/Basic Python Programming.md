# <font color="#0070c0">파이썬 기초</font>

```py
# 출력을 해주는 함수
print("안녕 파이썬")
```

```py
print("안녕"*10)
```

- 표현식: 값으로 표현하는 코드
	`23` `"hello"` `1 + 2`

| Operator         | Name                | Example |
|:----------------: |:------------------- | :-------: |
| +                | Addition            | x + y   |
| -                | Subtraction         | x - y   |
| *                | Multiplication      | x * y   |
| /                | Division            | x / y   |
| //               | Floor division (몫) | x // y  |
| %                | Modulus (나머지)    | x % y   |
| **               | Exponentiation      | x ** y  |
| ==               | Equal               | x == y  |
| !=               | Not equal(≠)        | x != y  |
| +=, (-=, *=, /=) | x = x + 3           | x += 3  |

- 문장: 실행될 수 있는 코드로 표현식이 하나 이상 모인 것
	`a = 1 + 2`       `print("hello python")`
- 프로그램: 문장이 모여서 만들어진 코드
	```py
	import time
	s = 1
	time.sleep(s)
	print("Hello")
	```

### 키워드
- 특별한 의미가 부여된, 예약된 단어
- 사용자가 변수나 함수 등의 이름을 정할 때 키워드 사용할 수 없음
	```py
	# 키워드 확인하는 방법
	import keyword
	print(keyword.kwlist)
	```

### 식별자
- 프로그래밍 언어에서 변수, 함수 등의 이름을 붙일 때 사용하는 단어
- 대/소문자 구분함
- 키워드 사용불가
- 특수 문자는 언더바(_) 사용 가능함
- 숫자로 시갖할 수 없음
- 공백 포함할 수 없음
1. **snake_case**
	- 모두 소문자이거나 대문자인 평평한 모양
	- 파이썬에서는 모두 소문자로 작성하되, 단어와 단어 사이를 언더바(_)로 구별함
	- ==함수나 변수의 이름 작성 방법==
			- 함수는 소괄호가 있고, 변수는 없음

2. **PascalCase**
	- 단어의 첫글자는 대문자이고 나머지는 소문자인 울퉁불퉁한 모양
	- 파이썬에서는 단어의 첫 글자는 대문자로 나머지는 소문자로 작성하되 모든 단어는 공백없이 붙여서 사용함
	- ==클래스 이름 작성 방법==


# <font color="#0070c0">파이썬 기본 자료형</font>
## 기본 자료형 (data type): 자료의 형식
1. 문자형 - [[문자열 (string)]]
2. 수치형 - [[숫자 (number)]]
3. 논리형 - [[불 (boolean)]]

## 자료형 확인

### 함수 type()
- 문자열 str
- 정수 int
- 실수 float
- 논리형 bool
	```py
	print(type("hungry"))
	print(type(23))
	print(type(2.3))
	print(type(True))
	```
### 집합형 자료형
- [[리스트 list]]
- 튜플 tuple
- [[딕셔너리 dictionary]]
### 컨테이너 자료형
- 서로 다른 자료형을 쉽게 묶어 사용 가능
		- 순서가 **있는** 컨테이너
		: 문자열, 리스트, 튜플, range
		- 순서가 **없는** 컨테이너
		: 딕셔너리

### 현재 날짜 시간 활용
- 모듈 `datetime` 필요
```py
import datetime # datetime 모듈 불러옴
now = datetime.datetime.now()

print(now); print(now.year); print(now.month); print(now.day)
print(now.hour); print(now.minute); print(now.second)
print(now.weekday())

# 0: 월, 1: 화, 2: 수, 3: 목, 4: 금, 5: 토, 6: 일
```

```py
import datetime
now = datetime.datetime.now()

print("{}년 {}월 {}일 {}시 {}분 {}초입니다.".format(now.year, now.month, now.day,now.hour, now.minute, now.second))
```
# <font color="#0070c0">변수</font>
- 프로그래밍 - 어떠한 값을 저장하는 장소
- 값을 저장할 때 사용하는 식별자
	```py
	pi = 3.14 # 변수 생성
	print(pi) # 변수 확인
	print(pi + pi) # 변수 사용
	```
### 변수 이름 작성
1. 파이썬은 대소문자 구분하므로 변수는 소문자로 작성하는 것을 권장
2. 키워드 사용 불가
3. 알파벳, 숫자, 밑줄로 구성하여 작성
	- 알파벳, 밑줄로 시작할 수 있음
	- 숫자로 시작할 수 없음
4. 의미가 있는 단어로 작성하는 것이 좋음
5. 주로 snake_case 이용함
	```py
	_2var = 6
	_var2 = 7
	var2 = 8
	print(_2var, _var2, var2)
	```

## 복합대입연산자
- 숫자에서 사칙 연산자 등 기본 연산자와 = 기호를 함께 사용하는 방법
	- `+=` 더하기 후에 대입
	- `-=` 빼기 후에 대입
	- `*=` 곱하기 후에 대입
	- `/=` 나누기 후에 대입
	- `//=` 몫을 구한 후에 대입
	- `%=` 나머지를 구한 후에 대입
	- `**=` 제곱 후에 대입
	```py
	# += <= 문자 (+, *)
	string = "안녕"
	string += "!" # 안녕 + ! = 안녕! = string
	string += "!" # 안녕! + ! = 안녕!! = string
	string += "!" # 안녕!! + ! = 안녕!!! = string
	print(string)
	```

	```py
	string = "안녕"
	string *= 2 # 안녕 + ! = 안녕! = string
	string *= 2
	string *= 2
	print(string)
	```

## 사용자 입력

### 표준 입력 함수 `input()`
- 프롬프트에서 사용자가 입력한 값을 받을 때 사용함
- 함수 input()이 실행될 때는 사용자가 값을 입력하기 전까지 프로그램이 잠시 멈추는데 이것을 블록이라고 함
- ==사용자가 어떤 값을 입력해도 항상 문자열로 저장됨==
	```py
	# 입력값에 23 입력하기
	value = input("값을 입력하세요>"); print(type(value)) 
	```

#### case function(캐스트 함수)
: 문자열을 숫자로 변환하는 함수(자료형 변환)
- `int()`: 정수로 변환, 실수 입력하면 ValueError 발생
	```py
	input_a = input("첫번째 정수를 입력하세요> ")
	input_b = input("두번째 정수를 입력하세요> ")
	int_a = int(input_a)
	int_b = int(input_b)
	print("문자열 = ", input_a + input_b)
	print("정수 = ", int_a + int_b)
	```
- `float()`: 실수로 변환, 실수 & 정수 모두 입력 가능함(범용성 있음)
	```py
	a = input("input float>")
	print(type(a))
	
	a = float(a)
	print(type(a))
	```

# <font color="#0070c0">조건문</font>
조건문의 종류
1. if 조건문
2. if ~ else 문
3. if ~ elif ~ else 문

## if 조건문
조건식이 참인 경우에만 실행
```py
# 짝수, 홀수 구분하는 프로그램(1)
no = input("숫자(정수)를 입력하세요> ")
last_no = int(no[-1]) # 마지막 숫자를 뽑음
if last_no == 0 or last_no == 2 or last_no == 4 or last_no == 6 or last_no == 8:
  print("현재 입력한 숫자는 짝수입니다.")
if last_no == 1 or last_no == 3 or last_no == 5 or last_no == 7 or last_no == 9:
  print("현재 입력한 숫자는 홀수입니다.")
```

```py
# 짝수, 홀수 구분하는 프로그램(2)
no = input("숫자(정수)를 입력하세요> ") #가장 일반적으로 사용하는 코드
last_no = int(no[-1])
if last_no % 2 == 0:
  print("현재 입력한 숫자는 짝수입니다.")
if last_no % 2 == 1:
  print("현재 입력한 숫자는 홀수입니다.")
```

```py
# 짝수, 홀수 구분하는 프로그램(3)
no = input("숫자(정수)를 입력하세요> ")
last_no = no[-1]
if last_no in "02468":#문자열 안에서 확인하는방법
  print("현재 입력한 숫자는 짝수입니다.")
if last_no in "13579":
  print("현재 입력한 숫자는 홀수입니다.")
```

```py
# 계절을 알려주는 프로그램
import datetime
now = datetime.datetime.now()

if 3 <= now.month <= 5:
	print("spring")
	
if 6 <= now.month <= 8:
	print("summer")
	
if 9 <= now.month <= 11:
	print("fall")

if now.month == 12 or 1 <= now.month <= 2:
	print("winter")
```

## if ~ else 문
- 조건문이 참인 경우와 거짓인 경우를 모두 실행

## if ~ elif ~ else 문
- 조건이 3개 이상일 때 연결하여 사용하는 경우
```py
score = float(input("학점을 입력하세요> "))

if 3.5 <= score <= 4.5:
	print("당신의 학점은 A입니다.")

elif 2.5 <= score:
	print("당신의 학점은 B입니다.")

elif 1.5 <= score:
	print("당신의 학점은 C입니다.")

elif 0 < score:
	print("당신의 학점은 D입니다.") 

else:
	print("당신의 학점은 F입니다.") 
```
⟹ 위에서 비교됐다면 2.5 <= score < 3.5 라고 다시 작성 안해도 된다.

## 조건문에 들어가면 **False** 로 변환되는 값 3 가지
- None
	```py
	if None:
		print("None 값은 현재 True입니다.")
	
	else:
		print("None 값은 현재 False입니다.")
	```
- 0
	```py
	if 0:
		print("0 값은 현재 True입니다.")
	
	else:
		print("0 값은 현재 False입니다.")
	```
- 비어 있는자료나 자료 구조(빈 컨테이너, 비어 있는 문자열 등)
	```py
	if []:# 비어있는 자료
		print("리스트 값은 현재 True입니다.")
	
	else:
		print("리스트 값은 현재 False입니다.")
	```




# <font color="#0070c0">반복문</font>
반복문
: loop, 정해진 동작을 반복적으로 수행할 때 사용하는 명령어

## for 문
- 특정 횟수만큼 반복 = ==반복 횟수를 정할 수 있다==
- 문자열, 리스트, 딕셔너리, 범위 등과 조합하여 반복
```ad-note
**for**  반복할 이름  **in**  리스트
- 리스트 안의 요소 개수 만큼 반복
- 관례상 반복할 이름은 i, j, k 가 자주 사용 된다. 
or
**단수** in **복수** (ex. **item** in **items**)
```

### 중첩 리스트 & 중첩 반복문
- 중첩 반복문
	- 반복문을 여러 겹 중첩하여 사용
	- 일반 적으로 n 차원 처리할 때 사용
	1. 2차원 리스트에서 반복문 **1**번 사용
		```py
		list_of_list = [
		[1, 2, 3],
		[4, 5, 6, 7],
		[8, 9]
		]
		
		for items in list_of_list:
			print(items)
		```
	2. 2차원 리스트에서 반복문 **2**번 사용
		```py
		list_of_list = [
		[1, 2, 3],
		[4, 5, 6, 7],
		[8, 9]
		]
		
		# 전부다 2차원임으로 for를 한번 더 사용해야함
		for items in list_of_list:
			for item in items:
				print(item)
		```

#### 중첩 반복문으로 피라미드 만들기
```py
# 반쪽 피라미드
output = ""
for i in range(1, 10):
	for j in range(0, i):
		output += "*"
	output += "\n"
print(output)
```

```py
# 전체 피라미드
output = ""
for i in range(1, 10):
	for j in range(9, i, -1):
		output += " "
	for k in range(0, 2 * i -1): # 홀수개의 *이 생성되어야 함
		output += "*"
	output += "\n"

print(output)
```

### 리스트로 반복문
- 리스트 안에 있는 요소가 모두 리스트가 아닌 경우 ex. [리스트, 리스트, 요소]
```py
# 조건문과 함께 사용하여 리스트가 있다면 두번 반복하도록 만든다.
list_c = [[1,2,3],[4,5,6],7]

for i in list_c:
	if type(i) == list:
		for j in i:
			print(j)
	else:
		print(i)
```

#### 리스트와 범위로 반복문
- 인덱스 번호와 값을 동시에 출력해보자.
	```py
	list_a = [21, 34, 11, 5, 67]
	
	for i in range(len(list_a)):
		print("index", i, "value", list_a[i])
	```

### ![[딕셔너리로 반복문]]

### 범위와 반복문
- 범위 range
	- 반복 횟수 지정 가능(특정 횟수만큼 반복할 경우에 사용)
	- 매개변수는 반드시 **정수**로 입력
	- ==**끝 번호** 포함하지 **않음**==
	```py
	# 1) 끝번호, 시작 번호 생략(= 처음부터)
	range(10) # 10번 반복
	print(list(range(10))) # range(9+1)
	```
	
	```py
	# 2) 시작 번호, 끝번호 & 간격이 1 (기본값)
	range(1,10) # 9번 반복
	print(list(range(1,10))) # range(1,9+1)
	```
	
	```py
	# 3) 시작 번호, 끝번호, 간격 2
	range(1,10, 2) # 5번 반복 1 부터 9까지 간격 2를 두고
	print(list(range(1,10, 2))) # range(1,9+1,2)
	```

#### 역반복문
역반복문: 반대로 반복
- 범위 ** `range(A, B, -1)`**
	 - A: 끝번호, B: 시작번호, -1: 간격(다른 숫자 가능)
	```py
	for i in range(5, 0, -1): # range(5, 1 -1, -1)
		print(i)
	```
	
	```py
	for j in range(6, -1, -2): # range(6, 0 -1, -2)
		print(j)
	```
- 함수 **`reversed(range(A, B))`**
	- A: 시작번호(생략 가능), B: 끝 번호
	```py
	for i in reversed(range(5+1)):
		print(i)
	```

## while 문
- 조건이 **참**인 경우 반복한다.
	- 만약, 조건이 무조건 참이면 **무한 반복**이 됨 ⇒ ==**무한루프**==

	cf. 
	- 함수 print( ) 의 end 기본 값은 줄바꿈(`end = \n`)이다.
	- `end = ""`을 입력하면 옆으로 작성된다.

### while 문 사용
#### for 문 처럼 while 문 사용
- 비교 연산자 이용
	```py
	i = 0 
	while i < 10:
		print(i)
		i += 1
	```
#### 상태를 기반으로 반복
- 연산자 in 사용
```py
# 중복되는 2를 지워주는 코드
list_a = [1, 2, 3, 2, 4, 2, 5]
value = 2
while value in list_a:
	list_a.remove(value)
print(list_a)
```

#### 특정시간 기반으로 반복
- 통신과 관련해서 자주 사용
- 일반적으로 **시간 기반**으로 반복할 때 while 문을 사용
- 유닉스 타임을 기준
	- 세계 표준시 1970년 1월 1일 0시 0분 0초 기준으로 몇초가 지났는지 정수로 표현됨
	```py
	import time
	print(time.time())
	```

```py
import time
number = 0
target = time.time() + 3 # 3초 동안 반복해라

while time.time() < target:
	number += 1
print(number)
```

### 반복문의 제어
- 키워드 **break**
	- 중간에 반복을 종료
	- 일반적으로, 조건문을 함께 사용하여 조건을 만족하면 종료하는 식으로 사용
	```py
	# 반복 종료
	i = 0
	
	while True:
	  print(i)
	  i += 1 # 반복 횟수 출력
	  yn = input("종료할까요? (종료를 원하시면 Y 나 y 를 입력하세요)> ")
	  if yn in ["Y", "y"]:
	    print("반복 종료")
	    break # 내가 원하는 조건을 만족하면 break를 써서 멈춤
	```
- 키워드 **continue**
	- 실행 중인 반복문을 <u>건너뛸 수 있음</u> = 현재 반복 명령을 실행하지 않고 **다음 반복으로 넘어간다**.
	- 다음 문장에서 들여쓰기를 하지 않아도 된다.
	```py
	# continue 사용
	i = 0
	
	while i < 10:
	  if i % 2 == 0:
	    i += 1
	    continue
	  print(i)
	  i += 1
	```

# <font color="#0070c0">함수</font> 

### **함수의 정의**
- 함수가 해야할 기능(function)을 구체적으로 기술하는 것
- 어떤 일을 수행하는 여러줄의 코드 전체

### ** 함수의 장점**
1. 반복 수행 업무를 한 번만 작성해 놓고 필요할 때마다 호출하여 사용 가능
2. 코드를 논리적 단위로 분할 가능
3. 코드를 모듈처럼 **재사용 및 공유** 가능

### **함수 선언**
```ad-Key
> def <u>함수 이름(매개변수)</u>:
> **&nbsp;** **&nbsp;** **&nbsp;**명령어...
> **&nbsp;** **&nbsp;** **&nbsp;**return 반환값
- def = 정의(definition)
- 매개변수(인수) = 입력값(input)
- 명령어 = 기능(function)
- 반환값 = 출력값 (output)
```

### **함수의 형태**
- 매개변수와 반환값의 유무에 따라 4 가지 형태로 구분
- ==반환값(return)이 없으면 **None**으로 저장됨==

```py
# 매개변수 ⃝ & 반환값 ⃝
def plus1(x, y):
	return x + y
a = plus1(2, 3) # 안나옴
print(a) 

# 매개변수 ⃝ & 반환값 X
def plus2(x, y):
	print(x + y)
b = plus2(2, 3) # print 출력
print(b) # None

# 매개변수 X & 반환값 ⃝
def plus3():
	return 2 + 3 # 매개변수  & 반환값 ⃝
c = plus3() # 안나옴
print(c)

# 매개변수 X & 반환값 X
def plus4():print(2 + 3)
d = plus4()
print(d) # None
```


## 리스트에 적용 가능한 함수

### 파이썬 내장 함수
- 함수 `min()` / `max()` #iterable #가변매개변수
	- 리스트를 직접 사용하지 않고 개별 요소의 값을 직접 넣어서 사용 가능
	```py
	list_a = [1,2,3,4,5]
	print(min(list_a))
	print(max(list_a))
	```
- 함수 `sum()` #iterable
	- 매개변수 **start**
	```py
	# 시작하는 숫자 지정할 수 있음
	print(sum([1, 2, 3], 5))
	print(sum([1, 2, 3], start = 5))
	```

### 리스트 값의 순서를 반대로 바꾸는 함수
- 순서가 있어야 함
- 함수 `reversed()` #list #tuple #string
	- 함수 결과: [[이터레이터]] 객체
	- 반환값이 리스트가 아니므로, list() 사용해야함

- 함수 `reverse()` #list
	- `reversed()`와 결과는 같지만, 파괴적 처리를 한다.

## 인덱스 번호와 값 확인 방법
### 리스트를 이용한 반복문
```py
list_a = [21, 34, 11, 5, 67]
i = 0
for j in list_a:
	print(f" index {i} value {j}")
	i += 1
```

### 리스트와 범위를 이용한 반복문
```py
list_a = [21, 34, 11, 5, 67]
for i in range(len(list_a)):
	print("index", i , "value", list_a[i])
```

### 함수 `enumerate()` 
- 튜플 형태로 반환 
	((인덱스, 값),(인덱스, 값2)) 형태
```py
# enumerate 함수 with 리스트
list_a = [21, 34, 11, 5, 67]
list(enumerate(list_a))
print(list(enumerate(list_a))) # 튜플 형태로 반환

for i, j in enumerate(list_a):
	print(f"index {i} value {j}")
```

### 함수 `items()` #dictionary
- 딕셔너리에 적용 가능한 함수
- 딕셔너리 안에 들어있는 키와 값을 확인
- 반복문 for 작성을 쉽게 할 수 있음
```py
dic = {
	"name": "최민혁",
	"age": 26,
	"height": 180,
	"weight": 70
}

for i, j in dic.items():
	print(f"key is {i} value is {j}")
```

## 파이썬 스타일 코드 (pythonic code)
: 파이썬 특유의 문법

### 리스트 컴프리헨션(list comprehension)
- 기존 리스트형을 사용하여 간단하게 새로운 리스트를 만드는 방법
- 필터링, 중첩, 이차원 리스트 등 다양한 방법으로 사용 가능
```py
list_a = [i for i in range(1, 6)]
print(list_a)
list_b = [i ** 2 for i in range(1, 6)]
print(list_b)
```

조건문 (필터링) 추가
```py
# 홀수만 출력
result = [i for i in range(10) if i % 2 == 1]
print(result)

# 채소를 제외한 과일만 리스트로 저장
list_a = ["사과", "복숭아", "수박", "토마토", "망고"]
fruit = [ j # 표현식(값 표현)
	for j in list_a # 반복문
	if j != "토마토"] # 조건문
	
print(fruit)
```

## 구문 내부에 여러 문자열 사용시 문제점
- 조건문이나 반복문 안에서 **들여쓰기**
	- 문장 안에서 줄바꿈으로 여러 문자열을 사용하게 되면 같이 들여쓰기가 되는 문제점
		or
		들여쓰기를 없애기 위해 문자열을 맨 앞으로 보내면, 문장 안에서 들여쓰기 통일성이 없어짐
	- `\n` 을 사용해서 해결

- 괄호로 문자열 연결하기
: 여러개의 문자열을 한 줄의 문자열을 합칠 때, 소괄호 안에 쉼표(,)를 입력하면 튜플이됨으로 **쉼표 없이** 작성해야 한다.

```py
a = (
	"Hello"
	"My name is "
	"Seongmin"
)
print(a); print(type(a))

b = (
	"Hello",
	"My name is ",
	"Seongmin"
)
print(b); print(type(b))
```

### 함수 `join()`
- 리스트 안의 문자열을 **지정한 문자**로 연결하여 합쳐 줌
- 문자열은 **대괄호([ ])** 안에 있어야 함
```py
print("-".join(["010", "1234", "5678"]))
print(" ".join(["010", "1234", "5678"]))
print("|".join(["010", "1234", "5678"]))
```

## [[사용자 정의 함수]]

## 리턴

- 함수의 결과 → 반환값 / 리턴값

### **자료 없이 리턴**

키워드 `return`: 함수를 실행했던 위치로 돌아가라는 의미 + 함수를 여기서 끝내라는 의미

```py

def return_test():
    print("A")
    return
    print("B")
	
return_test()

```

⇒ `return`을 만나면서 함수가 종료되어 "A"가 출력된다.

  

### **자료와 함께 리턴**

`return`+ `자료`: 자료를 가지고 리턴한다.(돌아간다.)

```py

# 함수를 정의한다.
def return_test():
    return "B"

# 함수를 호출한다.
str = return_test()
print(str)

# 가장 일반적인 방식
def return_test2():
    a = 3 + 2
    return a

value = return_test2()
print(value)

```

  

### **아무것도 리턴하지 않기 = None**

  

파이썬에서 **None**은 '없다'라는 의미

```py

def return_test():
    return
value = return_test()

print(value)

```

  

## 함수의 활용

  

### 재귀함수

재귀: 자기 자신을 호출하는 것

- 재귀함수의 문제점

    - 상황에 따라 같은 내용을 기하급수적으로 반복함 → ****메모화** 사용으로 해결

**메모화**

: 재귀 함수와 함께 많이 사용되는 방법

- 같은 값을 반복해서 구하지 않고 딕셔너리 자료형에 저장 → 메모 변수

- 새로운 값만 계산할 수 있게 코딩

  

**조기 리턴**

    - 코드 중간에 키워드 `return` 사용하는 것

  
  

### 변수 사용 범위

1. 지역 변수 - 함수 내부에서만 사용

2. 전역 변수 - 프로그램 전체에서 사용

    - 함수 내에서 지역 변수를 전역 변수로 선언하는 방법 - 키워드 `global`

```py

def test():
    global s
    s = "지역변수"
    print()

s = "전역변수"
test()
print(s) # 지역변수로 출력됨
```

↪ `global` 선언을 했기에 위 와 아래의 `s`가 같은 변수가 되었다.

  

## 콜백 함수
: 함수의 매개변수에 사용하는 함수
- 함수라는 기능을 매개변수로 전달
```py
def repeat_10(x):
	for i in range(10): # calling a function
		x() 
def print_hi(): # print_hi = callback function
	print("hi")
repeat_10(print_hi) 
```

### 함수 map(콜백 함수, 리스트)
: 리스트 등 <u>시퀀스 자료형</u>에서 요소마다 **같은 기능을 적용**할 때 주로 사용
ex) 리스트의 요소를 함수에 넣고 리턴된 값으로 새로운 리스트로 구성

- list 사용 할 때:
	```py
	def sqr(x):
		return x ** 2
	list_a = [1, 2, 3]
	output_map = map(sqr, list_a) # sqr = callback function
	print(output_map) # generator
	print(list(output_map))
	```

- list 사용 안 할 때:
	```py
	def sqr(x):
		return x ** 2
	list_a = [1, 2, 3]
	for i in map(sqr, list_a):
		print(i)
	```

- 2개 이상의 시퀀스 자료형 처리 = zip 함수
```py
def test(x, y):
	return x + y

list_a = [1, 2, 3]
output_map = map(test, list_a, list_a)
print(output_map)
print(list(output_map))
```
python tutor: https://pythontutor.com/render.html#mode=display

```py
list_a = [1, 2, 3]
print([x + y for x, y in zip(list_a, list_a)])
```
### 함수 reduce
: 리스트와 같은 시퀀스의 모든 요소를 **누적적**으로 함수에 적용
```py
from functools import reduce

numbers = [1, 2, 3, 4, 5]
def multiply(x, y):
	return x * y

result = reduce(multiply, numbers)
print(result)
```

### 함수 filter
: 리스트의 요소를 함수에 넣고 **리턴된 값이 True**인 것으로 새로운 리스트 구성
```py
numbers = [1, 2, 3, 4, 5]
def is_even(num):
	return num % 2 == 0

evens = filter(is_even, numbers)
print(list(evens))
```

## 람다
- 간단한 함수를 쉽게 선언하는 방법
> lambda 매개변수: 리턴값
```py
test = lambda x, y: x + y
print(test(1, 3))

print((lambda x, y: x + y)(1, 3))
```

## 딕셔너리에서 함수 사용
> **리스트에서 사용했던 함수를 딕셔너리에서 사용하는 방법 **
### 함수 `min()` & `max()`
- 키워드 매개변수 key에 콜백 함수로 사용
- 콜백 함수의 매개변수 이름은 딕셔너리 이름과 같지 않아도 됨

### 함수 `sort()`
- 리스트 요소를 정려하는 함수
- 파괴적 함수이므로 원본 변경
```py
# ascending order
players = [{"name": "John",
			"height": 189},
			{"name": "Alice",
			"height": 178},
			{"name": "Eva",
			"height": 182}
			]
players.sort(key = lambda x: x["height"])
print(players)
```

```py
# descending order
players = [{"name": "John",
			"height": 189},
			{"name": "Alice",
			"height": 178},
			{"name": "Eva",
			"height": 182}
			]
players.sort(key = lambda x: x["height"], reverse=True)
print(players)
```
### 함수 `sorted()` - 모든 이터러블 사용 가능
- 리스트
```py
a = [1,45,72,23,8]
# ascending order
print(sorted(a))
# descending order
print(sorted(a, reverse = True))
```

- 튜플
```py
a = (1,45,72,23,8)
# ascending order
print(sorted(a))
# descending order
print(sorted(a, reverse = True))
```

- 딕셔너리
```py
a = { 
	"name": "John",
	"age": 19,
	"height": 79
}
# ascending order
print(sorted(a))
# descending order
print(sorted(a, reverse = True))
```

```py
a = "This is Python class"

print(sorted(a.split()))
```

# 파일 읽기
파일: 컴퓨터를 실행할 때 가장 기본이 되는 단위

파일의 종류:
1. 바이너리 파일: 컴퓨터만 이해할 수 있는 **이진 정보**로 저장된 파일
	- 정보를 효율적으로 저장하기위해 이진 정보로 저장
		ex) excel, word
  2. 텍스트 파일: 사람이 이해할 수 있는 문자열로 저장된 파일
	  - 메모장 열면 내용확인 가능한 파일
		  ex) 파이썬, HTML
	- 실제로는 바이너리 형태로 저장된 파일
		ex) 변환표준 - 아스키코드, 유니코드

## 텍스트 파일 처리
- 파일 처리를 위해서 일단 파일열기를 해야함
- 파일을 열면 파일 읽기 또느 파일 쓰기 할 수 있음

### 파일 열기 & 닫기
- 함수 `open()` - 파일 열기
> 파일 객체 = **open**(문자열: 파일경로, 문자열: 파일 열기 모드)

| 모드 |                설명                |
|:----:|:----------------------------------:|
|  w   |     write 모드(새로 쓰기 모드)     |
|  a   | append 모드(뒤에 이어서 쓰기 모드) |
|  r   |        read 모드(읽기 모드)        |

- 함수 `close()` - 파일 닫기

```py
# 파일 열기
file = open("base.txt", "w")
# 텍스트 쓰기
file.write("Hello python! Nice to meet you.")
# 파일 닫기
file.close
```
↪ 프로그램과 같은 폴더에 "basic.txt"라는 파일이 생성되고 그 파일안에 "Hello python! Nice to meet you."란 글이 쓰여 있다.

```py
# 파일 열기
file = open("base.txt", "r")
# 텍스트 읽기
contents = file.read()
print(contents)
# 파일 닫기
file.close()
```
↪ "Hello python! Nice to meet you."가 출력됨

- 키워드 `with`
: 파일을 열고 닫지 않는 실수를 방지하기위해 사용 → with 문이 끝나면 자동으로 파일이 닫힘
> with open (문자열: 파일 경로, 문자열: 모드) as 파일 객체: 문장

```py
# 파일 열기
with open("basic.txt", "w") as file:
	# 파일에 텍스트 쓰기
	file.write("Hello python! Nice to meet you.")
```

### 파일에 텍스트 쓰기

  

### 파일 읽기

  

### 키워드 with

  

### 텍스트 파일 한 줄씩 읽기

```sql

```

## [[Error]]