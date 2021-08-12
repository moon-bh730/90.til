## 1. 깃허브 설치

### 1.1 깃 계정 정보 설정

 - ```bash
   git confit --global user.name "kimmimi"
   git confit --global user.email "asdf@asdf.com"
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

    

  - push, pull : 원격 레포에 올리고 가져오는 명령

    ```bash
    git push	#올리기
    git pull	#가져오기
    ```

    

### 2.3 원격과 지역 장소 연결관리

#### 	2.3.1 지역장소의 초기화

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

레포지트리 로컬폴더로 내리기

로컬폴더 레포지트리에 올리기

## 3. 브랜치

- 분기된 새로운 버전의 관리

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

## 5. 깃허브 협업

## 6. 깃허브 이론

- [(working directory = work tree)] - [스테이지] - [저장소]

<img src="https://git-scm.com/book/en/v2/images/lifecycle.png" alt="파일의 라이프사이클." style="zoom: 67%;" />

<img src="https://media.vlpt.us/images/janeljs/post/2654de26-d74b-4618-9a3c-96668a4e2a53/image.png" alt="Git의 기본 개념들 (1) (working directory, staging area, remote)" style="zoom: 67%;" />



#### 6.1 스테이지와 커밋



