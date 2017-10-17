---
layout: docs
title: 타이포그래피
description: 글로벌 설정, 헤드라인, 본문, 목록 등을 포함한 타이포그래피에 대한 문서와 예제.
group: content
toc: true
---



## 전역 설정

부트스트랩은 기본적으로 전역 display, typography 및 link 스타일을 설정 합니다. 더 많은 제어가 필요하면 [텍스트 유틸리티 클래스]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/)를 확인 하십시오.

- 각 OS 및 디바이스에 가장 적합한 `font-family`을 선택하는 [기본 폰트 스택]({{ site.baseurl }}/docs/{{ site.docs_version }}/content/reboot/#기본-폰트-스택)을 사용하십시오.
- 더 포괄적이고 이해하기 쉬운 폰트 크기조정을 위해 우리는 방문자가 필요에 따라 브라우저 기본값을 사용자 정의를 할 수 있도록 브라우저의 기본 루트 `font-size` (일반적으로 16 픽셀)를 사용합니다.
- `$font-family-base`, `$font-size-base`, 그리고 `$line-height-base` 속성을 폰트 기본 설정으로 `<body>` 적용하여 사용하세요.
- `$link-color`로 전역 링크 칼라를 설정하고 `:hover` 에만 링크 밑줄(underline)을 적용 하세요.
- `<body>`에 `background-color`을 설정하려면 `$body-bg`를 사용 하십시오 (기본적으로 `#fff`).

이러한 스타일은 `_reboot.scss`에서 찾을 수 있으며 전역 변수는 `_variables.scss`에서 정의됩니다. `rem`으로 `$font-size-base`를 설정 해야합니다.

## 제목 Headings

모든 HTML 제목요소 `<h1>`부터 `<h6>`까지 사용할 수 있습니다.

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

{% highlight html %}
<h1>h1. 부트스트랩 제목</h1>
<h2>h2. 부트스트랩 제목</h2>
<h3>h3. 부트스트랩 제목</h3>
<h4>h4. 부트스트랩 제목</h4>
<h5>h5. 부트스트랩 제목</h5>
<h6>h6. 부트스트랩 제목</h6>
{% endhighlight %}

제목 폰트 스타일을 일치시키고 관련 HTML 요소를 사용할 수 없는 경우 `.h1`에서 `.h6` 까지의 클래스도 사용할 수 있습니다.

{% example html %}
<p class="h1">h1. 부트스트랩 제목</p>
<p class="h2">h2. 부트스트랩 제목</p>
<p class="h3">h3. 부트스트랩 제목</p>
<p class="h4">h4. 부트스트랩 제목</p>
<p class="h5">h5. 부트스트랩 제목</p>
<p class="h6">h6. 부트스트랩 제목</p>
{% endexample %}

### 제목 사용자 정의 Customizing headings

포함된 유틸리티 클래스를 사용하여 부트스트랩 3의 작은 보조 제목을 재구성 하십시오.

<div class="bd-example">
  <span class="h3">
    멋진 제목 표시
    <small class="text-muted">희미한 보조 텍스트 사용</small>
  </span>
</div>

{% highlight html %}
<h3>
  멋진 제목 표시
  <small class="text-muted">희미한 보조 텍스트 사용</small>
</h3>
{% endhighlight %}

## Display headings

전통적인 헤딩 요소들은 페이지 콘텐츠에서 가장 잘 작동하도록 설계 되었습니다. 눈이 띄는 제목이 필요할 때는 **display heading** 으로 더 크고 좀더 독창적인 제목 스타일을 적용하는 사용하는 것을 고려해 보세요.

<div class="bd-example bd-example-type">
  <table class="table">
    <tbody>
      <tr>
        <td><span class="display-1">Display 1</span></td>
      </tr>
      <tr>
      <td><span class="display-2">Display 2</span></td>
      </tr>
      <tr>
      <td><span class="display-3">Display 3</span></td>
      </tr>
      <tr>
      <td><span class="display-4">Display 4</span></td>
      </tr>
    </tbody>
  </table>
</div>

{% highlight html %}
<h1 class="display-1">Display 1</h1>
<h1 class="display-2">Display 2</h1>
<h1 class="display-3">Display 3</h1>
<h1 class="display-4">Display 4</h1>
{% endhighlight %}

## 리드

단락에 `.lead`를 추가하여 눈에 띄게 만드십시오.

{% example html %}
<p class="lead">
  동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
</p>
{% endexample %}

## 인라인 텍스트 요소

일반적인 인라인 HTML5 요소의 스타일.

{% example html %}
<p>mark 태그를 사용하여 텍스트를 <mark>강조</mark> 표시 할 수 있습니다.</p>
<p><del>삭제된 텍스트로 간주됩니다.</del></p>
<p><s>더 이상 정확하지 않은 것으로 간주됩니다.</s></p>
<p><ins>문서에 추가되는 것으로 간주됩니다.</ins></p>
<p><u>언더라인 형태로 렌더링 됩니다.</u></p>
<p><small>작은 글자로 취급 됩니다.</small></p>
<p><strong>굵게 표시 됩니다.</strong></p>
<p><em>기울임 텍스트로 표시 됩니다.</em></p>
{% endexample %}

`.mark`와 `.small` 클래스는 `<mark>`와 `<small>`와 같은 스타일을 적용하는 동시에 태그가 가진 원치않는 의미적용을 피할 수 있습니다.

위에 표시되지 않았지만 HTML5의 `<b>` 및`<i>`를 자유롭게 사용하십시오. `<b>`은 중요성 의미를 부여하지 않고 단어나 문구를 강조표시 하기 위한 것이고 `<i>`는 주로 음성, 기술용어 등에 사용 됩니다.

## 텍스트 유틸리티

텍스트 정렬, 변환, 스타일, 굵기 및 색상을 [텍스트 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment)로 변경하십시오.

## 약어 Abbreviations

Stylized implementation of HTML's `<abbr>` element for abbreviations and acronyms to show the expanded version on hover. Abbreviations have a default underline and gain a help cursor to provide additional context on hover and to users of assistive technologies.

Add `.initialism` to an abbreviation for a slightly smaller font-size.

호버에 확장 된 버전을 표시하기위한 약어 및 머리 글자에 대한 HTML의 `<abbr>` 요소의 양식화 된 구현입니다. 약어에는 기본 밑줄이 있으며 hover와 보조 기술 사용자에 대한 추가 컨텍스트를 제공하는 도움말 커서가 있습니다.

조금 더 작은 글꼴 크기의 약어에 `.initialism`을 추가하십시오.

{% example html %}
<p><abbr title="attribute">attr</abbr></p>
<p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
{% endexample %}

## 인용구 Blockquotes

For quoting blocks of content from another source within your document. Wrap `<blockquote class="blockquote">` around any <abbr title="HyperText Markup Language">HTML</abbr> as the quote.

문서 내의 다른 소스에서 내용 인용하기. 인용 부호로 <abbr title="HyperText Markup Language">HTML</abbr> 주위에 `<blockquote class="blockquote">`를 둘러 쌉니다.

{% example html %}
<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
</blockquote>
{% endexample %}

### Naming a source

Add a `<footer class="blockquote-footer">` for identifying the source. Wrap the name of the source work in `<cite>`.

{% example html %}
<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
{% endexample %}

### Alignment

Use text utilities as needed to change the alignment of your blockquote.

{% example html %}
<blockquote class="blockquote text-center">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
{% endexample %}

{% example html %}
<blockquote class="blockquote text-right">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
{% endexample %}

## Lists

### Unstyled

Remove the default `list-style` and left margin on list items (immediate children only). **This only applies to immediate children list items**, meaning you will need to add the class for any nested lists as well.

{% example html %}
<ul class="list-unstyled">
  <li>Lorem ipsum dolor sit amet</li>
  <li>Consectetur adipiscing elit</li>
  <li>Integer molestie lorem at massa</li>
  <li>Facilisis in pretium nisl aliquet</li>
  <li>Nulla volutpat aliquam velit
    <ul>
      <li>Phasellus iaculis neque</li>
      <li>Purus sodales ultricies</li>
      <li>Vestibulum laoreet porttitor sem</li>
      <li>Ac tristique libero volutpat at</li>
    </ul>
  </li>
  <li>Faucibus porta lacus fringilla vel</li>
  <li>Aenean sit amet erat nunc</li>
  <li>Eget porttitor lorem</li>
</ul>
{% endexample %}

### Inline

Remove a list's bullets and apply some light `margin` with a combination of two classes, `.list-inline` and `.list-inline-item`.

{% example html %}
<ul class="list-inline">
  <li class="list-inline-item">Lorem ipsum</li>
  <li class="list-inline-item">Phasellus iaculis</li>
  <li class="list-inline-item">Nulla volutpat</li>
</ul>
{% endexample %}

### Description list alignment

Align terms and descriptions horizontally by using our grid system's predefined classes (or semantic mixins). For longer terms, you can optionally add a `.text-truncate` class to truncate the text with an ellipsis.

{% example html %}
<dl class="row">
  <dt class="col-sm-3">Description lists</dt>
  <dd class="col-sm-9">A description list is perfect for defining terms.</dd>

  <dt class="col-sm-3">Euismod</dt>
  <dd class="col-sm-9">
    <p>Vestibulum id ligula porta felis euismod semper eget lacinia odio sem nec elit.</p>
    <p>Donec id elit non mi porta gravida at eget metus.</p>
  </dd>

  <dt class="col-sm-3">Malesuada porta</dt>
  <dd class="col-sm-9">Etiam porta sem malesuada magna mollis euismod.</dd>

  <dt class="col-sm-3 text-truncate">Truncated term is truncated</dt>
  <dd class="col-sm-9">Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.</dd>

  <dt class="col-sm-3">Nesting</dt>
  <dd class="col-sm-9">
    <dl class="row">
      <dt class="col-sm-4">Nested definition list</dt>
      <dd class="col-sm-8">Aenean posuere, tortor sed cursus feugiat, nunc augue blandit nunc.</dd>
    </dl>
  </dd>
</dl>
{% endexample %}

## Responsive typography

*Responsive typography* refers to scaling text and components by simply adjusting the root element's `font-size` within a series of media queries. Bootstrap doesn't do this for you, but it's fairly easy to add if you need it.

Here's an example of it in practice. Choose whatever `font-size`s and media queries you wish.

{% highlight scss %}
html {
  font-size: 1rem;
}

@include media-breakpoint-up(sm) {
  html {
    font-size: 1.2rem;
  }
}

@include media-breakpoint-up(md) {
  html {
    font-size: 1.4rem;
  }
}

@include media-breakpoint-up(lg) {
  html {
    font-size: 1.6rem;
  }
}
{% endhighlight %}
