튜플: 함수와 함께 많이 사용되는 리스트와 비슷한 자료형, but **변경이 불가능***
- 리스트는 대괄호[ ] ↔ 튜플 소괄호( )
- 소괄호 없이도 튜플 생성 가능함
```py
list_a = [1, 2, 3]
tuple_a = (1, 2, 3)
print(list_a); print(tuple_a)
print(type(list_a)); print(type(tuple_a))

# indexing
print(list_a[0]) ; print(tuple_a[0])

# value change
list_a[0] = 10
print(list_a)

# make tuple without parenthesis
tuple_b = 1, 2, 3
print(tuple_b)
print(type(tuple_a))
```

## 여러 변수를 한 번에 할당
```py
# assigning multiple variables at once
[a, b] = [1, 2]
(c, d) = (3, 4)
print(a); print(b); print(c); print(d)
print(type(a)); print(type(b)); print(type(c)); print(type(d))
```

```py
# assigning values to multiple variables without parentheses
a, b, c, d = 1, 2, 3, 4
print(a); print(b); print(c); print(d)
print(type(a)); print(type(b)); print(type(c)); print(type(d))
```

## 값의 교환
- 튜플 특성을 이용하면 편리하게  값을 교환할 수 있음
	```py
	a, b = 1, 2
	print(a); print(b)
	
	a, b = b, a
	print(a); print(b)
	```

# 튜플 자료형
- **패킹**: <u>하나의 변수</u>에 *여러 개의 데이터*를 할당하는 개념
ex) 리스트 생성 
<br>
- **언패킹**: <u>하나의 변수에 들어있는 여러 개의 데이터</u>를 *각각의 변수로 반환*하는 개념  
ex) 튜플의 특성을 이용한 소괄호 없이 여러 변수에 값 할당, 전개 연산자 등
	- **데이터의 개수와 변수의 개수가 동일**하지 않으면 오류 발생

```py
# packing
z = [1, 2, 3] 
# unpacking
a, b, c = z 
print(z, a, b, c)
```

# 튜플과 함수
- 튜플은 함수 리턴에 많이 사용함

```py
# To create a user-defined function that returns a tuple
def test():
 return (1, 2)
a, b = test()
# a, b = (1, 2)
print(a); print(b)
```

## 함수 `enumerate()`
: <u>리스트의 값을 추출할 때 인덱스를 붙여 함께 출력</u>하는 함수 
- 사전적으로 '열거하다' 라는 의미
- 인덱스와 리스트의 값이 언패킹되어 추출
```py
tuple(enumerate([1, 2, 3]))
```

## 함수 `items()`
: <u>딕셔너리의 키와 값을 출력</u>하는 함수
```py
tuple({0:1, 1:2, 2:3}.items())
```

## 함수 `divmod()`
: 몫과 나머지를 출력하는 함수
```py
a, b = 63, 30
c, d = divmod(a, b) # c = quotient d = remainder
print(divmod(a, b))
```