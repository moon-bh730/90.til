## 멀티라인 편집

>  현재 커서 에서 [Ctrl + Alt + ↑or ↓] 를 입력하면 동일선상에 멀티커서가 생기며 코드를 한 번에 편집가능



## 단축기능 요약

----강력한 에디팅 기능------------
Alt + Shift + ↑or ↓  		해당 영역 아래로 또는 위로 복제 
Ctrl + D  			현재 커서가 위치해 있는 단어와 일치하는 선택하기
					동일단어 일괄 바꾸기 가능!!
Alt + 				클릭  커서 삽입하기
					삽입된 커서에 일괄 작업 가능!!

----강력한 화면 구성 기능-------------
Ctrl + B  			왼쪽 탐색기 토글
Ctrl + ` 			터미널 보이기 / 숨기기 
F11 				풀 스크린 모드(전체화면) 
Ctrl + F4 			현재 코드창 닫기 
Ctrl + \ 			코드 창 나누기(split)
코드창의 상단 탭 드래그시 화면 나누어보기 가능
	좌측이나 하단으로 나눠 볼 수있고 원래자리에 놓으면 처음대로 됨

---- 그냥 알아두면 좋은 기능
Ctrl + /  			해당 영역 주석처리  
(Ctrl + K) + (Ctrl + T)  	VSC 테마설정(다크, 라이트 등) 
Ctrl + 				비율확대(줄이고 싶으면  ctrl -)
Shift + Alt + → , ←  		선택 영역 확장하기 
Shift + Alt + F 		도큐먼트 포맷화하기
Ctrl + ↑or ↓  		스크롤 올리기 / 내리기 



## 디버그 모드 사용하기

> [ctrl + c] 활성화된 터미널은 종료한다!(충돌 발생 방지 차원)
>
> [F9] 해당위치에 브레이크 포인트 설정
>
> [F5] 계속/일시중지
>
> [F10] 단위실행
>
> [F11] 단계정보
>
> [shift+F11] 단계출력
>
> [ctrl+shift+F5] 다시시작
>
> [shift + F5] 디버그모드 종료
>
> 

```python
# launch.json 참고 사이트
# https://demun.github.io/vscode-tutorial/debug/#launchjson
# launch.json > configurations 에 추가
{
            "name": "Python: Current File (integrated)",
            "type": "python",
            "request": "launch",
            "program": "${file}",
            "console": "integratedTerminal",
            "stopOnEntry": true
},
```

