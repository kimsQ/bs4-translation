---
layout: docs
title: 컬랩스 Collapse
description: 몇개의 클래스와 자바스크립트 플러그인을 사용하여 프로젝트 전체에 콘텐츠 가시성을 토글합니다.
group: components
toc: true
---



## 예제

클래스 변경을 통해 다른 요소를 표시하거나 숨기려면 아래 버튼을 클릭하세요.

- `.collapse` 는 내용을 숨깁니다.
- `.collapsing` 는 전환되는 동안 적용됩니다.
- `.collapse.show` 는 내용을 보여줍니다.

`href` 속성이 있는 링크 나 `data-target` 속성이 있는 버튼에 사용할 수 있습니다. 두 경우 모두 `data-toggle="collapse"` 가 필요합니다.

{% example html %}
<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
    href 링크
  </a>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#collapseExample" aria-expanded="false" aria-controls="collapseExample">
    data-target 버튼
  </button>
</p>
<div class="collapse" id="collapseExample">
  <div class="card card-body">
    동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세. 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 가을 하늘 공활한데 높고 구름 없이 밝은 달은 우리 가슴 일편단심일세
  </div>
</div>
{% endexample %}

## 멀티 타켓

A `<button>` or `<a>` can show and hide multiple elements by referencing them with a JQuery selector in its `href` or `data-target` attribute.
Multiple `<button>` or `<a>` can show and hide an element if they each reference it with their `href` or `data-target` attribute

`<button>` 또는 `<a>`는 JQuery 선택자인 `href` 또는 `data-target` 속성을 사용하여 복수의 요소를 표시하거나 숨길 수 있습니다. 복수의 `<button>` 또는 `<a>`는 그들의 `href` 또는 `data-target` 속성을 사용하여 요소를 표시하거나 숨길 수 있습니다.

{% example html %}
<p>
  <a class="btn btn-primary" data-toggle="collapse" href="#multiCollapseExample1" aria-expanded="false" aria-controls="multiCollapseExample1">첫번째 요소 토글</a>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target="#multiCollapseExample2" aria-expanded="false" aria-controls="multiCollapseExample2">두번째 요소 토글</button>
  <button class="btn btn-primary" type="button" data-toggle="collapse" data-target=".multi-collapse" aria-expanded="false" aria-controls="multiCollapseExample1 multiCollapseExample2">양쪽 요소 토글</button>
</p>
<div class="row">
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample1">
      <div class="card card-body">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
  <div class="col">
    <div class="collapse multi-collapse" id="multiCollapseExample2">
      <div class="card card-body">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
</div>
{% endexample %}

## 아코디언 예제

[카드]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/card/) 구성 요소를 사용하여, 기본 컬랩스 동작을 확장하여 아코디언(accordion)을 만들 수 있습니다.

{% example html %}
<div id="accordion" role="tablist">
  <div class="card">
    <div class="card-header" role="tab" id="headingOne">
      <h5 class="mb-0">
        <a data-toggle="collapse" href="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
          토글 가능한 그룹 항목 #1
        </a>
      </h5>
    </div>

    <div id="collapseOne" class="collapse show" role="tabpanel" aria-labelledby="headingOne" data-parent="#accordion">
      <div class="card-body">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" role="tab" id="headingTwo">
      <h5 class="mb-0">
        <a class="collapsed" data-toggle="collapse" href="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
          토글 가능한 그룹 항목 #2
        </a>
      </h5>
    </div>
    <div id="collapseTwo" class="collapse" role="tabpanel" aria-labelledby="headingTwo" data-parent="#accordion">
      <div class="card-body">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
  <div class="card">
    <div class="card-header" role="tab" id="headingThree">
      <h5 class="mb-0">
        <a class="collapsed" data-toggle="collapse" href="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
          토글 가능한 그룹 항목 #3
        </a>
      </h5>
    </div>
    <div id="collapseThree" class="collapse" role="tabpanel" aria-labelledby="headingThree" data-parent="#accordion">
      <div class="card-body">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
</div>
{% endexample %}

사용자 맞춤 마크업으로 아코디언을 만들 수도 있습니다. `data-children` 속성을 추가하고 토글 할수있는 형제 요소셋을 지정하십시오 (예:`.item`). 그런 다음 토글을 관련 콘텐츠에 연결하기 위해 위에 표시된 것과 동일한 속성 및 클래스를 사용합니다.

{% example html %}
<div id="exampleAccordion" data-children=".item">
  <div class="item">
    <a data-toggle="collapse" data-parent="#exampleAccordion" href="#exampleAccordion1" aria-expanded="true" aria-controls="exampleAccordion1">
      토글 아이템
    </a>
    <div id="exampleAccordion1" class="collapse show" role="tabpanel">
      <p class="mb-3">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </p>
    </div>
  </div>
  <div class="item">
    <a data-toggle="collapse" data-parent="#exampleAccordion" href="#exampleAccordion2" aria-expanded="false" aria-controls="exampleAccordion2">
      토글 아이템 2
    </a>
    <div id="exampleAccordion2" class="collapse" role="tabpanel">
      <p class="mb-3">
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </p>
    </div>
  </div>
</div>
{% endexample %}

## 접근성

컨트롤 요소에 `aria-expanded`를 추가 해야합니다. 이 특성은 스크린리더 및 유사한 보조기술에 컨트롤에 연결된 토글 가능한 요소의 현재 상태를 명시적으로 전달합니다. 토글 가능한 요소가 기본적으로 닫히면 컨트롤 요소의 속성은 `aria-expanded="false"` 값을 가져야합니다. `show` class를 사용하여 토글 가능한 요소를 기본적으로 열도록 설정 한 경우, 컨트롤에 `aria-expanded="true"` 를 설정 하십시오. 이 플러그인은 토글 가능한 요소가 열리거나 닫혔는지 여부에 따라 컨트롤의 이 속성을 자동으로 토글합니다.(JavaScript를 통해, 또는 사용자가 다른 컨트롤 요소를 트리거하여 동일한 토글 가능한 요소에 연결했는지 여부)

또한, 컨트롤 요소가 하나의 접을수 있는 요소를 타겟팅하는 경우 (즉, `data-target` 속성이 `id` 선택자를 가리키는 경우) `aria-controls` 속성을 컨트롤 요소에 추가 할 수 있습니다. 최신 스크린 리더 및 이와 유사한 보조 기술은 이 속성을 사용하여 접을 수 있는 요소 자체를 직접 탐색 할 수있는 추가 단축키를 사용자에게 제공합니다.

## 사용법

컬랩스 플러그인은 다음과 같은 몇가지 클래스를 사용하여 열고/접기를 처리합니다.

- `.collapse`는 컨텐츠를 숨깁니다.
- `.collapse.show`는 컨텐츠를 보여줍니다.
- `.collapsing`은 전환이 시작될 때 추가되고 완료되면 제거됩니다.

이러한 클래스는 `_transitions.scss` 에서 찾을 수 있습니다.

### data 속성 방식

`data-toggle="collapse"` 와 `data-target` 을 요소에 추가하면 하나 이상의 접을 수 있는 요소에 대한 제어가 자동으로 할당됩니다. `data-target` 속성은 열고/접기를 적용할 대상에 CSS 선택자를 허용합니다. 접을 수있는 요소에 `.collapse`를 추가 해야합니다. 기본으로 열린 상태를 원한다면 `.show`를 추가 하십시오.

접을수 있는 영역에 아코디언과 같은 그룹 관리를 추가하려면 `data-parent="#selector"` 데이터 속성을 추가하십시오. 이것을 실제로 보려면 데모를 참조하십시오.

### JavaScript 방식

수동으로 사용 설정 :

{% highlight js %}
$('.collapse').collapse()
{% endhighlight %}

### 옵션

옵션은 데이터 속성 또는 JavaScript를 통해 전달될 수 있습니다. 데이터 속성의 경우 `data-parent=""` 에서 처럼 `data-`에 옵션명을 추가하십시오.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <th style="width: 100px;">옵션명</th>
      <th style="width: 50px;">타입</th>
      <th style="width: 50px;">기본</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>parent</td>
      <td>selector | jQuery object | DOM element </td>
      <td>false</td>
      <td>parent가 제공된 경우, 지정된 parent 아래의 모든 접을 수 있는 요소는 닫힙니다. (전통적인 아코디언 동작과 유사 - 이것은 <code>card</code> 클래스에 따라 달라집니다). 이 속성은 접을 수 있는 타겟 영역에 설정 해야합니다.</td>
    </tr>
    <tr>
      <td>toggle</td>
      <td>boolean</td>
      <td>true</td>
      <td>호출시 접이식 요소를 토글합니다.</td>
    </tr>
  </tbody>
</table>

### 메서드 Methods

{% capture callout-include %}{% include callout-danger-async-methods.md %}{% endcapture %}
{{ callout-include | markdownify }}

#### `.collapse(options)`

콘텐츠를 접을 수 있는 요소로 활성화합니다. 선택적 옵션 `object`를 수락합니다.

{% highlight js %}
$('#myCollapsible').collapse({
  toggle: false
})
{% endhighlight %}

#### `.collapse('toggle')`

접을 수 있는 요소를 표시하거나 숨깁니다. 접을 수 있는 요소가 실제로 표시되거나 숨겨지기 전에 호출자에게 반환됩니다. **(즉, `shown.bs.collapse` 또는 `hidden.bs.collapse` 이벤트가 발생하기 전에)**

#### `.collapse('show')`

접을 수 있는 요소를 표시합니다. **접을 수있는 요소가 실제로 표시되기 전에 호출자에게 반환됩니다.** (즉, `shown.bs.collapse` 이벤트가 발생하기 전에)

#### `.collapse('hide')`

접을 수 있는 요소를 숨깁니다. **접을 수있는 요소가 실제로 숨겨지기 전에 호출자에게 반환됩니다.** (즉,`hidden.bs.collapse` 이벤트가 발생하기 전에)

### 이벤트 Events

부트스트랩의 컬랩스 클래스는 접이식 기능에 연결하기 위해 몇가지 이벤트를 제공합니다.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <th style="width: 150px;">이벤트 타입</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>show.bs.collapse</td>
      <td>이 이벤트는  <code>show</code> instance 메서드가 호출 될 때 즉시 발생됩니다.</td>
    </tr>
    <tr>
      <td>shown.bs.collapse</td>
      <td>이 이벤트는 collapse 요소가 사용자에게 표시될 때 발생됩니다 (CSS 전환이 완료 될 때까지 기다림).</td>
    </tr>
    <tr>
      <td>hide.bs.collapse</td>
      <td>이 이벤트는 <code>hide</code> 메서드가 호출되면 즉시 발생됩니다.</td>
    </tr>
    <tr>
      <td>hidden.bs.collapse</td>
      <td>이 이벤트는 collapse 요소가 사용자에게 숨겨진 후에 발생됩니다 (CSS 전환이 완료 될 때까지 기다림).</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#myCollapsible').on('hidden.bs.collapse', function () {
  // do something…
})
{% endhighlight %}
