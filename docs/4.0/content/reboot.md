---
layout: docs
title: 리부트 Reboot
description: Reboot, a collection of element-specific CSS changes in a single file, kickstart Bootstrap to provide an elegant, consistent, and simple baseline to build upon. 요소별 CSS 변경사항 모음인 리부트는 구축 할때 우아하고 일관되며 심플한 기준치를 제공합니다.
group: content
redirect_from: "/docs/4.0/content/"
toc: true
---




## 접근법

리부트는 Normalize를 사용하여 빌드되며, 요소 선택자만을 사용하여 독창적인 스타일의 많은 HTML 요소를 제공합니다. 추가적인 스타일은 클래스 만으로 수행됩니다. 예를 들어 보다 단순한 기준치를 위해 `<table>` 스타일을 리부트한 다음 후에 `.table`, `.table-bordered`, 등을 제공합니다.

Here are our guidelines and reasons for choosing what to override in Reboot:
리부트 시에 덮어쓸 대상을 선택하기 위한 가이드라인과 이유는 다음과 같습니다.

- 확장 가능한 구성 요소의 간격에 대해 `em` 대신 `rem`을 사용하도록 일부 브라우저 기본 값을 업데이트합니다.
- Avoid `margin-top`. Vertical margins can collapse, yielding unexpected results. More importantly though, a single direction of `margin` is a simpler mental model.
- `margin-top`을 피하십시오. 수직 마진은 합쳐질수 있어 예기치 않은 결과를 초래할 수 있습니다. 더 중요한 것은 한방향의 `margin`은 보다 단순한 mental model 입니다.
- 디바이스 사이즈에 맞게 쉽게 크기조정 하려면 블록 요소는 `margin`에 `rem`을 사용해야 합니다.
- 가급적이면 `inherit`을 사용하여 `font` 관련 속성의 선언을 최소한으로 유지하십시오.

## 페이지 기본값

`<html>`과 `<body>`는 더 나은 페이지 전체 기본값을 제공하도록 업데이트 되었습니다. 더 구체적으로:

- `box-sizing`은 모든 요소(`*::before` 와 `*::after` 포함)에 `border-box`로 전역적으로 설정 됩니다. 이렇게하면 padding 또는 border로 인해 요소에 선언된 너비가 결코 초과되지 않습니다.
  - No base `font-size` is declared on the `<html>`, but `16px` is assumed (the browser default). `font-size: 1rem` is applied on the `<body>` for easy responsive type-scaling via media queries while respecting user preferences and ensuring a more accessible approach.
  - 기본 `font-size`는 `<html>`에 선언되지 않지만  `16px`로 간주됩니다 (브라우저 기본값). `font-size: 1rem`은 `<body>`에 적용되어 사용자 설정을 존중하고 보다 이해하기 쉬운 접근을 보장하면서 미디어 쿼리를 통해 반응형 폰트 크기조정을 쉽게 합니다.
- `<body>` 에는 또한 `font-family`, `line-height`, 과 `text-align`이 셋팅 됩니다. 이것은 폰트 불일치를 방지하기 위해 나중에 일부 form 요소로 상속됩니다.
- 안전하게 `<body>`에는 `background-color`가 선언되어 있으며 기본값은 `#fff` 입니다.

## 기본 폰트 스택

기본 웹 폰트 (Helvetica Neue, Helvetica 및 Arial)는 부트스트랩 4에 포함되지 않았으며 모든 디바이스 및 OS에서 최적의 텍스트 렌더링을 위해 "기본 글꼴 스택"으로 대체 되었습니다. 이 스매싱 매거진 기사에서 [기본 글꼴 스택](https://www.smashingmagazine.com/2015/11/using-system-ui-fonts-practical-guide/)에 대해 자세히 읽어보십시오.

{% highlight sass %}
$font-family-sans-serif:
  // Safari for OS X and iOS (San Francisco)
  -apple-system,
  // Chrome < 56 for OS X (San Francisco)
  BlinkMacSystemFont,
  // Windows
  "Segoe UI",
  // Android
  "Roboto",
  // Basic web fallback
  "Helvetica Neue", Arial, sans-serif,
  // Emoji fonts
  "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol" !default;
{% endhighlight %}

이 `font-family`는 `<body>`에 적용되고 부트스트랩 전역에서 자동으로 상속됩니다. 전역 `font-family`를 바꾸려면 `$font-family-base`를 갱신하고 부트스트랩을 다시 컴파일 하십시오.

## 제목과 단락

모든 제목요소들 (예 : `<h1>` 과 `<p>`)에는 `margin-top`이 제거 되었습니다. 제목요소 에는 `margin-bottom: .5rem`이 `<p>`에는 `margin-bottom: 1rem`이 쉬운 여백처리를 위해 추가 되었습니다.

<table>
  <thead>
    <tr>
      <th>제목</th>
      <th>예제</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>
        {% markdown %}`<h1></h1>`{% endmarkdown %}
      </td>
      <td><span class="h1">h1. 부트스트랩 제목</span></td>
    </tr>
    <tr>
      <td>
        {% markdown %}`<h2></h2>`{% endmarkdown %}
      </td>
      <td><span class="h2">h2. 부트스트랩 제목</span></td>
    </tr>
    <tr>
      <td>
        {% markdown %}`<h3></h3>`{% endmarkdown %}
      </td>
      <td><span class="h3">h3. 부트스트랩 제목</span></td>
    </tr>
    <tr>
      <td>
        {% markdown %}`<h4></h4>`{% endmarkdown %}
      </td>
      <td><span class="h4">h4. 부트스트랩 제목</span></td>
    </tr>
    <tr>
      <td>
        {% markdown %}`<h5></h5>`{% endmarkdown %}
      </td>
      <td><span class="h5">h5. 부트스트랩 제목</span></td>
    </tr>
    <tr>
      <td>
        {% markdown %}`<h6></h6>`{% endmarkdown %}
      </td>
      <td><span class="h6">h6. 부트스트랩 제목</span></td>
    </tr>
  </tbody>
</table>

## 목록 Lists

모든 목록(`<ul>`, `<ol>` 및 `<dl>`)은 `margin-top`이 제거되고 `margin-bottom: 1rem` 이 적용 되었습니다. 중첩 목록에는 `margin-bottom` 없습니다.

<div class="bd-example">
{% markdown %}
* 동해물과 백두산이 마르고 닳도록 하느님이
* 보우하사 우리 나라만세 무궁화 삼천리 화려 강산
* 대한사람 대한으로 길이 보전하세
* 남산 위에 저 소나무 철갑을 두른듯
* 바람서리 불변함은 우리 기상일세
  * 무궁화 삼천리 화려 강산 대한사람
  * 대한으로 길이 보전하세 가을 하늘 공활한데
  * 높고 구름 없이 밝은 달은 우리 가슴
  * 일편단심일세 무궁화 삼천리 화려 강산
* 대한사람 대한으로 길이 보전하세
* 이 기상과 이 마음으로 충성을 다하여
* 괴로우나 즐거우나 나라사랑하세 무궁화 삼천리

1. 동해물과 백두산이 마르고 닳도록 하느님이
2. 보우하사 우리 나라만세 무궁화 삼천리 화려 강산
3. 대한사람 대한으로 길이 보전하세
4. 남산 위에 저 소나무 철갑을 두른듯
5. 바람서리 불변함은 우리 기상일세
6. 무궁화 삼천리 화려 강산 대한사람
7. 대한으로 길이 보전하세 가을 하늘 공활한데
8. 높고 구름 없이 밝은 달은 우리 가슴
{% endmarkdown %}
</div>


보다 단순한 스타일, 명확한 계층구조 및 더 나은 간격조정을 위해 정의형 목록에 `margin`이 업데이트 되었습니다. `<dd>`는 `margin-left`가 `0`으로 설정되었고 `margin-bottom: .5rem`이 추가 되었습니다. `<dt>`는 **굵게** 표시 됩니다.

<div class="bd-example">
{% markdown %}
<dl>
  <dt>정의형 목록</dt>
  <dd>정의형 목록은 용어 정의에 적합 합니다.</dd>
  <dt>애국가 1절</dt>
  <dd>동해물과 백두산이 마르고 닳도록 하느님이.</dd>
  <dd>보우하사 우리 나라만세 무궁화 삼천리 화려 강산.</dd>
  <dt>애국가 2절</dt>
  <dd>남산 위에 저 소나무 철갑을 두른듯.</dd>
</dl>
{% endmarkdown %}
</div>

## 여백 서식이 적용된 텍스트

`<pre>` 요소는 `margin-top`을 제거하고 `margin-bottom`에 대해 `rem` 단위를 사용하세요.

<div class="bd-example">
{% markdown %}
<pre>
.example-element {
  margin-bottom: 1rem;
}
</pre>
{% endmarkdown %}
</div>

## 테이블

테이블은 `<caption>`에 스타일을 지정하고 테두리를 상쇄하고 전체적으로 일관된 `text-align`을 유지하도록 약간 조정 되었습니다. border, padding 등에 대한 추가 변경 사항은 [`.table`]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/tables/) 클래스와 함께 제공 됩니다.

<div class="bd-example">
  <table>
    <caption>
      이것은 예제 테이블이며 내용을 설명하는 캡션입니다.
    </caption>
    <thead>
      <tr>
        <th>Table heading</th>
        <th>Table heading</th>
        <th>Table heading</th>
        <th>Table heading</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
    </tbody>
  </table>
</div>

## 폼 Forms

더 간단한 기본 스타일을 위해 다양한 폼 요소가 리부트 되었습니다. 다음은 가장 주목할 만한 변경사항 입니다.

- `<fieldset>`에는 border, padding 또는 margin이 없으므로 개별 입력폼이나 입력폼 그룹에 대한 wrapper로 쉽게 사용할 수 있습니다.
- `<legend>`는 fieldset와 마찬가지로 제목처럼 표시되도록 재구성 되었습니다.
- `<label>`은 `margin`을 적용할수 있도록 `display: inline-block`이 적용 되었습니다.
- `<input>`, `<select>`, `<textarea>` 및 `<button>`는 대부분 Normalize로 처리되지만 리부트에서는 `margin`을 제거하고 `line-height: inherit`도 설정 합니다.
- `<textarea>`는 가로 크기 조정이 종종 페이지 레이아웃을 깨지게 하기 때문에 세로로만 크기를 조정할 수 있도록 수정 되었습니다.

이러한 변경 사항은 아래에서 확인할 수 있습니다.

<form class="bd-example">
  <fieldset>
    <legend>legend 예제</legend>

    <p>
      <label for="input">input 예제</label>
      <input type="text" id="input" placeholder="input 예제">
    </p>

    <p>
      <label for="select">select 예제</label>
      <select id="select">
        <option value="">선택하세요...</option>
        <optgroup label="항목 그룹 1">
          <option value="">항목 1</option>
          <option value="">항목 2</option>
          <option value="">항목 3</option>
        </optgroup>
        <optgroup label="항목 그룹 2">
          <option value="">항목 4</option>
          <option value="">항목 5</option>
          <option value="">항목 6</option>
        </optgroup>
      </select>
    </p>

    <p>
      <label>
        <input type="checkbox" value="">
        이 체크박스를 체크 하십시오.
      </label>
    </p>

    <p>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios1" value="option1" checked>
        Option one is this and that
      </label>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios2" value="option2">
        Option two is something else that's also super long to demonstrate the wrapping of these fancy form controls.
      </label>
      <label>
        <input type="radio" name="optionsRadios" id="optionsRadios3" value="option3" disabled>
        Option three is disabled
      </label>
    </p>

    <p>
      <label for="textarea">textarea 예제</label>
      <textarea id="textarea" rows="3"></textarea>
    </p>

    <p>
      <label for="time">temporal 예제</label>
      <input type="datetime-local" id="time">
    </p>

    <p>
      <label for="output">output 예제</label>
      <output name="result" id="output">100</output>
    </p>

    <p>
      <button type="submit">submit 버튼</button>
      <input type="submit" value="Input submit 버튼">
      <input type="button" value="Input 버튼">
    </p>

    <p>
      <button type="submit" disabled>submit 버튼</button>
      <input type="submit" value="Input submit 버튼" disabled>
      <input type="button" value="Input 버튼" disabled>
    </p>
  </fieldset>
</form>

## 기타 요소

### 주소 Address

 `<address>`s are for presenting contact information for the nearest ancestor (or an entire body of work). Preserve formatting by ending lines with `<br>`.

`<address>` 요소는 브라우저 기본 `font-style`인 `italic`에서 `normal`로 재설정 하도록 업데이트 되었습니다. `line-height` 도 상속되며 `margin-bottom: 1rem`이 추가 되었습니다. `<address>`는 가장 가까운 조상 (또는 전체 작업 본문)에 대한 연락처 정보를 제공하기 위한 것입니다. `<br>`로 끝나는 문자를 서식으로 유지하십시오.

<div class="bd-example">
  <address>
    <strong>대한주식회사</strong><br>
    서울특별시 중구 명동<br>
    세종대로 110<br>
    <abbr title="Phone">전화:</abbr> (02) 456-7890
  </address>

  <address>
    <strong>성명</strong><br>
    <a href="mailto:#">first.last@example.com</a>
  </address>
</div>

### 인용문 Blockquote

blockquote의 기본 `margin`은 `1em 40px`이므로 다른 요소와의 일관성을 위해이 값을 `0 0 1rem` 으로 재설정 합니다.

<div class="bd-example">
  <blockquote class="blockquote">
    <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세</p>
    <footer>Someone famous in <cite title="Source Title">Source Title</cite></footer>
  </blockquote>
</div>

### 인라인 요소 Inline elements

`<abbr>` 요소는 단락 텍스트 사이에서 눈에 띄도록 기본 스타일링을 받습니다.

<div class="bd-example">
  Nulla <abbr title="attribute">attr</abbr> vitae elit libero, a pharetra augue.
</div>

## HTML5 `[hidden]` 속성

HTML5 adds [a new global attribute named `[hidden]`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden), which is styled as `display: none` by default. Borrowing an idea from [PureCSS](https://purecss.io/), we improve upon this default by making `[hidden] { display: none !important; }` to help prevent its `display` from getting accidentally overridden. While `[hidden]` isn't natively supported by IE10, the explicit declaration in our CSS gets around that problem.

HTML5는 [`[hidden]`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/hidden) 이라는 새로운 전역 속성을 추가합니다. 기본적으로 `display: none`이 지정 됩니다. [PureCSS](https://purecss.io/)에서 아이디어를 빌리자면, 우리는 `[hidden] { display: none !important; }`을 사용하여 `display`가 실수로 무시되는 것을 방지 할 수 있습니다. `[hidden]`은 기본적으로 IE10에서 지원하지 않지만 CSS의 명시적 선언은 이러한 문제를 해결합니다.

{% highlight html %}
<input type="text" hidden>
{% endhighlight %}

{% callout warning %}
#### jQuery와의 비호환성

`[hidden]`은 jQuery의 `$(...).hide()` 및 `$(...).show()` 메소드와 호환되지 않습니다. 그러므로 우리는 현재 요소 `display` 관리를 위한 다른 기법에 비해 `[hidden]`을 추천하지 않습니다.
{% endcallout %}

단순히 요소의 가시성을 토글 하려면 해당 요소의 `display`가 수정되지 않고 요소가 문서의 흐름에 영향을 미칠수 있으므로 대신 [`.invisible` class]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/visibility/)를 사용하십시오.

To merely toggle the visibility of an element, meaning its `display` is not modified and the element can still affect the flow of the document, use [the `.invisible` class]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/visibility/) instead.

## 터치를 위한 Click delay 최적화

Traditionally, browsers on touchscreen devices have a delay of approximately 300ms between the end of a "tap" – the moment when a finger/stylus is lifted from screen – and the [`click` event](https://developer.mozilla.org/en-US/docs/Web/Events/click) being fired. This delay is necessary for these browsers to correctly handle "double-tap to zoom" gestures without prematurely triggering actions or links after the first "tap", but it can make your site feel slightly sluggish and unresponsive.

일반적으로 터치 스크린 디바이스의 브라우저는 "tap"(손가락/스타일러스를 화면에서 들어 올린진 순간)이 끝나는 순간에서 [`click` 이벤트](https://developer.mozilla.org/en-US/docs/Web/Events/click)가 시작될 때까지 약 300ms의 지연현상이 있습니다. 이 지연은 이러한 브라우저가 첫
번째 "탭" 이후에 동작이나 링크를 올바르게 트리거 하지 않고 "double-tap to zoom" 동작을 올바르게 처리하는 데 필요하지만 사이트가 약간 느린 반응이 느껴질 수 있습니다.

Most mobile browsers automatically optimize away this 300ms delay for sites that use the `width=device-width` property as part of their [responsive meta tag]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/introduction/#responsive-meta-tag) (as well as for sites that disable zooming, for instance with `user-scalable=no`, though this practice is strongly discouraged for accessibility and usability reasons). The biggest exceptions here are IE11 on Windows Phone 8.1, and iOS Safari (and any other iOS WebView-based browser) [prior to iOS 9.3](https://webkit.org/blog/5610/more-responsive-tapping-on-ios/).

대부분의 모바일 브라우저는 [반응형 meta tag]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/introduction/#responsive-meta-tag)중에 `width=device-width` 속성을 사용하는 사이트에 대해 300ms 지연현상을 자동으로 최적화 합니다 (접근성과 사용성 면에서 강력하게 권장되지는 않지만 예를 들면 `user-scalable = no`를 사용하여 줌 기능을 사용하지 않는 사이트들에 대해서도) 여기에서 가장 큰 예외는 Windows Phone 8.1의 IE11과 [iOS 9.3 이전](https://webkit.org/blog/5610/more-responsive-tapping-on-ios/)의 iOS Safari (및 기타 iOS WebView 기반 브라우저)입니다.


On touch-enabled laptop/desktop devices, IE11 and Microsoft Edge are currently the only browsers with "double-tap to zoom" functionality. As the [responsive meta tag]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/introduction/#responsive-meta-tag) is ignored by all desktop browsers, using `width=device-width` will have no effect on the 300ms delay here.

터치를 지원하는 노트북/데스크탑 디바이스에서 IE11 및 Microsoft Edge는 현재 "double-tap to zoom" 기능이 있는 유일한 브라우저 입니다. [반응형 meta tag]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/introduction/#responsive-meta-tag)는 모든 데스크탑 브라우저에서 무시되므로 `width=device-width`를 사용하면 300ms 지연현상에 아무런 영향을 미치지 않습니다.

To address this problem in IE11 and Microsoft Edge on desktop, as well as IE11 on Windows Phone 8.1, Bootstrap explicitly uses the [`touch-action:manipulation` CSS property](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action) on all interactive elements (such as buttons and links). This property essentially disables double-tap functionality on those elements, eliminating the 300ms delay.

부트스트랩은 Windows Phone 8.1의 IE11 뿐만 아니라 데스크탑의 IE11 과 Microsoft Edge에서 이 문제를 해결하기 위해 모든 상호작용 요소(버튼 및 링크)에서 [`touch-action:manipulation` CSS 속성](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action)를 명시적으로 사용합니다. 이 속성은 본질적으로 요소에 대해 double-tap 기능을 사용하지 못하게 하므로 300ms의 지연현상이 없습니다.

iOS 이전 버전(9.3 이전)의 경우 제안된 방법은 [FastClick](https://github.com/ftlabs/fastclick)과 같은 추가 스크립트를 사용하여 지연을 명시적으로 해결하는 것입니다.

자세한 내용은 [터치스크린 상호작용을 위해 300ms 지연현상 억제](https://patrickhlauke.github.io/touch/tests/results/#suppressing-300ms-delay)하기 위한 호환성 표를 참조하십시오.
