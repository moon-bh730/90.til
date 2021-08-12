

# Numpy



## 1. Numpy란?

	- 다차원 배열을 효과적으로 처리 할 수 있도록 도와주는 도구
	- 파이썬 list에 비해 빠르고 강력함

## 2. Numpy의 차원

	- 1차원 축(행) : axis0  => Vector
	- 2차원 축(열) : axis1  => Matrix
 - 3차원 축(채널) : axis2  => Tensor(3차원 이상)

## 3. 기본 명령어

```python
# 선언
import numpy as np

# 0~3배열 만들기
array1 = np.arange(4)

# 0 float 배열 생성
array2 = np.zeros((4,4),dtype=float)

# 1 string 배열 생성(0,1만 있고 2,3,4는 없다)
array3 = np.ones((4,4),dtype=str)

# 0~9 까지 랜덤하게
array4 = np.random.randint(0,10,(3,3))

# 평균이 0, 표준편차 1인 표준 정규분포 배열 생성
array5 = np.random.normal(0,1, (3,3))

# 배열 합치기
array1 = np.array([1,2,3])
array2 = np.array([4,5,6])
array3 = np.concatenate([array1, array2])

# 가로축 합치기
array1 = np.array([1,2,3,4])
array2 = array1.reshape((2,2))
print(array2)

#세로축 합치기
array1 = np.arange(4).reshape(1,4)
array2 = np.arange(8).reshape(2,4)
print(array1)
print(array2)
array3 = np.concatenate([array1, array2],axis=0)
print(array3)

#2차원 배열의 행열 값 구하기
c = np.array([[0, 1, 2], [3, 4, 5]])  # 2 x 3 array

# 행의 갯수
len(c)
# 열의 갯수
len(c[0])

#배열의 차원과 크기값
print(d.ndim)		#배열의 차원수 리턴
print(d.shape)		#Vector(행), Matrix(열), Tensor(채널)
```

## 4. 넘파이 파일처리(파일 save, load)

```python
import numpy as np

##### 저장
array = np.arange(0,10)
#print(array)
np.save("saved.npy",array)

#### 불러오기
result = np.load("saved.npy")
print(result)

```

## 5. 연산과 함수

```python
### 배열에 사칙연산이 가능하다
import numpy as np

array = np.random.randint(1, 10, size=4).reshape(2,2)
print(array)

result_array = array * 10
print(result_array)
```

```python
### 배열과 배열의 연산
import numpy as np

array1 = np.arange(4).reshape(2, 2)
array2 = np.arange(2)

array3 = array1 + array2
print(array3)
```

> numpy.concatenate((a1,a2, ...), axis=0, out=None, dtype=None, casting="same_kind")
>
> - a1, a2,		: 배열 순서
>
>   ​					배열은 *축* (기본적으로 첫 번째)에 해당하는 차원을 제외하고 동일한 모양을 가져야 합니다
>
> - axis            : 배열이 결합될 방향.  axis가 None이면 아래에 붙는다. 기본값은 0도 아래
>
>   ​                      1일경우 우측에 붙는다.
>
> - out
>
> - dtype
>
> - casting      :{'no', 'equiv', 'safe', 'same_kind', 'unsafe'}, 선택 사항
>
>   발생할 수 있는 데이터 캐스팅의 종류를 제어합니다. 기본값은 'same_kind'

```python
### 형태가 다른 배열도 브로드캐스팅(배열을 동적 변환) 하여 연산한다
import numpy as np

array1 = np.arange(0,8).reshape(2, 4)
array2 = np.arange(0,8).reshape(2, 4)
array3 = np.concatenate([array1, array2], axis = 0)
print(array3)
array4 = np.arange(0,4).reshape(4,1)
print(array4)
print(array3+array4)
```

```python
### 마스킹 연산 - 조건을걸어 각 배열방에 True/False값을 넣어준다.
import numpy as np

array1 = np.arange(16).reshape(4, 4)
print(array1)

array2 = array1 < 10
print(array2)

# 활용(True일때 100을 넣는다) - 이미지 처리에서 많이 수행된다.
array1[array2] = 100
print(array1)
```

## 6. 넘파이 집계함수

```python
import numpy as np

array = np.arange(16).reshape(4,4)

print("최대 : ",np.max(array))
print("최소 : ",np.min(array))
print("합계 : ",np.sum(array))
print("평균 : ",np.mean(array))
print("표준편차 : ",np.std(array))
```

```python
# 부분계산 - 특정한 열, 행의 계산
import numpy as np

array = np.arange(16).reshape(4,4)
print(array)

print("합계 : ",np.sum(array, axis=0))
```

## 7. 슬라이싱

> ":" 를 써서 범위지정 하는게 슬라이싱

```python
a = np.array([[0, 1, 2, 3], [4, 5, 6, 7]])

	array([[0, 1, 2, 3],
    	   [4, 5, 6, 7]])
    
a[0, :]  # 첫번째 행 전체

	array([0, 1, 2, 3])
    
a[:, 1]  # 두번째 열 전체

	array([1, 5])

a[1, 1:]  # 두번째 행의 두번째 열부터 끝열까지

array([5, 6, 7])
    
a[:2, :2]

	array([[0, 1],
    	   [4, 5]])
```

## 8. 인덱싱

> x[i, k] - i는 행, k는 열 행태를 인덱싱이라 한다.

```python
a = np.array([[0, 1, 2], [3, 4, 5]])
a
	array([[0, 1, 2],
    	   [3, 4, 5]])

a[0, 0]  # 첫번째 행의 첫번째 열
a[0, 1]  # 첫번째 행의 두번째 열
a[-1, -1]  # 마지막 행의 마지막 열
```



## 9. 넘파이 자료형

> `넘파이의 ndarray`클래스는 원소가 모두 같은 자료형이어야 한다
>
> b		불리언					b (참 혹은 거짓)
> i		정수						i8 (64비트)
> u		부호 없는 정수		u8 (64비트)
> f		부동소수점				f8 (64비트)
> c		복소 부동소수점	c16 (128비트)
> O		객체						0 (객체에 대한 포인터)
> S		바이트 문자열		S24 (24 글자)
> U		유니코드 문자열	U24 (24 유니코드 글자)

```python
x = np.array([1, 2, 3], dtype='f')			#dtype으로 자료형을 정의한다.
```



## 10. 배열의 생성

### 10.1. zeros, ones

> zeros는 모든 값이 0 인 배열, ones는 1인 배열을 생성

```python
a = np.zeros(5)
a

	array([0., 0., 0., 0., 0.])
```



### 10.2. arange

> 조건에 따라 증가하는 수열을 만든다
>
> arange([시작값],[끝값],[증감값])

```python
np.arange(10)

	array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])


np.arange(3, 21, 2) 

	array([ 3,  5,  7,  9, 11, 13, 15, 17, 19])
```





##  11. 행과 열 바꾸기

> 2차원 배열의 transpose 연산은 행과 열을 바꾼다
>
> 메서드가 아닌 T속성으로 구현한다.

```python
A = np.array([[1, 2, 3], [4, 5, 6]])
A.T
```



## 12. RESHAPE

>  현재의 배열의 차원(1차원,2차원,3차원)을 변경하여 행렬을 반환하는 함수

### 12.1. 1차원 2차원 변환

```python
import numpy as np

a = [1,2,3,4,5,6,7,8]
b = np.reshape(a,(2,4))
c = np.reshape(a,(4,2))
print(b)
print(c)
```

### 12.2. 3차원 변환

```python
a = np.arange(1,9)
b = a.reshape(2,2,2)
b

# 3차원에서 첫 번째 행렬의 1행 2열 값 인덱싱
b[0][0,1]
# 21.08.12 인덱싱과 슬라이싱의 차이를 아직 모르겠다
```

### 12.3. `reshape`에서 -1 의 의미(=알아서 자동으로 해라)

> 변경된 배열의 ‘-1’ 위치의 차원은 “원래 배열의 길이와 남은 차원으로 부터 계산”이 된다는 뜻

#### 12.3.1. 행의 위치에 -1

> 행(row)의 위치에 -1을 넣고 열의 값을 지정하면 변환될 배열에 행의 수는 자동 지정

#### 12.3.2. 열의 위치에 -1

> 열(col)의 위치에 -1을 넣고 열의 값을 지정하면 변환될 배열에 열의 수는 자동 지정

#### 12.3.3. reshape(-1)

> 1차원 배열로 변환



### 12.4. 1차원 배열로 만들어 주는거

> 다차원 배열을 무조건 1차원으로 만들기 위해서는 `flatten` 나 `ravel` 메서드

```python
a.flatten()

a.ravel()
```



## 13. 배열의 정렬

> 21.08.13 이건 필요한거다 싶을때 정리할 예정



## 14. Random 난수

> 시드설정 -> 난수발생
>
> 시작 숫자를 시드(seed)라고 한다. 시드값은 최초 한 번만 정해주면 된다.
>
> 생성된 난수는 다음번 난수 생성을 위한 시드값이 된다.

```python
np.random.seed(0)	#시드값 >= 0
np.random.rand(5)
```



