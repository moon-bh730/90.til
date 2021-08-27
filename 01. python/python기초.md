# python

## 1. 기초

### 	1.1 기본문법

#### 		1.1.1 세미콜론

``` python
# 여러 명령을 한줄에 쓸때 구분자로 쓰인다.
print('hello world!'); print('1234')
```

### 	1.2 숫자계산

#### 		1.2.1 사칙연산

```python
# 4칙 연산, +, -< *, /, %, //
# % - module, 나머지
5/2 ; 5%2 ; 5/2; 6%3 ; 2**10
```



### 	1.3 변수와 입력

#### 			1.3.1 변수

​					- 영문 문자와 숫자를 사용할 수 있습니다.

​					- 대소문자를 구분합니다.

​					- 문자부터 시작해야 하며 숫자부터 시작하면 안 됩니다.

​					- _(밑줄 문자)로 시작할 수 있습니다.

​					- 특수 문자(+, -, *, /, $, @, &, % 등)는 사용할 수 없습니다.

​					- 파이썬의 키워드(if, for, while, and, or 등)는 사용할 수 없습니다.

```python
# 파이썬에서는 변수 여러 개를 한 번에 만들 수도 있습니다.
x, y, z = 10, 20, 30
x, y, z
```

```python
# 변수 삭제는 del을 사용
del z
print(z)
```

#### 			1.3.2 입력

```python
x=input()
```



## 99 함수



### strip()

> 공백을 제거한다.
>
> 인수 할당시 해당 값을 제거한다.
>
> lstrip(), rstrip()

## map()

> 리스트의 형변환
>
> 동일한 기능인 List Comprehension 방법도 참고로 정리

```python
# map 기본형식
$ originalList = ['2', '4', '6', '8', '10', '12']
$ intList = list(map(int, originalList))
$ print(intList)
	[2, 4, 6, 8, 10, 12]

 # comprehension 형식
$ originalList = ['2', '4', '6', '8', '10', '12']
$ intList = [int(x) for x in originalList]
$ print(intList)
	[2, 4, 6, 8, 10, 12]
    
 # 맵으로 입력 받기
 a = map(int, input().split())
    
 # lambda 매핑
for li in map(lambda x : x+1 , users):
	print(li)
    
 # 일반 함수 매핑
for name in map(convert_to_name, users):
	print(name)
   	# convert_to_name의 인자로 users의 요소가 넘어감.
	# 각각의 요소에 대해 함수 진행 후 return
```

