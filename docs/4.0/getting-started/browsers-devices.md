---
layout: docs
title: 브라우저와 디바이스
description: Learn about the browsers and devices, from modern to old, that are supported by Bootstrap, including known quirks and bugs for each. 부트스트랩이 지원하는 브라우저와 디바이스에 대한 최신 정보를 제공합니다. 여기에는 알려진 각서와 버그가 포함됩니다.
group: getting-started
toc: true
---



## 지원 브라우저

부트스트랩은 모든 주요 브라우저와 플랫폼의 **최신, stable 버전** 을 지원합니다. Windows에서는 **Internet Explorer 10-11 / Microsoft Edge** 를 지원합니다.

Alternative browsers which use the latest version of WebKit, Blink, or Gecko, whether directly or via the platform's web view API, are not explicitly supported. However, Bootstrap should (in most cases) display and function correctly in these browsers as well. More specific support information is provided below.

최신 버전의 Webkit, Blink또는 Gecko, 또는 플랫폼의 웹뷰 API를 사용하는 대체 브라우저는 명확하게 지원되지 않습니다. 그러나 부트스트랩은 대부분의 경우 이 브라우저에서도 올바르게 표시되고 작동 해야합니다. 보다 구체적인 지원 정보는 아래에 제공됩니다.

### 모바일 디바이스

일반적으로 부트스트랩은 각 주요 플랫폼의 기본 브라우저의 최신 버전을 지원합니다. Opera Mini, Opera Mobile의 Turbo 모드, UC Browser Mini, Amazon Silk와 같은 프록시 브라우저는 지원되지 않습니다.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <td></td>
      <th>Chrome</th>
      <th>Firefox</th>
      <th>Safari</th>
      <th>Android Browser &amp; WebView</th>
      <th>Microsoft Edge</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Android</th>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-muted">해당없음</td>
      <td class="text-success">Android v5.0 이상 지원됨</td>
      <td class="text-muted">해당없음</td>
    </tr>
    <tr>
      <th scope="row">iOS</th>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-muted">해당없음</td>
      <td class="text-muted">해당없음</td>
    </tr>
    <tr>
      <th scope="row">Windows 10 Mobile</th>
      <td class="text-muted">해당없음</td>
      <td class="text-muted">해당없음</td>
      <td class="text-muted">해당없음</td>
      <td class="text-muted">해당없음</td>
      <td class="text-success">지원됨</td>
    </tr>
  </tbody>
</table>

### 데스크탑 브라우저

마찬가지로 대부분의 데스크톱 브라우저의 최신 버전이 지원됩니다.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <td></td>
      <th>Chrome</th>
      <th>Firefox</th>
      <th>Internet Explorer</th>
      <th>Microsoft Edge</th>
      <th>Opera</th>
      <th>Safari</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Mac</th>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-muted">해당없음</td>
      <td class="text-muted">해당없음</td>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
    </tr>
    <tr>
      <th scope="row">Windows</th>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨, IE10 이상</td>
      <td class="text-success">지원됨</td>
      <td class="text-success">지원됨</td>
      <td class="text-danger">지원되지 않음</td>
    </tr>
  </tbody>
</table>


Firefox의 경우 최신 표준 안정 버전 외에도 최신 ESR ([Extended Support Release](https://www.mozilla.org/en-US/firefox/organizations/faq/)) 버전을 지원합니다.

공식적으로 지원되지는 않지만 비공식적으로 부트스트랩은 Chromium 및 Linux 용 Chrome, Linux 용 Firefox 및 Internet Explorer 9에서 충분히 보이고 작동될수 있습니다.

부트스트랩이 해결해야하는 브라우저 버그 목록은 브라우저 [Wall of browser bugs]({{ site.baseurl }}/docs/{{ site.docs_version }}/browser-bugs/)을 참조하십시오.


## 인터넷 익스플로러

Internet Explorer 10 이상이 지원 됩니다. IE9 이하는 지원되지 않습니다. 일부 CSS3 속성 및 HTML5 요소는 IE10 에서 완전히 지원되지 않으며  전체 기능에 대해 미리 정의된 속성이 필요 하다는 점을 유념해 주시기 바랍니다. CSS3 및 HTML5 기능의 브라우저 지원에 대한 자세한 내용은 [Can I use...](https://caniuse.com/)를 참조하십시오.

**IE8-9 지원이 필요한 경우 부트 스트랩 v3을 사용하십시오.** 가장 안정적인 코드 버전이며 중요한 버그 수정 및 문서 변경 사항에 대해서는 팀에서 지원합니다. 그러나 새로운 기능은 추가되지 않습니다.


## 모바일에서 모달과 드롭다운

### Overflow 와 scrolling

Support for `overflow: hidden;` on the `<body>` element is quite limited in iOS and Android. To that end, when you scroll past the top or bottom of a modal in either of those devices' browsers, the `<body>` content will begin to scroll. See [Chrome bug #175502](https://bugs.chromium.org/p/chromium/issues/detail?id=175502) (fixed in Chrome v40) and [WebKit bug #153852](https://bugs.webkit.org/show_bug.cgi?id=153852).

### iOS text fields 와 scrolling

As of iOS 9.2, while a modal is open, if the initial touch of a scroll gesture is within the boundary of a textual `<input>` or a `<textarea>`, the `<body>` content underneath the modal will be scrolled instead of the modal itself. See [WebKit bug #153856](https://bugs.webkit.org/show_bug.cgi?id=153856).

### 네비게이션바 드롭다운

The `.dropdown-backdrop` element isn't used on iOS in the nav because of the complexity of z-indexing. Thus, to close dropdowns in navbars, you must directly click the dropdown element (or [any other element which will fire a click event in iOS](https://developer.mozilla.org/en-US/docs/Web/Events/click#Safari_Mobile)).

## 브라우저 zooming

Page zooming inevitably presents rendering artifacts in some components, both in Bootstrap and the rest of the web. Depending on the issue, we may be able to fix it (search first and then open an issue if need be). However, we tend to ignore these as they often have no direct solution other than hacky workarounds.

## Sticky `:hover`/`:focus` on mobile

Even though real hovering isn't possible on most touchscreens, most mobile browsers emulate hovering support and make `:hover` "sticky". In other words, `:hover` styles start applying after tapping an element and only stop applying after the user taps some other element. On mobile-first sites, this behavior is normally undesirable.

Bootstrap includes a workaround for this, although it is disabled by default. By setting `$enable-hover-media-query` to `true` when compiling from Sass, Bootstrap will use [mq4-hover-shim](https://github.com/twbs/mq4-hover-shim) to disable `:hover` styles in browsers that emulate hovering, thus preventing sticky `:hover` styles. There are some caveats to this workaround; see the shim's documentation for details.

## 프린팅

Even in some modern browsers, printing can be quirky.
일부 모던 브라우저에서도 인쇄가 기발합니다.

Safari v8.0부터 고정폭(fixed-width) `.container` 클래스를 사용하면 Safari에서 인쇄 할 때 글꼴 크기가 비정상적으로 작아 질 수 있습니다. 자세한 내용은 [issue #14868]({{ site.repo }}/issues/14868) 및 [WebKit bug #138192](https://bugs.webkit.org/show_bug.cgi?id=138192) 를 참조하십시오. 잠재적 해결 방법중 하나는 아래의 CSS 입니다.

{% highlight css %}
@media print {
  .container {
    width: auto;
  }
}
{% endhighlight %}

## Android stock browser

Out of the box, Android 4.1 (and even some newer releases apparently) ship with the Browser app as the default web browser of choice (as opposed to Chrome). Unfortunately, the Browser app has lots of bugs and inconsistencies with CSS in general.

#### Select menu

On `<select>` elements, the Android stock browser will not display the side controls if there is a `border-radius` and/or `border` applied. (See [this StackOverflow question](https://stackoverflow.com/questions/14744437/html-select-box-not-showing-drop-down-arrow-on-android-version-4-0-when-set-with) for details.) Use the snippet of code below to remove the offending CSS and render the `<select>` as an unstyled element on the Android stock browser. The user agent sniffing avoids interference with Chrome, Safari, and Mozilla browsers.

{% highlight html %}
<script>
$(function () {
  var nua = navigator.userAgent
  var isAndroid = (nua.indexOf('Mozilla/5.0') > -1 && nua.indexOf('Android ') > -1 && nua.indexOf('AppleWebKit') > -1 && nua.indexOf('Chrome') === -1)
  if (isAndroid) {
    $('select.form-control').removeClass('form-control').css('width', '100%')
  }
})
</script>
{% endhighlight %}

Want to see an example? [Check out this JS Bin demo.](http://jsbin.com/OyaqoDO/2)

## Validators

In order to provide the best possible experience to old and buggy browsers, Bootstrap uses [CSS browser hacks](http://browserhacks.com/) in several places to target special CSS to certain browser versions in order to work around bugs in the browsers themselves. These hacks understandably cause CSS validators to complain that they are invalid. In a couple places, we also use bleeding-edge CSS features that aren't yet fully standardized, but these are used purely for progressive enhancement.

These validation warnings don't matter in practice since the non-hacky portion of our CSS does fully validate and the hacky portions don't interfere with the proper functioning of the non-hacky portion, hence why we deliberately ignore these particular warnings.

Our HTML docs likewise have some trivial and inconsequential HTML validation warnings due to our inclusion of a workaround for [a certain Firefox bug](https://bugzilla.mozilla.org/show_bug.cgi?id=654072).
