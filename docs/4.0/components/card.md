---
layout: docs
title: 카드
description: 부트스트랩 카드는 다양한 변형과 옵션을 갖춘 유연하고 확장 가능한 콘텐츠 컨테이너를 제공합니다.
group: components
toc: true
---


## 소개

**카드** 는 유연하고 확장 가능한 콘텐츠 컨테이너 입니다. 여기에는 헤더와 풋터, 다양한 컨텐트, 상황별 배경색 및 강력한 표시 옵션이 포함되어 있습니다.

부트스트랩 v3에 익숙하다면 panel, well 및 thumbnails로 대체 할 수 있습니다. 이러한 구성 요소와 유사한 기능은 카드의 수정자 클래스로 사용할 수 있습니다.

## 예제

카드는 가능한 적은 마크업과 스타일로 제작 되지만 여전히 적지않은 제어와 사용자 정의를 제공합니다. Flexbox로 제작되어 쉽게 정렬 할 수 있으며 다른 부트스트랩 컴포넌트와 잘 섞일 수 있습니다.

다음은 혼합된 컨텐츠와 고정 너비가 있는 기본 카드의 예제 입니다. 카드는 시작할 때 고정 너비가 없으므로 부모 요소의 전체 너비를 자연스럽게 채웁니다. 다양한 [크기 조정](#크기-조정) 옵션으로 쉽게 사용자 정의를 할 수 있습니다.

{% example html %}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

## 컨텐츠 타입

Cards support a wide variety of content, including images, text, list groups, links, and more. Below are examples of what's supported.

### Body

The building block of a card is the `.card-body`. Use it whenever you need a padded section within a card.

{% example html %}
<div class="card">
  <div class="card-body">
    This is some text within a card body.
  </div>
</div>
{% endexample %}

### 타이틀, 텍스트, 그리고 링크

Card titles are used by adding `.card-title` to a `<h*>` tag. In the same way, links are added and placed next to each other by adding `.card-link` to an `<a>` tag.

Subtitles are used by adding a `.card-subtitle` to a `<h*>` tag. If the `.card-title` and the `.card-subtitle` items are placed in a `.card-body` item, the card title and subtitle are aligned nicely.

{% example html %}
<div class="card" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
{% endexample %}

### 이미지

`.card-img-top` places an image to the top of the card. With `.card-text`, text can be added to the card. Text within `.card-text` can also be styled with the standard HTML tags.

{% example html %}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=Image cap" alt="Card image cap">
  <div class="card-body">
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>
{% endexample %}

### 목록 그룹

Create lists of content in a card with a flush list group.

{% example html %}
<div class="card" style="width: 20rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
</div>
{% endexample %}

### Kitchen sink

Mix and match multiple content types to create the card you need, or throw everything in there. Shown below are image styles, blocks, text styles, and a list group—all wrapped in a fixed-width card.

{% example html %}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=Image cap" alt="Card image cap">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">Cras justo odio</li>
    <li class="list-group-item">Dapibus ac facilisis in</li>
    <li class="list-group-item">Vestibulum at eros</li>
  </ul>
  <div class="card-body">
    <a href="#" class="card-link">Card link</a>
    <a href="#" class="card-link">Another link</a>
  </div>
</div>
{% endexample %}

### 헤더와 풋터

Add an optional header and/or footer within a card.

{% example html %}
<div class="card">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

Card headers can be styled by adding `.card-header` to `<h*>` elements.

{% example html %}
<div class="card">
  <h4 class="card-header">Featured</h4>
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

{% example html %}
<div class="card">
  <div class="card-header">
    Quote
  </div>
  <div class="card-body">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
    </blockquote>
  </div>
</div>
{% endexample %}

{% example html %}
<div class="card text-center">
  <div class="card-header">
    Featured
  </div>
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
  <div class="card-footer text-muted">
    2 days ago
  </div>
</div>
{% endexample %}

## 크기 조정

Cards assume no specific `width` to start, so they'll be 100% wide unless otherwise stated. You can change this as needed with custom CSS, grid classes, grid Sass mixins, or utilities.

### 그리드 마크업 사용

Using the grid, wrap cards in columns and rows as needed.

{% example html %}
<div class="row">
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h4 class="card-title">Special title treatment</h4>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
  <div class="col-sm-6">
    <div class="card">
      <div class="card-body">
        <h4 class="card-title">Special title treatment</h4>
        <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
        <a href="#" class="btn btn-primary">Go somewhere</a>
      </div>
    </div>
  </div>
</div>
{% endexample %}

### 유틸리티 사용

Use our handful of [available sizing utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/sizing/) to quickly set a card's width.

{% example html %}
<div class="card w-75">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>

<div class="card w-50">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>
{% endexample %}

### 사용자 정의 CSS

Use custom CSS in your stylesheets or as inline styles to set a width.

{% example html %}
<div class="card" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

## 텍스트 정렬

You can quickly change the text alignment of any card—in its entirety or specific parts—with our [text align classes]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment).

{% example html %}
<div class="card" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-center" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>

<div class="card text-right" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

## 네비게이션

Add some navigation to a card's header (or block) with Bootstrap's [nav components]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/navs/).

{% example html %}
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-tabs card-header-tabs">
      <li class="nav-item">
        <a class="nav-link active" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

{% example html %}
<div class="card text-center">
  <div class="card-header">
    <ul class="nav nav-pills card-header-pills">
      <li class="nav-item">
        <a class="nav-link active" href="#">Active</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Link</a>
      </li>
      <li class="nav-item">
        <a class="nav-link disabled" href="#">Disabled</a>
      </li>
    </ul>
  </div>
  <div class="card-body">
    <h4 class="card-title">Special title treatment</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
{% endexample %}

## 이미지

Cards include a few options for working with images. Choose from appending "image caps" at either end of a card, overlaying images with card content, or simply embedding the image in a card.

### 이미지 캡션

Similar to headers and footers, cards can include top and bottom "image caps"—images at the top or bottom of a card.

{% example html %}
<div class="card mb-3">
  <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
  </div>
</div>
<div class="card">
  <div class="card-body">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
  </div>
  <img class="card-img-bottom" data-src="holder.js/100px180/" alt="Card image cap">
</div>
{% endexample %}

### 이미지 오버레이 (overlays)

Turn an image into a card background and overlay your card's text. Depending on the image, you may or may not need additional styles or utilities.

{% example html %}
<div class="card bg-dark text-white">
  <img class="card-img" data-src="holder.js/100px270/#55595c:#373a3c/text:Card image" alt="Card image">
  <div class="card-img-overlay">
    <h4 class="card-title">Card title</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text">Last updated 3 mins ago</p>
  </div>
</div>
{% endexample %}

## 카드 스타일

Cards include various options for customizing their backgrounds, borders, and color.

### 백그라운드와 칼라

Use [text and background utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/) to change the appearance of a card.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="card{% unless color.name == "light" %} text-white{% endunless %} bg-{{ color.name }} mb-3" style="max-width: 20rem;">
  <div class="card-header">Header</div>
  <div class="card-body">
    <h4 class="card-title">{{ color.name | capitalize }} card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

### 테두리

Use [border utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/) to change just the `border-color` of a card. Note that you can put `.text-{color}` classes on the parent `.card` or a subset of the card's contents as shown below.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="card border-{{ color.name }} mb-3" style="max-width: 20rem;">
  <div class="card-header">Header</div>
  <div class="card-body{% unless color.name == "light" %} text-{{ color.name }}{% endunless %}">
    <h4 class="card-title">{{ color.name | capitalize }} card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>{% endfor %}
{% endexample %}

### 믹스인(Mixins) 유틸리티

You can also change the borders on the card header and footer as needed, and even remove their `background-color` with `.bg-transparent`.

{% example html %}
<div class="card border-success mb-3" style="max-width: 20rem;">
  <div class="card-header bg-transparent border-success">Header</div>
  <div class="card-body text-success">
    <h4 class="card-title">Success card title</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
  <div class="card-footer bg-transparent border-success">Footer</div>
</div>
{% endexample %}

## 카드 레이아웃

In addition to styling the content within cards, Bootstrap includes a few options for laying out series of cards. For the time being, **these layout options are not yet responsive**.

### 카드 그룹

Use card groups to render cards as a single, attached element with equal width and height columns. Card groups use `display: flex;` to achieve their uniform sizing.

{% example html %}
<div class="card-group">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
</div>
{% endexample %}

When using card groups with footers, their content will automatically line up.

{% example html %}
<div class="card-group">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
</div>
{% endexample %}

### 카드 테크 (decks)

Need a set of equal width and height cards that aren't attached to one another? Use card decks.

{% example html %}
<div class="card-deck">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px200/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
</div>
{% endexample %}

Just like with card groups, card footers in decks will automatically line up.

{% example html %}
<div class="card-deck">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
    </div>
    <div class="card-footer">
      <small class="text-muted">Last updated 3 mins ago</small>
    </div>
  </div>
</div>
{% endexample %}

### 카드 칼럼 (columns)

Cards can be organized into [Masonry](https://masonry.desandro.com/)-like columns with just CSS by wrapping them in `.card-columns`. Cards are built with CSS `column` properties instead of flexbox for easier alignment. Cards are ordered from top to bottom and left to right.

**Heads up!** Your mileage with card columns may vary. To prevent cards breaking across columns, we must set them to `display: inline-block` as `column-break-inside: avoid` isn't a bulletproof solution yet.

{% example html %}
<div class="card-columns">
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px160/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title that wraps to a new line</h4>
      <p class="card-text">This is a longer card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    </div>
  </div>
  <div class="card p-3">
    <blockquote class="blockquote mb-0 card-body">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">
        <small class="text-muted">
          Someone famous in <cite title="Source Title">Source Title</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card">
    <img class="card-img-top" data-src="holder.js/100px160/" alt="Card image cap">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card bg-primary text-white text-center p-3">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat.</p>
      <footer class="blockquote-footer">
        <small>
          Someone famous in <cite title="Source Title">Source Title</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card text-center">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This card has supporting text below as a natural lead-in to additional content.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
  <div class="card">
    <img class="card-img" data-src="holder.js/100px260/" alt="Card image">
  </div>
  <div class="card p-3 text-right">
    <blockquote class="blockquote mb-0">
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
      <footer class="blockquote-footer">
        <small class="text-muted">
          Someone famous in <cite title="Source Title">Source Title</cite>
        </small>
      </footer>
    </blockquote>
  </div>
  <div class="card">
    <div class="card-body">
      <h4 class="card-title">Card title</h4>
      <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This card has even longer content than the first to show that equal height action.</p>
      <p class="card-text"><small class="text-muted">Last updated 3 mins ago</small></p>
    </div>
  </div>
</div>
{% endexample %}

Card columns can also be extended and customized with some additional code. Shown below is an extension of the `.card-columns` class using the same CSS we use—CSS columns— to generate a set of responsive tiers for changing the number of columns.

{% highlight scss %}
.card-columns {
  @include media-breakpoint-only(lg) {
    column-count: 4;
  }
  @include media-breakpoint-only(xl) {
    column-count: 5;
  }
}
{% endhighlight %}
