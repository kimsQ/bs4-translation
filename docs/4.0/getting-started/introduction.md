---
layout: docs
title: 소개
description: 반응형, 모바일 우선 사이트를 구축하기 위해 부트스트랩 CDN 및  스타터 템플릿을 사용하여 세계에서 가장 인기 있는 프레임워크인 부트스트랩으로 시작하십시오.
group: getting-started
redirect_from:
  - /docs/4.0/getting-started/
  - /docs/4.0/
  - /docs/
toc: true
---



## 빠른 시작
프로젝트에 부트스트랩을 빠르게 추가하려고 하십니까? MaxCDN에서 무료로 제공하는 Bootstrap CDN을 사용하십시오. 패키지 매니저를 사용하거나 원본 파일을 다운로드해야 합니까?
[다운로드 페이지로 이동]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/download/)

### CSS

bootstrap CSS를  로드하기 위해  아래의 `<link>`코드를  다른 모든 스타일 시트들 보다 우선하여(상위에) `<head>`에 복사하여 붙여넣기 하세요.

{% highlight html %}
<link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
{% endhighlight %}

### JS

대부분의 컴포넌트는 JavaScript를 사용해야 작동합니다. 특히 [jQuery](https://jquery.com), [Popper.js](https://popper.js.org/) 및 자체 자바 스크립트 플러그인이 필요합니다. 아래의`<script>`를 `</body>`태그 바로 앞에 붙여 놓습니다. 먼저 jQuery가 오고 그 다음 Popper.js가 오고 그 다음 부트스트랩 JS 플러그인이 와야합니다.

[jQuery slim 버전](https://blog.jquery.com/2016/06/09/jquery-3-0-final-released/)을 사용하며, jQuery full 버전도 지원 됩니다.

{% highlight html %}
<script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

jQuery, 우리의 JS 및 Popper.js가 명시적으로 필요한 컴포넌트가 궁금하신가요?
아래의 컴포넌트 보기 링크를 클릭 합니다. 일반 페이지 구조에 대해 확실하지 이해되지 않은 경우에는 예제 페이지 템플릿을 계속 읽어 보십시오.

<details>
<summary class="text-primary mb-3">JavaScript가 필요한 컴포넌트 보기</summary>
{% markdown %}
- Alerts을 닫을때
- 토글링(toggling)을 위한 버튼 그리고 checkbox/radio의 작동
- 캐러셀(Carousel)에서 슬라이드의 동작과 컨트롤 그리고 지시자(indicators)
- 콘텐츠의 가시성 확보를 위한 접고 펼치기(Collapse)
- 드롭다운(Dropdown)의 표시와 위치지정 ([Popper.js](https://popper.js.org/)도 필요)
- 모달(Modal)의 표시 및 위치지정 그리고 스크롤 동작
- Navbar의 반응형 작동관련(Collapse)
- 툴팁(Tooltip)과 팝오버(popover)의 표시와 위치지정 ([Popper.js](https://popper.js.org/)도 필요)
- 스크롤스파이(Scrollspy)의 스크롤작동과 네이게이션 업데이트
{% endmarkdown %}
</details>

## 기본 템플릿

페이지를 최신 디자인 및 개발 표준으로 설정하십시오. 즉, HTML5 Doctype을 사용하고 적절한 반응형 동작을 위해 뷰포트 메타 태그를 포함 해야합니다. 모두 정리하면 페이지가 아래와 같이 보입니다.

{% highlight html %}
<!doctype html>
<html lang="ko">
  <head>
    <title>Hello, world!</title>
    <!-- meta tags 필요 -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- 먼저 jQuery가 오고 그 다음 Popper.js 그 다음 Bootstrap JS -->
    <script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
    <script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
  </body>
</html>
{% endhighlight %}

이것이 전체 페이지 요구사항의 전부 입니다. [레이아웃 문서]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/overview/) 또는 [공식예제]({{ site.baseurl }}/docs/{{ site.docs_version }}/examples/)를 확인하여 사이트의 콘텐츠 및 컴포넌트 구성을 시작하십시오.

##  중요한 글로벌 설정 (Important globals)

부트스트랩은 중요한 글로벌 스타일과 설정을 사용합니다.
이 스타일은 크로스 브라우저 스타일의 *normalization* 에 대해서만 적용되어 있습니다. 이제 들어가 봅시다.


### HTML5 doctype

부트스트랩을 사용하려면 HTML5 Doctype을 사용해야 합니다. 이것이 없다면, 케케묵은 불완전한 스타일링을 보게 될 것입니다.

{% highlight html %}
<!doctype html>
<html lang="ko">
  ...
</html>
{% endhighlight %}

### 반응형 메타 태그

부트스트랩은 먼저 모바일 기기에 코드를 최적화 한 다음 CSS 미디어 쿼리를 사용하여 필요한대로 컴포넌트를 확장하는 *mobile first* 방식으로 개발 되었습니다.
모든 기기에 대해 올바른 렌더링 및 터치줌을 보장하려면 **아래의 반응형 뷰포트 메타 태그** 를 `<head>` 에 추가하세요.

{% highlight html %}
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
{% endhighlight %}

이 예제는 [기본-템플릿](#기본-템플릿)에서 실제로 볼 수 있습니다.

### Box-sizing

CSS에서 보다 간단한 크기 조정을 위해서, 우리는 전역 `box-sizing` 값을 `content-box`에서 `border-box`로 전환 합니다.
이렇게하면 `padding`이 요소의 최종계산 된 너비에는 영향을 미치지 않지만 Google 지도 및 Google 맞춤 검색엔진과 같은 일부 타사 소프트웨어에는 문제가 발생할 수 있습니다.

드문 경우이긴 하지만 필요하다면 아래의 코드를 보완(override)하여 사용하시면 됩니다.

{% highlight scss %}
.selector-for-some-widget {
  box-sizing: content-box;
}
{% endhighlight %}

위의 스니핏을 사용하면 중첩된(nested) 요소(`::before` 및 `::after`를 통해 생성된 내용 포함)에 `.selector-for-some-widget`에서 지정한 `box-sizing`을 상속됩니다.

[CSS Tricks](https://css-tricks.com/box-sizing/)에서 박스모델 및 사이징에 대해 자세히 알아보세요.

Learn more about [box model and sizing at CSS Tricks](https://css-tricks.com/box-sizing/).

### Reboot

보다 향상된 크로스 브라우징 랜더링을 위해, 우리는 [Reboot]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/) 사용하여 브라우저와 디바이스 간에 불일치를 교정하고 공통적인 HTML요소에 대한 약간의 임의적 리셋을 제공합니다.


## 커뮤니티

부트스트랩 개발의 최신정보를 얻고 유용한 자원들이 있는 커뮤니티에 들어와보세요.

-  트위터에서 [@getbootstrap](https://twitter.com/getbootstrap)를 팔로우 할 수 있습니다.
- [공식 부트스트랩 블로그]({{ site.blog }})를 읽고 구독합니다.
- [공식 Slack 룸]({{ site.slack }})에 참여 합니다.
- `irc.freenode.net` 서버의 `##bootstrap` channel 에서 부트스트랩을 다루는 사람들과 채팅을 하세요.
- 구현 도움말은 스택오버플로우에서 찾을수 있습니다. (tagged [`bootstrap-4`](https://stackoverflow.com/questions/tagged/bootstrap-4)).
- 개발자는 부트스트랩의 기능을 변경하거나 추가한 패키지를 [npm](https://www.npmjs.com/browse/keyword/bootstrap) 또는 이와 유사한 메커니즘을 사용하여 배포 할때 최대한 검색 가능성을 높이기 위해 키워드에 `bootstrap` 을 사용해야 합니다.

트위터에서 [@getbootstrap](https://twitter.com/getbootstrap)을 팔로우하면 최신 가십 거리와 멋진 뮤직 비디오를 볼 수 있습니다.
