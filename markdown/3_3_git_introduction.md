# Git

## 개요

Git은 리눅스의 리누스 토발즈가 리눅스 커널 관리를 위해 개발한 분산 버전관리 시스템(decentralized version control system)이다. Git은 단순한 diff와 버전관리를 넘어서 브랜치와 태그를 제공해 프로젝트 전체를 좀 더 체계적으로 관리하고 추적할 수 있도록 도와주며, 프로젝트에 부가된 변경이력 정보를 통해 다양한 정보를 통해 다양한 기능들을 제공한다. 또한 분산형 버전관리 어플리케이션으로서 중앙서버를 통한 관리뿐만 아니라 개개의 작업 공간을 공유하거나 분산된 작업 환경을 통합하기 위한 기능들을 제공한다. 또한 SVN과 같이 이전에 많이 쓰이던 버전관리 시스템에 스테이징 영역이 추가되어 로컬 상에서 저장소에 파일을 commit 하는 과정에 있어서 좀 더 섬세한 조작이 가능하다. 이러한 많은 장점을 비롯해 무엇보다도 Git 오픈소스로서 하나의 어플리케이션으로는 대부분의 환경에서 아무런 제약없이 사용할 수 있다.

## Git 설치하기

### 리눅스

#### 패키지 관리자를 이용한 설치

리눅스에서는 각각 배포판에서 사용하는 패키지 관리자를 사용해 Git을 바로 설치할 수 있다. 쉘에서 패키지 관리자 설치 명령어를 직접 입력하거나, GUI로 만들어져있는 패키지 매니저에서 검색해 설치할 수 있다. 아래는 Git을 설치하는 패키지 관리자 명령어이다.

```sh
# Debian / Ubuntu
$ apt-get install git

# Fedora
$ yum install git

# Gentoo
$ emerge --ask --verbose dev-vcs/git

# 설치 확인
$ git --version
git version 1.8.1.2
```

이외의 배포판에서도 각각의 패키지 관리자를 사용해 설치할 수 있다.[^git-5]

[^git-5]:각각의 리눅스 배포판에서 설치하는 명령어는 http://git-scm.com/download/linux 에서 확인할 수 있다.

#### 소스를 이용한 설치

패키지 관리자를 통해서 설치할 수 있는 버전은 해당하는 운영체제에 안정화된 버전이다. 일반적으로 안정화된 버전을 사용하는 것으로도 충분히 Git을 사용할 수 있지만, 최신 버전이나 특별한 버전을 설치할 경우 소스 코드를 다운로드 받아 직접 빌드해서 설치할 수 있다.

Git의 소스코드는 Git 공식 저장소[^git-10]에서 다운로드 받을 수 있다. 예를 들어 아래에서는 Git 최신 버전 1.8.5.2 버전을 설치한다.

```
# 패키지 관리자에서 제공하는 패키지 정보를 확인
$ apt-cache show git
Commend > apt-cache show git
Package: git
Version: 1:1.8.1.2-1

# 소스코드 다운로드
$ wget http://git-core.googlecode.com/files/git-1.8.5.2.tar.gz

# 압축 해제
$ tar xvzf git-1.8.5.2.tar.gz

# Git 빌드
$ cd git-1.8.5.2
$ ./configure
$ sudo make
$ sudo make install

# 설치 확인
$ git --version
git version 1.8.1.2
```

소스 코드를 통해 빌드하는 과정에서 다른 패키지에 대한 의존성 문제로 설치가 잘 되지 않을 수도 있다. 이럴 경우엔 에러 메시지를 확인하고 관련된 패키지를 설치해줘야한다. 이 외에도 시스템 환경에 따라서 다양한 문제가 발생할 수 있으므로 구글에 에러메시지를 검색해서 해결방법을 찾아볼 수 있다.

[^git-10]:http://code.google.com/p/git-core/downloads/list

### MacOS

#### Xcode Commennd Line Tools를 이용한 설치

#### 패키지 관리자를 이용한 설치

MacOS에서도 리눅스와 마찬가지로 패키지 관리자를 사용해서 Git을 설치할 수 있다. 아래는 Homebrew를 사용해서 설치하는 예제이다. Homebrew는비교적 패키지 업데이트가 빠른 편이라 비교적 최신 버전을 쉽게 설치할 수 있다.

```
# Homebrew 설치
$ ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"

# Git 설치
$ brew install git
$ git --version
git version 1.8.5.1
# 설치 확인

```

#### 소스를 이용한 설치

Mac에서도 리눅스와 마찬가지로 원하는 버전을 소스 코드를 직접 빌드해 설치할 수 있다. (자세한 내용은 Linux의 소소를 이용한 설치 절을 참조)

### 윈도우

## Git 기본 명령어

### Git 설정하기
### Git 저장소 생성하기
### Git 브랜치

## Github

Github[^github]는 원격에서 Git 저장소를 제공해주는 Git 서비스이자, 이 저장소를 웹에서 관리 및 조작할 수 있는 기능을 지원하는 웹서비스이다. Git에서는 기본적으로 저장소를 분산해서 관리하고 쉽게 공유할 수 있지만, Github는 이러한 원격 저장소를 한 곳에서 일관적으로 관리할 수 있도록 도와주며 브랜치, 태그, 코드 병합과 같은 Git의 기능을 기본적으로 지원함은 물론 추가적으로 저장소 Fork, 이슈 관리, Pull request, 접근 관리(멤버 관리), 위키 기능 등을 지원해 단순한 버전관리 시스템을 넘어서 협업 및 프로젝트 관리에 유용하게 사용할 수 있다.

Github은 공개된 코드에 대해서는 사용료가 없으며, 이러한 이유로 현재는 대부분의 오픈소스가 Github 저장소를 사용하고 있다. 공개된 코드는 오픈소스가 아니더라도 무료로 이용할 수 있으며 비공개 저장소를 만들고자 할 때는 약간의 이용료를 지불하면 된다.

이 뿐만 아니라 Github을 둘러싸고 있는 생태계 역시 주목할만하다. 어플리케이션 빌드 및 배포를 지원하는 CI서비인 Travis[^travis], 테스트 커버리지 측정을 해주는 Coveralls[^coveralls], 정적 코드 분석 도구인 Code Climate[^codeclimate] 등등, 이러한 서비스들은 Github 저장소만 있다면 언제든 바로 사용이 가능하며, 일련의 서비스들 역시 공개 저장소에 대해서는 무료로 사용할 수 있다.

[^github]:http://github.com
[^travis]:http://travis.com
[^coveralls]:http://coveralls.io
[^codeclimate]:http://codeclimate.com , 현재는 ruby와 javascript의 정적 분석을 지원한다.

### Gtihub 계정 만들기
### ssh키 생성

Github을 비롯한 외부 저장소 서비스를 이용하려면 사용자 인증을 대신해 ssh 키를 사용해야한다. ssh키를 생성하면 공개키와 비밀키가 생성이 된다. 이 때 비밀키는 인증하려는 하는 시스템에 안전하게 보관해야하며, 공개키는 Github에 등록해야한다.

#### 리눅스, MacOS

리눅스와 MacOS에서 ssh키는 ssh-keygen 명령어를 사용해 생성한다.

```sh
$ ssh-keygen -t rsa -C "<YOUR_EMAIL>"
Gnerating public/private rsa key pair.
Enter file in which to save the key (/home/YOUR_ACCOUNT/.ssh/id_rsa): <Enter>
Enter passphrase (empty for no passphrase): <YOUR_PASSWORD>
Enter same passphrase again: <YOUR_PASSWORD>
Your identification has been saved in /home/YOUR_ACCOUNT/.ssh/id_rsa
Your public key has been saved in /home/YOUR_ACCOUNT/.ssh/id_rsa.pub
The key fingerprint is:
...
```

일반적으로 ssh키 생성 경로는 홈디렉토리/.ssh를 사용한다. 패스워드를 입력하지 않으면  파일을 복사하는 것만으로 인증이 가능해지므로 패스워드를 지정하는 것이 좋다. 생성된 홈디렉토리/.ssh 디렉토리에서 확인할 수 있으면 비밀키는 id_rsa 파일에 저장되고, 공개키는 id_rsa.pub 파일에 저장된다.

#### 윈도우

### Github ssh키 등록

ssh키를 생성했다면 Github에 공개키를 등록해 커맨드라인이나 다른 어플리케이션에서 인증이 가능하도록 해주어야한다.

* 먼저 Github에 로그인을 하고 오른쪽 상단 메뉴 중에 Account Settings에 접속한다.
* 왼쪽 사이드 바의 "ADD SSH key"를 선택한다.
* key 필드에 공개키의 내용을 그대로 복사하고 키를 추가한다.

키 등록이 완료되었으면 ssh를 통해 인증이 정상적으로 이루어지는지 확인해볼 필요가 있다.

```sh
$ ssh -T git@github.com
```

처음 접속시 아래와 같은 메시지가 출력된다.

```sh
The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is 16:27:ac:a5:76:5d:2d:36:63:1b:32:4d:eb:df:a6:48.
# Are you sure you want to continue connecting (yes/no)?
```

yes를 입력하거나 엔터를 치면 아래와 같은 메시지를 볼 수 있다.

```sh
Hi YOUR_NAME! You've successfully authenticated, but GitHub does not provide shell access.
```

접속에 실패하면 다음과 같은 메시지가 출력된다.

```sh
Permission denied (publickey).
```

이러한 경우 키 생성이나 공개키 복사 과정에서 문제가 생겼을 수 있으니 다시 한 번 확인해볼 필요가 있다. 이러한 과정이 정상적인 경우에도 문제가 발생하는 경우엔 네트워크 문제나 어플리케이션 접근하려는 ssh 키 경로가 다를 수 있다. 이를 때는 자세한 접속 로그를 확인해볼 필요가 있다.

```sh
$ ssh -vT git@github.com
```

`-v` 옵션을 사용하면 자세한 접속 로그를 확인할 수 있어 이러한 문제를 확인할 수 있어 문제 해결에 도움을 준다.

### Github에 저장소 생성하기

Github에 저장소를 생성하는 방법에는 크게 두가지 방법이 있다. 하나는 Github에서 저장소를 초기화해서 로컬으로 클론(clone)하는 방법이며, 또 하나는 로컬에서 관리중에 git 저장소를 Github에 푸쉬(push)하는 방법이다. 전자는 미리 저장소를 초기화할 필요가 있는 경우에 사용하며, 후자는 이미 로컬에서 관리중인 git 저장소가 있는 사용하는 게 보통이지만 두 접근법에 근본적인 차이가 있는 것은 아니므로 상황에 따라 편리한 방법을 사용하면 된다.

#### Github에서 저장소 초기화하기

아래와 같은 절차에 따라 Git저장소를 웹상에서 바로 초기화할 수 있다.

* github.com 에 접속해서 로그인
* 오른쪽 상단의 Create a new repo 선택
* Repository 이름 입력
* Initialize this repository with a README 옵션에 체크
* Create Repository 선택

저장소를 만들면 바로 저장소 관리 페이지를 볼 수 있다. 페이지 오른쪽에는 로컬에서 clone할 수 있는 주소를 볼 수 있다. 이 주소를 복사해 로컬에서 아래 명령어를 입력하면 저장소 이름으로 새로운 디렉토리가 생성된다.

```sh

```


#### 로컬 저장소를 Github에 푸쉬해서 초기화하기

### Github에 저장소 푸쉬

### hub를 통한 Git 확장
