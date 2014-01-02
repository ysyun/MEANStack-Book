MEANStack-Book
==============

MEANStack 책 공동집필

Markdown
==============

* Header는 `#`, `##`, `###`, `####` 문법 사용
* 코드는 &#x60;&#x60;&#x60; 문법 사용
* 주석 `[^footnote]` 사용

Word(.docx) 생성
================

Markdown 문서는 pandoc을 통해서 워드 문서로 변환할 수 있습니다.

## pandoc 설치

```sh
# linux(debian 계열)
$ sudo apt-get install pandoc

# mac(homebrew 사용시)
$ brew install haskell-platform
$ cabal update
$ cabal install pandoc

# mac(port 사용시)
$ sudo port install pandoc
```

## pandoc을 통한 변환 명령어

pandoc에서 md 파일을 워드 파일로 변경하려면 `pandoc input.md -o
output.docx` 명령어를 사용합니다. 구체적인 명령어는 아래와 같이 사용합니다.

```sh
$ pandoc markdown/3_4_heroku_introduction.md -o docx/3_4_heroku_introduction.docx
```

## 논의가 필요한 부분

이외에 스타일 레퍼런스 문서를 지정 가능하다고 하니 확인이 필요합니다.

또한 이미지 파일 배치를 위해서 미리 적절한 크기로 리사이즈가 필요합니다.

