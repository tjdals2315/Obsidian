### 리스트 생성 - 대괄호, 쉼표, 모든 자료형
- **대괄호** 안에 개별 값들과 쉼표로 구분하여 저장
- 개별 값들을 **요소(item)**라고 부름

### 리스트 내부 요소: 인덱싱, 슬레이싱 가능
==리스트 내부 요소는 변경 가능하다==

## 인덱싱
```py
list_a = [[1, 2, 3, 4], "Hello", True]
print(list_a[0])
print(list_a[0][2]) # list안의 list에 개별적 접근 가능
print(list_a[1][2])
```

## 슬라이싱

```py
list_a = [[1, 2, 3, 4], "Hello", True]
print(list_a[0:2])
print(list_a[:2])
print(list_a[1:])
```

## 음수 인덱스
```py
list_a = [[1, 2, 3, 4], "Hello", True]
print(list_a[-1])
print(list_a[-2])
print(list_a[-3])
```

## 증가값
- [시작:끝:증가폭]
- [ : : -1]를 입력하면 리스트를 반대로 나타낼 수 있다.
```py
weather = ["🌈", "🌤️", "⛅️", "🌦️", "🌩️", "🌨️", "⛄️"]
print(weather[::2])
print(weather[::-1])
```

## 리스트 요소 변경

리스트 요소 변경을 위해 <u>**먼저 리스트를 꺼내서 원하는 곳에 할당 한 후**</u> 출력한다.
```py
list_a = [[1, 2, 3, 4], "Hello", True]

list_a[2] = False
print(list_a)
# list 안에 list 변경
list_a[0][2] = 9
print(list_a)
```

### <u>리스트 연산자</u>
- 연결 `+`
- 반복 `*`
	```py
	# 리스트 합치기
	list_1 = [1,2,3]
	list_2 = [4,5,6]
	print(list_1 + list_2) # 비파괴적 처리
	# 리스트 반복
	print(list_1 * 3) # 비파괴적 처리
	
	```
### <u>리스트 길이</u>
- 요소의 개수 `len()`
	```py
	list_3 = [1, 2, 3, 4, 5, 6, 7, 8, 9,]
	# 리스트 길이
	print(len(list_3))
	```

### <u>리스트 요소 추가</u>
- `append()`
	- 리스트 **뒤**에 추가
	- 추가할 값을 입력
	- 원본의 변화 있음 (**파괴적 처리**)
	```py
	list_1 = [1,2,3]
	# .append 뒤에 추가 = 요소(개별값)
	list_1.append(7)
	print(list_1) # 파괴적 처리
	```
- `insert()`
	- 리스트 **중간**에 추가
	- 추가할 **위치**와 값을 입력
	- 원본의 변화가 있음 (**파괴적 처리**)
	```py
	list_2 = [4,5,6]
	# .insert 중간에 추가 = 원하는 위치(인덱스 번호)에 추가 = 요소(개별값)
	list_2.insert(3, 9) # 인덱스 3번 위치에 9라는 값(요소) 추가
	print(list_2) # 파괴적 처리
	```
- `extand()`
	- 리스트 연결 `+` 연산자와 기능은 같지만, 원본의 변화가 있음 (**파괴적 처리**)
	```py
	list_1 = [1, 2, 3]
	list_2 = [4, 5, 6]
	# .extand() + 연결 = 리스트 전체 요소
	list_1.extend(list_2)
	print(list_1) # 파괴적 처리
	```

	비파괴적 처리 예시
	```py
	list_1 = [1, 2, 3]
	list_2 = [4, 5, 6]
	print(list_1 + list_2)
	
	print(list_1)
	print(list_2)
	```

### <u>리스트 요소 제거</u>
#### <span style="background:#d2cbff">인덱스 번호</span>
- 키워드 `del`
	- 인덱스 번호로 제거
	- 인덱스 번호 범위로 한 번에 제거
	```py
	# del 키워드 = delete
	list_1 = [1, 2, 3, 4, 5, 6, 7]
	del list_1 [2]
	print(list_1)
	
	list_1 = [1, 2, 3, 4, 5, 6, 7]
	del list_1 [1:5]
	print(list_1)
	```
- 함수 `pop()`
	- 인덱스 번호로 제거
	```py
	# pop 함수
	list_1 = [0, 1, 2, 3, 4, 5]
	list_1.pop(2)
	print(list_1)
	```

#### <span style="background:#d3f8b6"><span style="background:#d2cbff">값</span></span>
- 함수 `remove()`
	- **특정 값**을 지정하여 제거
	- **첫 번째** 나오는 값을 제거
	- **여러 개를 제거**하기 위해서는 **<u>반복문</u>** 사용해야 함

	```py
	# remove 함수 - 값으로 제거
	list_1 = [1, 2, 3, 4, 5, 6, 7]
	list_1.remove(4)
	print(list_1)
	```

#### 리스트 비우기
- 함수 `clear()`
	- 리스트 내부 요소를 **모두 제거**
	- 내용 비우기와 같음

	```py
	# clear 함수 - 비우기
	list_1 = [1, 2, 3, 4, 5, 6, 7]
	list_1.clear()
	print(list_1)
	```

### <u>리스트 정렬</u>
- 함수 `sort()`
	- 기본적으로 **오름차순(낮은값 →높은값)** 정렬
	- 내림차순 정렬을 하기 위해서 매개변수 **reverse=True** 입력
	```py
	# 오름차순
	score = [75,55,40,90,100]
	score.sort()
	print(score)
	
	# 내림차순
	score.sort(reverse=True) # reverse 매게변수
	print(score) #내가 가진 리스트 값을 정렬하고 싶으면 sort 사용
	```

### <u>리스트 확인</u>
- 연산자 `in` / `not in`
	- 특정 값이 리스트 안에 있는지 / 없는지 확인
	- 결과는 bool 형태임 (True/False)

## 전개연산자

: 리스트 안의 요소를 순서대로(순차적으로) 꺼내서 사용 가능  

`*list`
1. 리스트 안에서 사용하는 경우
	- 리스트형
	- 원본에 영향 없음 (비파괴적 처리)
	```py
	a = [1,2,3]
	b = [*a, 4]
	print(a) # a는 변하지 않음 (비파괴적)
	print(b)
	```
2. 함수 매개변수 위치에서 사용하는 경우
	- 리스트 안의 요소 값들이 순서대로 적용 = 가변매개함수
	```py
	a = [1, 2, 3, 4]
	print(a)
	print(*a) # 매개변수 이름에 *를 쓰면 -> 가변 매개변수(값의 개수 제한이 없음)
	print(1,2,3,4) #print가 대표적인 가변변수
	```

## 이차원 리스트
- 리스트를 효율 적으로 활요하기 위해, <u>여러개의 리스트</u>를 **하나의 변수**에 할당
- 리스트 안에 리스트
	```py
	언어영역 = [100,70,60,80]
	수리영역 = [50,100,80,40]
	과학영역 = [70,80,90,80]
	
	scores = [언어영역, 수리영역, 과학영역]
	print(scores)
	print(scores[0][2])
	```

	```ad-Key
	이차원 리스트 : **세로(행). 가로(열)**
	
	example)
	![[FDE5FD3B-23F6-48B3-8F3A-F9EC405E3BCA_1_105_c.jpeg]]
	
	```

