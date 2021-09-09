## 1. 깃허브 설치

### 1.1 깃 계정 정보 설정

 - ```bash
   // 1. 사용자 정보설정
   git confit --global user.name "kimmimi"
   git confit --global user.email "asdf@asdf.com"
   ```
   
- ```bash
  // 2. 편집기 설정(필수 사항은 아님)
  $ git config --global core.editor emacs
  
  // 노트패드를 편집기로 쓴다면
  // x86
  $ git config --global core.editor "'C:/Program
  Files/Notepad++/notepad++.exe' -multiInst -nosession"
  // x64
  $ git config --global core.editor "'C:/Program Files
  (x86)/Notepad++/notepad++.exe' -multiInst -nosession"
  ```

  

- ``` bash
  // 설정내용의 확인
  $ git config --list
  ```

  

## 2. 저장소 만들기

### 2.1 저장소 만들기

#### 2.1.1 깃 초기화 명령어

```bash
git init
```

- init 명령은 숨김 속성을 가진  [.git] 폴더를 생성 한다

#### 2.1.2 깃 상태 명령어

- status와 log
  - status 결과에 untracked files:는 한번도 버젼관리 하지 않은 파일을 말한다.
  - untracked files:은 (working directory = work tree)영역에 생성됨을 말한다.
  - git log 탈출은 q 키
  
  ```bash
  git log -p -2
  # 여기서 -p는 각 커밋의 diff 결과를 보여줍니다.
  # -2 는 최근 두개의 결과만를 보여줍니다.
  ```
  
  p		각 커밋에 적용된 패치를 보여준다.
  stat		각 커밋에서 수정된 파일의 통계정보를 보여준다.
  shortstat	stat 명령의 결과 중에서 수정한 파일, 추가된 라인, 삭제된 라인만 보여준다.
  name-only	커밋 정보중에서 수정된 파일의 목록만 보여준다.
  name-status	수정된 파일의 목록을 보여줄 뿐만 아니라 파일을 추가한 것인지, 수정한 것인지, 
  
  ​							삭제한 것인지도 보여준다.
  graph		브랜치와 머지 히스토리 정보까지 아스키 그래프로 보여준다.
  pretty		지정한 형식으로 보여준다. 이 옵션에는 oneline, short, full, fuller, format이 있다. 
  
  ​					format은 원하는 형식으로 출력하고자 할 때 사용한다.

### 2.2 저장소 작업(버젼관리)

- git add [file name]
  - (working directory = work tree) 파일을 스테이지로 올린다.
  
  - 스테이지의 파일은 ""이 파일은 버젼을 만들 수 있다" 라는 의미이다.
  
    ```bash
    # add를 취소할때(working directory에서 내린다)
    git restore <file>
    ```
  
    
  
- commit, push, pull 이 명령들을 어떤 작업이라 해야할지?

  - 워킹영역과 스테이지에 한번에 올리는 명령

    ```bash
    #기본형
    git commit -m [description]
    
    #워킹영역과 스테이지에 한번에 올리는 명령(add 안해도 되는건가? 한번 테스트 해볼것!!)
    git commit -am
    ```

    

### 2.3 원격과 지역 장소 연결관리

#### 	2.3.1 지역장소의 초기화

빈 레포 만들고 로컬 폴더로 연결하는 연습

```bash 
git init [폴더명]
```

#### 	2.3.2 원격 저장소 연결(로컬과 원격을 연동하는것!! 현재 내가 제일 헷갈려 하는 부분 )

```bash
# 저장소 연결
git remote add original [저장소 주소]

# 저장소 연결 확인
git remote -v
```



### 2.4 저장소 삭제하기

레보지트리 삭제

레포지트리 로컬폴더로 내리기 / 로컬폴더 레포지트리에 올리기

push, pull : 원격 레포에 올리고 가져오는 명령

```bash
git push	#올리기
git push origin main		#main을 master로 하기도 하고 이걸쓸때 헷갈리는 포인트-확인할것!!
git pull	#가져오기
```

다른분 레포를 가져와서 풀로 연동하는 연습!!

## 3. 브랜치(분기된 새로운 버전의 관리로 깃허브의 꽃)

브랜치 생성

```bash
git branch [브랜치 이름]
```

브랜치 이동

```bash
git checkout [브랜치 이름]
```

브랜치 생성 및 이동

```bash
git checkout -b [브랜치 이름]
```

브랜치 조회

```bash
git  branch
```

브랜치 merge

```bash
(master) $ git merge [브랜치 이름]
```

- master로 병합하려는 경우 master브랜치에서 명령어를 작성 해야함!!
- [브랜치 이름]을 해당 브랜치로 병합하는 명령어 이기 때문

브랜치 삭제

```bash
git branch -d [브랜치 이름]
```



## 4. 깃허브 백업관리

> 



## 5. 깃허브 협업

### 5.1. 과거 특정 시점으로 되돌리기

> git checkout [commitID]
> 돌아간 이후에도 작업했던 내역은 모두 볼 수 있다
> git log --all 또는 git log --all --oneline

### 5.2. 되돌린작업(checkout )을 취소할때

> git checkout master

## 6.  .gitignore

> 기본 규칙
>
>  - 아무것도 없는 라인이나, `#`로 시작하는 라인은 무시한다.
> - 표준 Glob 패턴을 사용한다.
> - 슬래시(/)로 시작하면 하위 디렉토리에 적용되지(Recursivity) 않는다.
> - 디렉토리는 슬래시(/)를 끝에 사용하는 것으로 표현한다.
> - 느낌표(!)로 시작하는 패턴의 파일은 무시하지 않는다.



## 99. 기타

1) 웹에서 파일 다운받기

   >  ***Raw*** 버튼을 누르고 열린 화면에서 윈도우 [Ctrl+S], 맥 [Cmd+S]
   
2) VisualStudio Code에서 Git Graph애드온은 Branch를 모두 보이도록 하고 관리가 가능하다.(막연하던게 눈에 보여서 이해가 쉽도록 해준다.)
