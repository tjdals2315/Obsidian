# Syntax error(구문 오류)
- 프로그


## Value Error
- 숫자가 아닌 값을 숫자로 변환하는 경우
	```py
	int("안녕")
	```
-  실수를 정수로 변환하는 경우
	```py
	int("2.3")
	```

## IndexError
- 리스트의 없는 요소를 사용하면 발생하는 오류
	```py
	list_a = [[1, 2, 3, 4], "Hello", True]
	list_a[4]
	```

### 키워드 `pass` 
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


