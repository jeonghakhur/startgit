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










