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
  <img class="card-img-top" data-src="holder.js/100px180/" alt="카드 이미지 캡션">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">카드 제목을 작성하고 카드의 내용을 대량으로 작성할 수 있는 몇가지 빠른 예제 텍스트.</p>
    <a href="#" class="btn btn-primary">어딘가에 가다</a>
  </div>
</div>
{% endexample %}

## 컨텐츠 타입

카드는 이미지, 텍스트, 목록 그룹, 링크 등 다양한 콘텐츠를 지원합니다. 다음은 지원되는 항목의 예입니다.

### Body

The building block of a card is the `.card-body`. Use it whenever you need a padded section within a card.
카드의 구성 블럭요소는 `.card-body` 입니다. 카드 안에 padded이 필요한 부분이 필요할 때마다 사용하십시오.

{% example html %}
<div class="card">
  <div class="card-body">
    이것은 카드 본문 내의 일부 텍스트입니다.
  </div>
</div>
{% endexample %}

### 타이틀, 텍스트, 그리고 링크

카드 타이틀은 `<h*>` 태그에 `.card-title` 을 추가하여 사용합니다. 마찬가지로, `<a>` 태그에 `.card-link`를 추가하여 링크를 추가하고 서로 옆에 배치합니다.

서브 타이틀은 `<h*>` 태그에 `.card-subtitle`을 추가하여 사용합니다. `.card-title` 및 `.card-subtitle` 항목이 `.card-body` 항목에 배치되면 카드 타이틀과 서브 타이틀은 잘 정렬됩니다.

{% example html %}
<div class="card" style="width: 20rem;">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <h6 class="card-subtitle mb-2 text-muted">카드 서브 타이틀</h6>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="card-link">카드 링크</a>
    <a href="#" class="card-link">또 다른 링크</a>
  </div>
</div>
{% endexample %}

### 이미지

`.card-img-top` places an image to the top of the card. With `.card-text`, text can be added to the card. Text within `.card-text` can also be styled with the standard HTML tags.

`.card-img-top`은 카드상단의 이미지에 적용합니다. `.card-text`를 사용하면 텍스트를 카드에 추가 할 수 있습니다. `.card-text` 내의 텍스트는 표준 HTML 태그로 스타일을 지정할 수도 있습니다.

{% example html %}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=Image cap" alt="카드 이미지 캡션">
  <div class="card-body">
    <p class="card-text">카드 제목을 기반으로하고 카드 내용의 대부분을 구성하는 간단한 예제 텍스트.</p>
  </div>
</div>
{% endexample %}

### 목록 그룹

플러시(flush) 목록 그룹으로 카드에 콘텐츠 목록을 생성합니다.

{% example html %}
<div class="card" style="width: 20rem;">
  <ul class="list-group list-group-flush">
    <li class="list-group-item">동해물과 백두산이</li>
    <li class="list-group-item">마르고 닳도록 하느님이</li>
    <li class="list-group-item">보우하사 우리 나라만세</li>
  </ul>
</div>
{% endexample %}

### Kitchen sink

여러 콘텐츠 유형을 믹스 앤 매치하여 필요한 카드를 만들거나 거기에 모든 것을 던져 넣으십시오. 아래에는 이미지 스타일, 블록, 텍스트 스타일 및 목록 그룹이 모두 고정폭 카드로 싸여 있습니다.

{% example html %}
<div class="card" style="width: 20rem;">
  <img class="card-img-top" data-src="holder.js/100px180/?text=이미지" alt="카드 이미지 캡션">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">카드 제목을 기반으로하고 카드 내용의 대부분을 구성하는 간단한 예제 텍스트.</p>
  </div>
  <ul class="list-group list-group-flush">
    <li class="list-group-item">동해물과 백두산이</li>
    <li class="list-group-item">마르고 닳도록 하느님이</li>
    <li class="list-group-item">보우하사 우리 나라만세</li>
  </ul>
  <div class="card-body">
    <a href="#" class="card-link">카드 링크</a>
    <a href="#" class="card-link">또 다른 링크</a>
  </div>
</div>
{% endexample %}

### 헤더와 풋터

카드에 선택적으로 헤더 또는 풋터를 추가하십시오.

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

카드 헤더는 `<h*>` 요소에 `.card-header`를 추가하여 스타일을 지정할 수 있습니다.

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
    인용구
  </div>
  <div class="card-body">
    <blockquote class="blockquote mb-0">
      <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.</p>
      <footer class="blockquote-footer">안익태 작곡 <cite title="Source Title">애국가</cite></footer>
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

카드는 특별한 `width`가 없는 것으로 가정하므로 별도로 언급하지 않는 한 100%로 넓어집니다. 사용자 맞춤 CSS, 그리드 클래스, 그리드 Sass 믹스인 또는 유틸리티를 사용하여 필요에 따라 변경할 수 있습니다.

### 그리드 마크업 사용

Using the grid, wrap cards in columns and rows as needed.
그리드를 사용하여 필요에 따라 칼럼과 행(row)에 카드를 감사쎄요.

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

[사이징 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/sizing/)  사용하여 카드의 너비를 빠르게 설정할 수 있습니다.

{% example html %}
<div class="card w-75">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>

<div class="card w-50">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">With supporting text below as a natural lead-in to additional content.</p>
    <a href="#" class="btn btn-primary">Button</a>
  </div>
</div>
{% endexample %}

### 사용자 정의 CSS

맞춤 CSS나 인라인 스타일로 너비를 설정하십시오.

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

[텍스트 정렬 클래스]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment)를 사용하여 전체 또는 특정 부분에서 모든 카드의 텍스트 정렬을 신속하게 변경할 수 있습니다.

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

부트스트랩의 [네이게이션 컴포넌트]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/navs/)를 사용하여 카드의 헤더 (또는 블록)에 네비게이션을 추가하십시오.

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

카드에는 이미지 구성을 위해 몇 가지 옵션이 있습니다. 카드의 양쪽 끝에 "이미지 캡"을 추가하거나 카드 내용으로 이미지를 겹치거나 간단히 이미지를 카드에 삽입하십시오.

### 이미지 캡

Similar to headers and footers, cards can include top and bottom "image caps"—images at the top or bottom of a card.
헤더와 풋터와 마찬가지로 카드에는 상단 및 하단 "image caps"이 포함될 수 있습니다. 이 이미지는 카드의 상단 또는 하단에 이미지를 나타냅니다.

{% example html %}
<div class="card mb-3">
  <img class="card-img-top" data-src="holder.js/100px180/" alt="Card image cap">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-muted">3분전 수정됨</small></p>
  </div>
</div>
<div class="card">
  <div class="card-body">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text"><small class="text-muted">3분전 수정됨</small></p>
  </div>
  <img class="card-img-bottom" data-src="holder.js/100px180/" alt="카드 이미지 캡">
</div>
{% endexample %}

### 이미지 오버레이 (overlays)

Turn an image into a card background and overlay your card's text. Depending on the image, you may or may not need additional styles or utilities.
이미지를 카드 배경으로 바꾸고 카드의 텍스트를 오버레이 합니다. 이미지에 따라 추가 스타일이나 유틸리티가 필요할 수도 있고 없을 수도 있습니다.

{% example html %}
<div class="card bg-dark text-white">
  <img class="card-img" data-src="holder.js/100px270/#55595c:#373a3c/text:카드 이미지" alt="카드 이미지">
  <div class="card-img-overlay">
    <h4 class="card-title">카드 타이틀</h4>
    <p class="card-text">This is a wider card with supporting text below as a natural lead-in to additional content. This content is a little bit longer.</p>
    <p class="card-text">3분전 업데이트</p>
  </div>
</div>
{% endexample %}

## 카드 스타일

카드에는 백그라운드, 테두리 및 색상을 사용자 정의하는 다양한 옵션이 있습니다.

### 백그라운드와 칼라

[텍스트 및 백그라운드 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/)를 사용하여 카드 모양을 변경 하십시오.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="card{% unless color.name == "light" %} text-white{% endunless %} bg-{{ color.name }} mb-3" style="max-width: 20rem;">
  <div class="card-header">헤더</div>
  <div class="card-body">
    <h4 class="card-title">{{ color.name | capitalize }} 카드 타이틀</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

### 테두리

Use [border utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/) to change just the `border-color` of a card. Note that you can put `.text-{color}` classes on the parent `.card` or a subset of the card's contents as shown below.

[border 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/) 를 사용하여 카드의 `border-color`만 변경 하십시오. 다음과 같이 `.text-{color}` 클래스를 부모 `.card` 또는 카드 내용의 하위에 넣을 수 있습니다.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="card border-{{ color.name }} mb-3" style="max-width: 20rem;">
  <div class="card-header">헤더</div>
  <div class="card-body{% unless color.name == "light" %} text-{{ color.name }}{% endunless %}">
    <h4 class="card-title">{{ color.name | capitalize }} 카드 타이틀</h4>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
  </div>
</div>{% endfor %}
{% endexample %}

### 믹스인(Mixins) 유틸리티

필요에 따라 카드 헤더와 풋터의 테두리를 변경하고 `background-color` 을 `.bg-transparent`로 제거 할 수도 있습니다.

{% example html %}
<div class="card border-success mb-3" style="max-width: 20rem;">
  <div class="card-header bg-transparent border-success">헤더</div>
  <div class="card-body text-success">
    <h4 class="card-title">Success 카드 타이틀</h4>
    <p class="card-text">카드 제목을 기반으로하고 카드 내용의 대부분을 구성하는 간단한 예제 텍스트.</p>
  </div>
  <div class="card-footer bg-transparent border-success">풋터</div>
</div>
{% endexample %}

## 카드 레이아웃

부트스트랩에는 카드 내의 내용을 스타일링하는 것 외에도, 일련의 카드 레이아웃을 위한 몇가지 옵션이 있습니다. **당분간, 이러한 레이아웃 옵션은 아직 반응형이 적용되지 않았습니다**.


### 카드 그룹

카드 그룹을 사용하여 동일한 너비와 높이의 칼럼이 있는 단일 부착 요소로 카드들을 렌더링 하십시오. 카드 그룹은 균일한 크기 조정을 위해 `display: flex;`을 사용합니다.

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

풋터가 있는 카드 그룹을 사용하면, 컨텐츠가 자동으로 정렬됩니다.

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

### 카드 덱(deck)

Need a set of equal width and height cards that aren't attached to one another? Use card decks.
서로 붙어 있지 않은 동일한 폭과 높이의 카드 세트가 필요합니까? 카드덱을 사용하십시오.

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

카드 그룹과 마찬가지로 카드 덱(deck)에 있는 카드 풋터가 자동으로 정렬됩니다.

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

카드는 `.card-columns`로 둘러싸여 CSS 만으로 [Masonry](https://masonry.desandro.com/) 형 컬럼으로 구성될 수 있습니다. 카드들은 flexbox가 아닌  `column` CSS 속성을 사용하여 쉽게 정렬 할 수 있습니다. 카드는 위에서 아래로, 왼쪽에서 오른쪽으로 정렬됩니다.

**Heads up!** Your mileage with card columns may vary. To prevent cards breaking across columns, we must set them to `display: inline-block` as `column-break-inside: avoid` isn't a bulletproof solution yet.

**조심하세요!** 카드 열이 있는 마일리지는 다를 수 있습니다. 카드가 칼럼을 가로 지르지 못하게하려면 다음과 같이 표시되도록 설정해야합니다. `display: inline-block` in `column-break-inside: avoid`은 아직 완전한 솔루션이 아닙니다.

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
