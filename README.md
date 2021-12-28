# FOSS-FinalProject - 소프트웨어학과 201720707 나용성

# 번역 프로젝트 보고서

---

## 번역 대상 선정 이유

이번 프로젝트의 보고서를 markdown 을 이용해 작성하도록 제시되어 있었기 때문에 먼저 교수님의 markdown 강의를 들어보았다. 강의를 들으면서 markdown 을 이용해 문서를 작성하는 것이 재밌어 보였고 더 자세히 알아보고 싶은 마음이 생겨서 markdown 메뉴얼을 번역을 하면서 알아보는 것이 좋을 것이라 생각했다.  
그리고 앞으로 개발자로 활동하면서 github에서 활동을 많이하게 될 것이고 md파일을 읽고 작성하고 수정하는 상황이 많이 생길 것이기 때문에 markdown 에 대해 잘 익혀두는 것이 좋을 것이라 생각했다.  
그리고 교수님이 직접 사용하시면서 `markdown-preview-enhanced` 플러그인이 좋다고 수업중에 자주 언급하시던 이유가 궁금하기도 했다. 또 주제를 정하는데 시간이 많이 지체되어 주제를 자체적으로 정하기 어려운 상황이 되어 교수님이 마련해주신 주제를 사용하는것이 최선일 것 같아 번역 대상으로 선정하게 되었다.

---

## 번역 내용 요약

github repository의 docs 디렉토리의 뷰 기준으로 위에서 부터 9개의 md파일과 대문역할을 하는 README.md파일을 번역했다. 번역된 md파일의 내용들은 다음과 같았다.

- [README.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/README.md): `markdown-preview-enhanced` 프로젝트와 기능 개요를 소개하는 프로젝트의 대문 역할을 맡음  
- [_navbar.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/_navbar.md): 메뉴얼의 언어를 선택할 수 있는 언어선택 바  
- [_sidebar.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/_sidebar.md): 클릭을 통해 원하는 문서로 이동할 수 있는 사이드 바  
- [backers.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/backers.md): 프로젝트를 후원하는 방법과 후원을 한 **후원자들** 을 소개하는 문서  
- [code-chunk.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/code-chunk.md): markdown문서에 code를 작성해 출력에 렌더링 하는 방법을 소개하는 문서  
- [customize-css.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/customize-css.md): `css`를 사용자에 맞게 재정의 하는 방법을 소개하는 문서  
- [developer.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/developer.md): `markdown-preview-enhanced` 프로젝트 개발을 하고자 하는 개발자들에게 개발 방법을 소개하는 문서  
- [diagrams.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/diagrams.md): `markdown-preview-enhanced` 를 이용한 각종 다이어그램을 렌더링 하는 방법을 소개하는 문서
- [ebook.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/ebook.md): `markdown-preview-enhanced` 로 markdown 문서의 출력을 `ebook` 파일로 내보내는 방법을 소개하는 문서
- [extend-parser.md](https://git.ajou.ac.kr/NaYongSung/foss-finalproject/-/blob/main/docs/extend-parser.md): markdown parser 를 확장하는 방법을 소개하는 문서

---

## 어려웠던 점

먼저 markdown 에 대한 지식이 없이 시작하게 된 점이 가장 컸다. 교수님이 유튜브에 올려주신 markdown 에 대한 강의가 있어 도움이 많이되긴 했지만 직접 markdown 에 대해 이해해야 사용법을 이해하기 쉽도록 번역할 수 있을 것이라 생각했기 때문에 markdown 에 대해 이해하는데 시간을 많이 투자했다.  
그리고 LICENSE.md파일의 번역을 가장 먼저 번역을 완료 했었는데 확인해본 결과 LICENSE는 이미 번역이 완료된 모든 언어에서 같은 링크를 가리키고 있음을 확인하여 LICENSE이기 때문에 수정이 되면 않된다는 것을 확인했다. 때문에 어쩔 수 없이 폐기할 수 밖에 없었다.  
또 어떤 용어는 한글로 번역하고 어떤 용어를 영어로 남겨놔야 하는지 번역을 해야 한다면 어떠한 단어가 가장 적절할 지의 기준이 처음엔 감이 정확히 잡히지 않기도 했고 또 긴 문장은 번역의 어순을 적절히 한국어에 맞게 바꿔야 되므로 이에 대한 어려움도 있었다. 이는 일본어 번역본과 영어 번역본의 어순을 비교하면서 한글 번역을 진행하여 어려움을 완화할 수 있었다.

---

## 기여방법

markdown-preview-enhanced repository를 내 github계정으로 fork하여 복제한 다음 컴퓨터로 clone하여 repository를 컴퓨터에 저장했다. 그 다음 docs 디렉토리의 번역할 md파일들을 VS Code프로그램과 Markdown preview Enhanced 플러그인을 같이 활용해서 수정된 md파일의 미리보기를 확인하면서 번역을 진행했다. 번역이 완료된 md파일들은 github의 내 repository에 push해두었다. 해당 프로젝트는 교수님이 학생들의 번역 결과를 본 repository에 반영하도록 issues에 연락을 취해놓은 것을 확인했으므로 교수님에게 내 repository의 링크를 알리면 반영될 수 있을 것이다.

---

## 느낀 점

가장 먼저 markdown 을 이용해 문서를 작성하는 것의 매력을 느끼게 되었다. 또 교수님이 왜 `markdown-preview-enhanced` 이 플러그인을 선호하시는지 알게 되었다. markdown 이외에도 `다이어그램`, `code chunk`, `ebook` 등 다양한 기능을 지원하는 점이 매력적이었다. 또 내 번역이 실제로 프로젝트에 반영되어 번역 페이지가 생성된 것을 확인하게 되면 기분이 좋을 것 같다는 생각이 들었다. 한글로 된 markdown 메뉴얼 만으로도 많이 편리해질 것 같은데 직접 번역한 메뉴얼이 반영될 수 있다는 점이 실제로 오픈소스 프로젝트에 처음으로 참여하는 경험이 된 것 같아 보람찼다.
