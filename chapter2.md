# Git 최초 설정

Git을 설치하고 나면 Git의 사용 환경을 적절하게 설정해 주어야 한다. 한 번만 설정하면 된다. 설정한 내용은 Git을 업그레이드해도 유지된다. 언제든지 다시 바꿀 수 있는 명령어도 있다.

git config라는 도구로 설정 내용을 확인하고 변경할 수 있다. Git은 이 설정에 따라 동작한다.

## 설정파일
1. ```gitconfig```: 시스템의 모든 사용자와 모든 저장소에 적용되는 설정이다. 파일 위치는 인스톨러로 Git을 윈도에 설치할 때 위치며 변경을 하지 않고 설치하였다면 ```C:\Program Files\Git\etc```가 파일 경로일 것이다.
2. ```.gitconfig```: 특정 사용자에게만 적용되는 설정파일로 윈도우 환경의 어드민 계정으로 Git을 설치하였다면 ```C:\Users\Administrator\``` 에 파일이 위치 할 것이다.
3. ```.git/config```: 이 파일은 Git 디렉토리에 있고 특정 저장소(혹은 현재 작업 중인 프로젝트)에만 적용된다.

각 설정은 역순으로 우선시 된다. 그래서 ```.git/config```가 ```.gitconfig```보다 우선한다.

## 사용자 정보
Git을 설치하고 나서 가장 먼저 해야하는 것은 사용자 이름과 이메일 주소를 설정하는 것이다. Git은 커밋할 때마다 이 정보를 사용한다. 한 번 커밋한 후에는 정보를 변경할 수 없다.
```
$git config --global user.name "Hong Gildong"
$git config --global user.email "honggildong@example.com"
```

*옵션 삭제*

```
$git config --global --unset user.name
```

///

```--global``` 옵션으로 설정한 것은 딱 한 번만 하면 된다. 해당 시스템에서 해당 사용자가 사용할 때에는 이 정보를 사용한다. 만약 프로젝트 마다 다른 이름과 이메일 주소를 사용하고 싶으면 ```---global``` 옵션을 빼고 명령을 실행한다.

## 편집기
사용자 정보를 설정하고 나면 Git에서 사용할 텍스트 편집기를 고른다. 기본적으로 Git은 시스템의 기본 편집기를 사용한다. 다른 텍스트 편집기를 사용할 수 있고 아래와 같이 실행하면 된다.

```
$git config --global core.editor 에디터 경로
```

## 설정 확인

```
$git config --list
```

Git은 같은 키를 여러 파일(```/etc/gitconfig```와 ```~/.gitconfig``` 같은)에서 읽기 때문에 같은 키가 여러개 있을 수도 있다. 그러면 Git은 나중 값을 사용한다.

```git config <key>``` 명령으로 Git이 특정 Key에 대한 어떤 값을 사용하는지 확인할 수 있다.

```
$git config user.name
Hong Gildong
```

 명령을 실행하면 설정한 모든 것을 보여준다.





