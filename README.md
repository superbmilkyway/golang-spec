# golang-spec
Go 언어 스펙 한글 번역

Go 언어 스펙 번역에 참여하실 분들은 아래 링크를 통해 본인이 번역하고자 하는 부분에 이름을 등록하시길 바랍니다.

https://docs.google.com/spreadsheets/d/1R-E_4SM1vGsUiGBLLVilUlahHxC7U1R592E3GLryYKA/edit?usp=sharing

작년에 Effective Go 번역과 마찬가지로 [GitHub 저장소](
https://github.com/golangkorea/golang-spec)를 fork하시고 번역하신 다음 PR을 생성해주시면 됩니다.

번역물은 [GitBook](https://www.gitbook.com/book/gosudaweb/go-language-specification-in-korean/details)에 호스트됩니다.

기본적인 번역 가이드라인에 대한 의견은 [issue](https://github.com/golangkorea/golang-spec/issues/2)를 이용해주세요. 

번역에 대한 질의나 토의는 [Gitter 방](https://gitter.im/golang-korean-community/go-spec-in-korean?utm_source=share-link&utm_medium=link&utm_campaign=share-link)을 이용해 주십시요.

# 번역 진행 과정
PR 생성 - Merge - GitBook 포스팅 - Proof of Reading - Discussion - Contents Update(PR)

GitHub에서 master branch에 merge되면 자동으로 [GitBook](https://www.gitbook.com/book/gosudaweb/go-language-specification-in-korean/details)에 포스팅됩니다. 따라서 번역물에 대한 논의, 오탈자 보고, 의견제시는 [GitBook](https://www.gitbook.com/book/gosudaweb/go-language-specification-in-korean/details)을 이용해 주시길 바랍니다.

# 번역 가이드라인

1. 번역글 상단에 아래와 같이 spec 버전, 원문, 번역자를 추가해주세요.

* spec 버전: June 28, 2017(spec문서 상단에 표기되어 있음)
* 원문: \[영문 섹션 이름\]\(영문 문서 주소\)
* 번역자: \[번역자 이름\]\(@github_ID\)


2. 번역글을 작성하실때 한 문단 단위로 나누어 하시길 권장합니다. Proof reading이 끝날 때까지는 원문을 그대로 남겨두시고 원문 문단 바로 밑에 번역 문단을 작성하시면 Proof Reading을 원할히 진행할 수 있습니다.

* 원문과 번역문이 서로 분리되어 렌더링되기 위해서 이 둘 사이에는 *반드시 하나 이상의 빈줄*을 유지해 주셔야 합니다.
* 리스트 번역을 하실 때에는 바로 밑에 번역을 하면 번역문이 영문 리스트에 포함되어 버립니다. 반드시 상위 문단과 함께 묶어 번역해 주세요.

```
//번역 예시

//BAD
Comments serve as program documentation. There are two forms:
주석을 이용해 프로그램 문서화를 할 수 있다. 주석은 2가지 형태가 있다:

//GOOD
Comments serve as program documentation. There are two forms:

주석을 이용해 프로그램 문서화를 할 수 있다. 주석은 2가지 형태가 있다:

//BAD
1. *Line comments* start with the character sequence // and stop at the end of the line.
1. *라인 주석*은 //로 시작하며 라인 끝에서 끝난다.
2. *General comments* start with the character sequence /\* and stop with the first subsequent character sequence \*/.
2. *일반 주석*은 /\*로 시작해서 \*/을 처음 만났을 때 끝난다. 

//GOOD
Comments serve as program documentation. There are two forms:

1. *Line comments* start with the character sequence // and stop at the end of the line.
2. *General comments* start with the character sequence /\* and stop with the first subsequent character sequence \*/.

주석을 이용해 프로그램 문서화를 할 수 있다. 주석은 2가지 형태가 있다:

1. *라인 주석*은 //로 시작하며 라인 끝에서 끝난다.
2. *일반 주석*은 /\*로 시작해서 \*/을 처음 만났을 때 끝난다. 
```

3. 맺음말은 "~하다"로 통일하겠습니다.
4. 번역 소스는 Markdown으로 작성되어 있습니다. [Gitbook에 있는 syntax](https://toolchain.gitbook.com/syntax/markdown.html)를 준수해 주십시요.
5. 단어의 통일을 위해 Glossary를 활용할 방침입니다. 번역에 자신이 없을 경우 [Gitter방](https://gitter.im/golang-korean-community/go-spec-in-korean?utm_source=share-link&utm_medium=link&utm_campaign=share-link)에 문의해 주시고 의견이 수렴되면 [Glossary 페이지](https://github.com/golangkorea/golang-spec/blob/master/GLOSSARY.md)에 첨가해 주십시요.
6. 번역이 애매하거나 어색한 경우는 한글 단어 옆에 괄호로 영어 원문의 단어를 적어주십시요.
7. 번역작업도 중요하지만 함께 작업하시는 분들의 내용을 Proof reading하는데 동참해 주십시요.
8. PR를 한 지 좀 시간이 지나다 보면 그 사이에 golangkorea/golang-spec에 많은 변화가 있을 수 있습니다. 그때는 본인의 로컬 repo를 최신의 golangkorea/golang-spec와 싱크 시킬 필요가 생깁니다. 새로운 포스트를 시작하기 전에 우선 로컬의 repo에 golangkorea/golang-spec를 upstream remote repo로 만드시고 나머지 단계를 따라 싱크 시키십시요.

* Add the remote, call it "upstream":
```bash
git remote add upstream https://github.com/golangkorea/golang-spec.git
```

* Fetch all the branches of that remote into remote-tracking branches, such as upstream/master:
```bash
git fetch upstream
```

* Make sure that you're on your master branch:
```bash
git checkout master
```

* Rewrite your master branch so that any commits of yours that aren't already in upstream/master are replayed on top of that other branch:
```bash
git rebase upstream/master
```
* Merge를 하는 경우에는 rebase를 merge로 바꿔주시면 됩니다. [GitHub의 공식 도움말](https://help.github.com/articles/syncing-a-fork/)을 참조하십시요. 일단 싱크되면 본인의 forked repo에 다시 푸쉬하십시요.
```bash
git push -f origin master
```
