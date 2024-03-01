# <font color="#0070c0">Syntax error(구문 오류)</font>
- 프로그램 **실행 전**에 발생하는 오류
- 문법 오류 - 오타가 일반적
- 파싱 오류
	- 오류 내용에서 캐럿 기호(^)가 표시되는 부분을 직접 해결해야 프로그램 실행됨
	- 예외 처리 <u>불가능</u>

# <font color="#0070c0">Exception(예외)</font>
-  문장이나 표현식이 <u>문법적으로 오류 없이</u> 작성되더라도 프로그램 **실행 중**에 발생하는 오류
- **runtime error(런타임 오류)**
-  <u>예외 처리로 해결 가능</u>

## NameError
:존재하지 않는 변수를 호출할 때 

## IndexError
: 자료형 인데스 범위를 벗어날 때

- 리스트의 없는 요소를 사용하면 발생하는 오류
	```py
	list_a = [[1, 2, 3, 4], "Hello", True]
	list_a[4]
	```

## ZeroDivisionError
: 0으로 숫자를 나눌 수 없을 때


## Value Error
: 변환할 수 없는 문자나 숫자를 변환할 때

- 숫자가 아닌 값을 숫자로 변환하는 경우
	```py
	int("안녕")
	```
-  실수를 정수로 변환하는 경우
	```py
	int("2.3")
	```

## FileNotFoundError
: 존재하지 않는 파일을 호출할 때

# 키워드 `pass` 
- 에러 발생하지 않도록 아무것도 하지 않고 지나가라는 의미로 pass 사용 가능
- 나중에 구현하고자하는 구문을 비워두는 경우 사용
	```py
	no = input("숫자(정수)를 입력하세요> ")
	last_no = int(no[-1])
	
	if last_no % 2 == 0:
		pass
	
	else:
		pass
	```

⟺ `raise NotImplementedError`
		: 아직 구현되지 않은 부분임을 강조하기 위해 일부러 **에러 발생**

```py
no = input("숫자(정수)를 입력하세요> ")
last_no = int(no[-1])
if last_no % 2 == 0:
  raise NotImplementedError
else:
  raise NotImplementedError
```




# <font color="#0070c0">예외 처리</font>

## 기본 예외 처리 - 조건문 사용
- `isdigit()` 함수: 문자열이 숫자로 인식될 수 있는지 확인

## try ~ except 구문
- 파이썬 예외 처리 기본 문법
- 예외 발생이 예상되는 코드는 `try` 문에, 예외 발생 시 실행하는 코드는 `exception` 문에 작성

## try ~ except 구문 + pass 키워드
- 예외가 발생하면 일단 처리해야 함
- 해당 코드가 중요하지 않다면 프로그램 강제 종료를 예방하기 위한 목적으로 사용
	- except 구문에 pass 키워드 이력
	- 어떤 명령어도 실행되지 않고 강제 종료도 되지 않음
- pass 없이 아무 것도 입력하지 않으면 구문 오류 발생

## try ~ except ~ else 구문
- try ~ except 구문 뒤에 **else 구문** 붙여 사용하면 예외가 발생하지 않았을 때 실행할 코드 지정
(이때, 예외 발생 가능성 있는 코드 → try 구문 내부에 넣음
나머지 → 모두 else 구문으로 빼는 경우 많음)
![[Pasted image 20240302013656.png]]

## try ~ except ~ else ~ finally 구문
- finally 문은 예외 처리 구문에서 **가장 마지막**에  사용할 수 있는 구문
- 예외 발생 여부와 관계없이 **무조건 실행할 경우** 사용

## try, except, finally 구문
- try 구문은 **단독으로 사용할 수 없으며**, 반드시 <u>except 구문 또는 finally 구문과 함께 사용</u>
- else 구문은 반드시 **except** 구문 뒤에 사용

⇒ **try + except / try + finally** 조합으로 사용해야 함 
- try + except 구문 조합
- try + except + else 구문 조합
- try + except + finally 구문 조합
- try + except + else + finally 구문 조합
- try + finally 구문 조합

## finally 구문 사용
- 반복문이나  함수 내부에서 finally 구문 사용하면 코드 간결해짐
- try 구문에서 파일 닫기 실행하는 경우
	- 예외 발생이 없으면 파일 닫힘
	- 파일 닫기 전에 예외 발생하면 파일이 닫히지 않는 문제가 발생함으로 finally 구문으로 무조건 파일 닫기 실행
1. 함수 내부에서 try 구문에서 return 키워드 사용
	- try 구문 중간에서 return 키워드 탈출해도 finally 구문 무조건 실행
	- return 키워드로 탈출할 때마다 파일 닫기 작성하면 코드가 복잡해지므로, finally 구문으로 파일 닫기 하면 코드가 간결해짐
	 (보통 파일 처리는 with 문이 더 편함
	 - 데이터 분석에서는 외부 자원이나 네트워크 등 접속 해제 이슈가 있을 때 많이 사용

2. 반복문과 함께 사용
	- 반복문에서 break 키워드로 try 구문을 탈출해도 finally 구문은 **무조건 실행**

# 예외 객체
: 현실에서 어떤 사건이 발생하면 누가, 언제, 어디서라는 정보가 생기는 것처럼, 예외 발생 시 예외 정보가 저장되는 곳
- 클래스 Exception
	- 모든 예외의 어머니라 부름
	- ValueError, IndexError 등 모두 포함

## 예외 구분
- 예외 객체 사용하면 except 구문을 if 조건문처럼 사용해 예외를 구분할 수 있음 