# branch command

- 브랜치 생성

```bash
$ git branch 브랜치명
```

- 브랜치 목록

```bash
$ git branch
```

- 브랜치 이동

```bash
#git checkout 까지만 입력한 상태에서
#tab*2 -> checkout 가능한 브랜치명 확인 가능
$ git checkout 브랜치명
(브랜치명) $
```

```bash
$ git log --oneline
d7ec4bd (HEAD -> master, origin/master, origin/HEAD) 01 file 수정
```

​		- HEAD:현재 우리가 속한위치

```bash
$ git log --all --graph --oneline
```



- 브랜치 생성+이동

```bash
$ git checkout -b 브랜치명
```

- 브랜치 병합

```bash
(master)인상태 $ git merge 브랜치명
```

 -반드시 master 브랜치에 (브랜치명)를 병합

 -(화면 전환 이후) i 누르면 내용 수정가능, 수정후 esc 누르고 :wq 누를시 저장됨

- 브랜치 삭제

```bash
$ git branch -d 브랜치명
```

- 브랜치 강제 삭제

```bash
$ git branch -D 브랜치명
```

-merge가 되지 않은  브랜치는 강제로 삭제해야 함.

## 3가지 병합 상황

### 1. fast-foward

"다른 브랜치를 생성 한 후, master 브랜치에 변경 사항이 없을때"

## 2. 3-way merge

"현재 브랜치(master)가 가르키는 커밋이 merge 할 브랜치의 조상이 아니라면 깃은 현재 브랜치와 머지할 브랜치의 거밋 2개와 두 브랜치의 공통조상 하나를 사용한다."

1. 새로운 브랜치 signup 생성
2. signup 브랜치 에서 signup.py 생성 (git add, commit 잊지말기)
3. master 브랜치에서 new folder와 new.py 생성(git add, commit 잊지말기)
4. master 브랜치와 signup 브랜치 병합
5. signup 브랜치 삭제

### Merge Conflict

"두 개의 브랜치가 동일한 파일의 동일한 위치를 수정하고 merge 하려고 할 때 발생하는 현상

단, 동일 파일을 수정했다고 하더라도 서로 다른 영역을 수정한다면 merge conflict는 발생하지 않는다"

- git이 자동으로 병합하지 못하는 상황

##### 1. 새로운 브랜치 hotfix 생성 

```bash
$ git branch hotfix
$ git checkout hotfix
# $ git chckout -b hotfix
```



##### 2.hotfix 브랜치에서 b.txt에 새로운 내용 입력(add,commit)

- git add,commit

```bash
$ git add . or b.txt
$ git commit -m "massage"
```



##### 3.master 브랜치에서 b.txt에 새로운 내용 입력(add,commit)

- git add,commit

##### 4.master 브랜치와 hotfix브랜치 병합

```bash
user1@DESKTOP-BAJ5JVA MINGW64 ~/Desktop/github_study (master)
$ git merge hotfix
Auto-merging b.txt
CONFLICT (content): Merge conflict in b.txt
Automatic merge failed; fix conflicts and then commit the result.

user1@DESKTOP-BAJ5JVA MINGW64 ~/Desktop/github_study (master|MERGING)

```



