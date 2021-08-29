# 1. matplotlib

## 1.1. plot함수에 그래프 그리는 3단계

> 1. 라이브러리 부르기
>
>    import matplolib.pyplot as plt
>
> 2. plot 함수에 데이터 입력하기
>
>    plt.plot([x축 데이터],[y축 데이터])
>
> 3. 그래프 보여주기
>
>    plt.show()



### bar()

> bar(막대를 표시할 위치, 막대의 높이)

### barh()

> 수평 막대그래프로 표현

```python
plt.barh(range(101),result)
```



### legend()

> 레이블 값이 범례로 표시

