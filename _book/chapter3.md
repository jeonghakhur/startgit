# Git 저장소 만들기

Git 저장소를 만드는 방법은 두 가지다. 기존 프로젝트를 Git 저장소로 만드는 방법이 있고, 다른 서버에 있는 저장소를 Clone 하는 방법이 있다.

##기존 디렉토리를 Git 저장소로 만들기
기좆ㄴ 프로젝트를 Git으로 관리하고 싶을 때, 프로젝트의 디렉토리로 이동해서 아래와 같은 명령을 실행한다.

```
$git init
```

이 명령은 ```.git``` 이라는 하위 디렉토리를 만든다. ```.git``` 디렉토리에는 저장소에 필요한 뼈대 파일이 들어있다.

Git이 파일을 관리하게 하려면 저장소에 파일을 추가하고 커밋해야 한다.

```
$git add --all
$git add *.md
$git commit -m 'first commit'
```

##기존 저정소를 Clone하기

```
$git clone https://github.com/jeonghakhur/testgit
```

다름 디렉토리 이름으로 Clone하기

```
$git clone https://github.com/jeonghakhur/testgit mytestgit
```


