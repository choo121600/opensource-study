# opensource-study


## GitHub 저장소 이해
```
Project Repository
    │
    ├── upstream
    │   └── main
    │
    └── 내 Fork
        │
        └── origin
            ├── main
            └── feature/my-pr
```


## Clone 하는 법

```
git clone <레포지토리 주소>
```

그리고
```
cd opensource-study
```
여기서 아래의 명령어로 확인
```
git remote -v
```


## 브랜치 만들기(최초 생성)

```
git checkout -b workshop
```

## 브랜치 들어가기(기존에 있는 브랜치)

```
git checkout workshop
```

## 브랜치 확인

```
git branch
```

## 브랜치 삭제

```
git branch -d workshop
```


## 커밋하기

```
git add .
git commit -m "커밋 메시지"
```

## 커밋 푸시하기

```
git push origin workshop
```

## 업스트림 등록하기

```
git remote add upstream https://github.com/SUSC-KR/opensource-study.git
```


## 최신 업스트림 main 가져오기

```
git fetch upstream
git rebase upstream/main
```

왜 rebase를 쓰는가?
- rebase는 커밋 히스토리를 깔끔하게 유지할 수 있다
```
내 브랜치

A
B
C

↓

upstream

A
D
E

↓

rebase

A
D
E
B
C
```

## Force push

```
git push origin workshop --force-with-lease
```

왜 --force 대신 --force-with-lease를 쓰는가?
- --force-with-lease는 다른 사람이 upstream에 push한 커밋을 덮어쓰지 않도록 보호해준다.
- --force는 다른 사람이 upstream에 push한 커밋을 덮어쓸 수 있다.


