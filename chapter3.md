# Git 저장소 만들기

Git 저장소를 만드는 방법은 두 가지다. 기존 프로젝트를 Git 저장소로 만드는 방법이 있고, 다른 서버에 있는 저장소를 Clone 하는 방법이 있다.

##기존 디렉토리를 Git 저장소로 만들기
기좆ㄴ 프로젝트를 Git으로 관리하고 싶을 때, 프로젝트의 디렉토리로 이동해서 아래와 같은 명령을 실행한다.

```
$ git init
```

이 명령은 ```.git``` 이라는 하위 디렉토리를 만든다. ```.git``` 디렉토리에는 저장소에 필요한 뼈대 파일이 들어있다.

Git이 파일을 관리하게 하려면 저장소에 파일을 추가하고 커밋해야 한다.

```
$ git add --all
$ git add *.md
$ git commit -m 'first commit'
```

##기존 저정소를 Clone하기

```
$ git clone https://github.com/jeonghakhur/testgit
```

다름 디렉토리 이름으로 Clone하기

```
$ git clone https://github.com/jeonghakhur/testgit mytestgit
```

##파일의 상태 확인하기

```
$ git status
```


##파일 제외하기

```
$ cat .gitignore
```

Staged와 Unstaged 상태의 변경 내용을 보기

```
git diff
```
##변경사항 커밋하기

```
$ git commit -m 커밋메세지
```
##Staging Area 생략하기

```
$ git commit -a -m '커밋 메시지'
```

```git commit``` 명령을 실행할 때 ```-a``` 옵션을 추가하면 Git은 Tracked 상태의 파일을 자동으로 Staging Area에 넣는다. 그래서 ```git add``` 명령을 실행하는 수고를 덜 수 있다.

##파일 삭제하기

```
$ git rm 삭제할파일명
```

Staging Area에 올라간 파일을 강제로 삭제해야한다면 ```-f``` 옵션을 주어야 한다. 또는 Staging Area에서만 제거하고 워킹 디렉토리에 있는 파일은 지우지 않고 남겨 둘 수 있는데 ```--cached``` 옵션을 사용하여 명령을 실행한다.

##파일 이름 변경하기

```
$ git mv file_from file_to
```

##되돌리기

```
$ git commit --amend
```
너무 일찍 커밋했거나 어떤 파일을 빼먹었을 때 그리고 커밋 메시지를 잘못 적었을 때 한다. 이 명령은 Staging Area를 사용하여 커밋한다. 만약 마지막으로 커밋하고 나서 수정한 것이 없다면 조금 전에 한 커밋과 모든 것이 같다. 이때는 커밋 메시지만 수정한다. 메시지를 수정하지 않고 그대로 커밋해도 기존의 커밋을 덮어쓴다.

커밋을 했는데 Stage 하는 것을 깜빡하고 빠트린 파일이 있으면 아래와 같이 고칠 수 있다.
```
$ git commit -m 'initial commit'
$ git add forgotten_file
$ git commit --amend
```
여기서 실행한 명령어 3개는 모두 하나의 커밋으로 기록된다. 두 번째 커밋은 첫 번째 커밋을 덮어쓴다.


##파일 상태를 Unstage로 변경하기
```
$ git reset HEAD unstage_file
```

##Modified 파일 되돌리기
```
$ git checkout -- modified_file
```

###리모트 저장소 확인하기
```
$ git remote -v
```
저장소를 Clone 하면 origin이라는 리모트 저장소가 자동으로 등록되기 때문에 origin이라는 이름을 볼 수 있다.


##리모트 저장소 추가하기
```
$ git remote [add] [단축이름 URL]
```


##리모트 저장소를 Pull 하거나 Fetch 하기
```
$ git fetch [remote-name]
```
이 명령은 모컬에는 없지만, 리모트 저장소에 있는 데이터를 모두 가져온다.

저장소를 Clone 하면 명령은 자동으로 리모트 저장소를 "origin"이라는 이름으로 추가한다. ```git fetch origin```을 실행하면 Clone 한 이후에 수정된 것을 모두 가져온다. ```git fetch``` 명령은 리모트 저장소의 데이터를 모두 로컬로 가져오지만, 자동으로 Merge 하지 않는다.

```git pull``` 명령은 리모트 저장소 브랜치에서 데이터를 가져올 뿐만 아니라 자동으로 로컬 브랜치와 Merge 시킬 수 있다.


##리모트 저장소에 Push 하기
```
$ git push [리모트 저장소 이름] [브랜치 이름]
```
Clone 한 사람이 여러 명 있을 때, 다른 사람이 Push 한 후에 Push 하려고 하면 Push 할 수 없다. 먼저 다른 사람이 작업한 것을 가져와서 Merge 한 후 Push 할 수 있다.


##리모트 저장소 살펴보기
```
$ git remote show origin
```


##리모트 저장소 이름 바꾸기 및 삭제하기
```
$ git remote rename [리모트 저장소 이름] [변경 할 리모트 저장소 이름]
```


##리모트 저장소 삭제하기
```
$ git remote rm [리모트 저장소 이름]
```
