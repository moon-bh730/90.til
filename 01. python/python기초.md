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

#### 1.3.3 list

> 여러개의 값을 하나의 변수에 저장
> []로 표시
> 인덱스는 0부터 시작한다.

##### 1.3.3.1 리스트 중복제거

 1. set 이용

    ``` python
    arr = [6, 5, 6, 4, 4, 1, 1, 2, 3, 9, 8, 7, 9, 8, 7] 
    
    result1 = set(arr) 
    print(f"set(arr) : {result1}") 	#중복 제거와 순서변경
    
    result2 = list(result1) # list(set(arr)) 
    print(f"list(set(arr) : {result2}")
    ```

    

 2. for 반복문

    ```python
    arr = [6, 5, 6, 4, 4, 1, 1, 2, 3, 9, 8, 7, 9, 8, 7] 
    result = [] # 중복 제거된 값들이 들어갈 리스트 
    for value in arr: 
        if value not in result: 
            result.append(value) 
            
    print(result)
    ```

    

 3. dictionary 이용

    ```python
    arr = [6, 5, 6, 4, 4, 1, 1, 2, 3, 9, 8, 7, 9, 8, 7] 
    result1 = dict.fromkeys(arr) # 리스트 값들을 key 로 변경 
    print(result1) 
    
    result2 = list(result1) # list(dict.fromkeys(arr)) 
    print(result2)
    ```

    

#### 1.3.4 tuple

> 리스트와는 다르게 불변한다. 즉 튜플을 정의 한 후에 수정,삭제,추가 불가
> 튜플은 리스트보다 더 적은 공간을 사용 
> 실수로 튜플의 항목이 손상될일(삭제, 변경)이 없다.
> 튜플을 딕셔너리의 키로 사용 할 수 있다. (딕셔너리 시간에)
> 함수의 인자들은 튜플로 전달된다.

### 1.2. 리스트 내포

```python
# 기본 형식
# 리스트 변수 = [표현식 for 변수 in 반복 가능한 대상]

# meter_list의 요소들을 for문을 돌면서 각각 100*i 연산을 시켜서 centi_meter_list에 저장
$ meter_list = [3, 7, 9, 10] 
$ centi_meter_list = [100*i for i in meter_list]

# 리스트 내포를 활용한 리스트 원소 제곱
$ meter_square_list = [i*i for i in meter_list]

# 리스트 내포에 조건 추가
# 리스트 명 = [표현식 for 변수 in 반복 가능한 대상 if 조건문]

# 리스트 내포를 활용한 홀수원소 단위 변환 (m -> cm)
$ centi_meter_list = [100*i for i in meter_list if i%2 != 0] 

# 리스트 내포를 활용한 이중 for문
# 1부터 10까지의 구구단을 출력하는 for문
$ result = [] 
$ for x in range(1, 10):     
$ 	for y in range(1, 10):
$ 		result.append(x * y)  
#-----------------------------------------
$ result = [x * y for x in range(1, 10) for y in range(1, 10)] 	# 바깥쪽의 for문이 앞쪽으로, 안쪽의 for문이 뒤쪽으로 가는 구조
#-----------------------------------------

$ result = [] 
$ for x in range(1, 10): 
$ 	if x%2 == 0: 		#짝수단만 처리
$ 		for y in range(1, 10): 
$ 			result.append(x * y) 
#-----------------------------------------
$ result = [x * y for x in range(1, 10) if x%2 == 0 for y in range(1, 10)] 		# 바깥쪽에 있는 for문 if문 순서대로 앞쪽으로 간다
#-----------------------------------------
```



## 99 함수



### append()

> 리스트에 값 추가

```python

# 마이너스 부호를 넣어서 음수로 바꾼다
m.append(-int(i))
```



### del [객체]

> ※ 객체란 파이썬에서 사용되는 모든 자료형
>
>  객체의 부분만 삭제시는 remove를 사용한다.

```python
# 슬라이싱으로 여러개 삭제도 가능
$ a = [1, 2, 3, 4, 5]
$ del a[2:]
$ a
	[1, 2]
```

### join()

>join 함수는 매개변수로 들어온 리스트에 있는 요소를 하나의 문자열로 합쳐서 반환하는 함수
>
>''.join(리스트)
>
>'구분자'.join(리스트)

### strip()

> 공백을 제거한다.
>
> 인수 할당시 해당 값을 제거한다.
>
> lstrip(), rstrip()

### turtle

> 화면에 그림을 그리는 파이썬 기본 모듈(painter 느낌?) import 필요
>
> 속성 : 위치, 방향, 펜
>
> 

### map()

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

