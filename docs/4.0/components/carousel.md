---
layout: docs
title: 캐러셀 Carousel
description: 회전목마와 같이 순환하는 슬라이드 쇼(이미지 또는 텍스트 슬라이드)를 구성하는 컴포넌트.
group: components
toc: true
---



## 작동원리

캐러셀은 CSS 3D 트랜스폼과 약간의 자바스크립트로 제작된 시리즈 콘텐츠를 순환하는 슬라이드 쇼 입니다. 일련의 이미지, 텍스트 또는 커스텀 마크업과 함께 작동합니다. 또한 이전/다음 컨트롤 및 인디케이터를 포함합니다.

[Page Visibility API](https://www.w3.org/TR/page-visibility/)가 지원되는 브라우저에서 브라우저 탭이 비활성 상태이거나 브라우저 창이 최소화 된 경우와 같이 웹 페이지가 사용자에게 표시되지 않으면 슬라이드가 진행되지 않습니다.

중첩된 캐러셀은 지원되지 않으며 캐러셀은 일반적으로 웹접근성 표준을 준수하지 않습니다.

마지막으로 소스에서 JS를 빌드하는 경우 [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util)가 필요합니다.

## 예제

캐러셀은 자동으로 슬라이드 크기를 표준화하지 않습니다. 따라서 콘텐츠의 크기를 적절하게 조정하려면 추가 유틸리티 또는 사용자 정의 스타일을 사용해야 할 수도 있습니다. 캐러셀은 이전/다음 컨트롤 및 인디케이터를 지원하지만 명확하게 요구되지는 않습니다. 원하는대로 추가하고 사용자 정의 하십시오.

선택적 컨트롤을 위해 `.carousel`에 고유ID를 설정 해야합니다. 특히 한 페이지에서 여러개의 캐러셀를 사용하는 경우 특히 그렇습니다.

### 슬라이드만 있는 경우

다음은 슬라이드만 있는 캐러셀 입니다. 브라우저 기본 이미지 정렬을 방지하기 위해 캐러셀 이미지에 `.d-block` 및 `.img-fluid`가 있는지 확인하십시오.


{% example html %}
<div id="carouselExampleSlidesOnly" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=첫번째 슬라이드" alt="첫번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=두번째 슬라이드" alt="두번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=세번째 슬라이드" alt="세번째 슬라이드">
    </div>
  </div>
</div>
{% endexample %}

### 컨트롤을 사용하는 경우

이전 및 다음 컨트롤을 추가하세요 :

{% example html %}
<div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=첫번째 슬라이드" alt="첫번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=두번째 슬라이드" alt="두번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=세번째 슬라이드" alt="세번째 슬라이드">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">이전</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">다음</span>
  </a>
</div>
{% endexample %}

### 인디케이터를 사용하는 경우

컨트롤과 함께 인디케이터를 캐러셀에 추가 할 수도 있습니다.

{% example html %}
<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=첫번째 슬라이드" alt="첫번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=두번째 슬라이드" alt="두번째 슬라이드">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=세번째 슬라이드" alt="세번째 슬라이드">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">이전</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">다음</span>
  </a>
</div>
{% endexample %}

{% callout warning %}
#### Initial active element required

The `.active` class needs to be added to one of the slides. Otherwise, the carousel will not be visible.
{% endcallout %}

### 캡션을 사용하는 경우

`.carousel-item` 내에 `.carousel-caption` 요소를 사용하여 슬라이드에 캡션을 쉽게 추가 할 수 있습니다. 아래 그림과 같이 선택적으로 [디스플레이 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/)를 사용하여 작은 뷰포트에 쉽게 숨길 수 있습니다. 처음에는 `.d-none`으로 숨기고 `.d-md-block` 으로  중간 크기의 디바이스에서 다시 가져옵니다.

<div class="bd-example">
  <div id="carouselExampleCaptions" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleCaptions" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleCaptions" data-slide-to="1"></li>
      <li data-target="#carouselExampleCaptions" data-slide-to="2"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=777&fg=555&text=첫번째 슬라이드" alt="첫번째 슬라이드">
        <div class="carousel-caption d-none d-md-block">
          <h3>첫번째 슬라이드 라벨</h3>
          <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=666&fg=444&text=두번째 슬라이드" alt="두번째 슬라이드">
        <div class="carousel-caption d-none d-md-block">
          <h3>두번째 슬라이드 라벨</h3>
          <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세.</p>
        </div>
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" data-src="holder.js/800x400?auto=yes&bg=555&fg=333&text=세번째 슬라이드" alt="세번째 슬라이드">
        <div class="carousel-caption d-none d-md-block">
          <h3>세번째 슬라이드 라벨</h3>
          <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리 나라만세.</p>
        </div>
      </div>
    </div>
    <a class="carousel-control-prev" href="#carouselExampleCaptions" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">이전</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleCaptions" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">다음</span>
    </a>
  </div>
</div>

{% highlight html %}
<div class="carousel-item">
  <img src="..." alt="...">
  <div class="carousel-caption d-none d-md-block">
    <h3>...</h3>
    <p>...</p>
  </div>
</div>
{% endhighlight %}

## 사용법

### data 속성 방식

Use data attributes to easily control the position of the carousel. `data-slide` accepts the keywords `prev` or `next`, which alters the slide position relative to its current position. Alternatively, use `data-slide-to` to pass a raw slide index to the carousel `data-slide-to="2"`, which shifts the slide position to a particular index beginning with `0`.

데이터 속성을 사용하여 캐러셀의 위치를 쉽게 제어 할 수 있습니다. `data-slide` 는 `prev` 또는 `next` 키워드를 사용하여 현재 위치를 기준으로 슬라이드 위치를 변경합니다. 또는 `data-slide-to`를 사용하여 슬라이드 포인터를 `0`으로 시작하는 특정 인덱스로 이동하는 슬라이드 포인터 `data-slide-to="2"` 에 원시 슬라이드 인덱스를 전달합니다.

The `data-ride="carousel"` attribute is used to mark a carousel as animating starting at page load. **It cannot be used in combination with (redundant and unnecessary) explicit JavaScript initialization of the same carousel.**

`data-ride="carousel"` 속성은 캐러셀 페이지 로드시 애니메이션으로 표시하는데 사용됩니다. 동일한 캐러셀을 JavaScript 초기화 (중복 및 불필요한)방식과 함께 사용할 수 없습니다.

### JavaScript 방식

다음을 사용하여 수동으로 케러셀을 호출합니다.

{% highlight js %}
$('.carousel').carousel()
{% endhighlight %}

### 옵션

옵션은 data 속성 또는 JavaScript를 통해 전달 될 수 있습니다. data 속성의 경우  `data-interval=""` 처럼 `data-`에 옵션명을 추가하십시오.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <th style="width: 100px;">옵션명</th>
      <th style="width: 50px;">유형</th>
      <th style="width: 50px;">기본</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>interval</td>
      <td>number</td>
      <td>5000</td>
      <td>아이템 자동 순환 지연시간 입니다. false 인 경우, 캐러셀은 자동으로 순환하지 않습니다.</td>
    </tr>
    <tr>
      <td>keyboard</td>
      <td>boolean</td>
      <td>true</td>
      <td>캐러셀이 키보드 이벤트에 반응해야 하는지 여부.</td>
    </tr>
    <tr>
      <td>pause</td>
      <td>string | boolean</td>
      <td>"hover"</td>
      <td><p><code>"hover"</code>로 설정하면 <code>mouseenter</code>에서 캐러셀의 순환을 일시 중지하고 <code>mouseleave</code>에서 캐러셀을 다시 시작합니다. <code>false</code>로 설정하면 캐러셀 위에 마우스를 올리면(hover) 일시 중지되지 않습니다.</p>
      <p>터치 지원 디바이스에서 <code>"hover"</code>로 설정하면 <code>touchend</code>(사용자가 캐러셀과 상호 작용을 완료하면)에서 두번의 인터벌 동안 순환이 일시 중지됩니다. 이것은 위의 마우스 동작에 추가 된 것입니다.</p>
      </td>
    </tr>
    <tr>
      <td>ride</td>
      <td>string</td>
      <td>false</td>
      <td>사용자가 첫번째 아이템을 수동으로 순환시킨 후 캐러셀을 자동 재생합니다. "carousel" 인 경우 로드시 캐러셀을 자동 재생 합니다.</td>
    </tr>
    <tr>
      <td>wrap</td>
      <td>boolean</td>
      <td>true</td>
      <td>캐러셀이 지속적으로 순환 해야하는지 아니면 단단하게 정지를 해야하는지.</td>
    </tr>
  </tbody>
</table>

### 메소드 Methods

{% capture callout-include %}{% include callout-danger-async-methods.md %}{% endcapture %}
{{ callout-include | markdownify }}

#### `.carousel(options)`

선택적 옵션 `object`를 사용하여 캐러셀을 초기화하고 아이템을 순환 시킵니다.

{% highlight js %}
$('.carousel').carousel({
  interval: 2000
})
{% endhighlight %}

#### `.carousel('cycle')`

왼쪽에서 오른쪽으로 캐러셀 아이템을 순환 시킵니다.

#### `.carousel('pause')`

아이템이 순환하는 것을 중지합니다.

#### `.carousel(number)`

캐러셀을 특정 프레임 (배열과 비슷한 0 기반)으로 이동 시킵니다. 대상 아이템이 표시되기 전에 (즉, `slid.bs.carousel` 이벤트가 발생하기 전에) 호출자에게 반환됩니다.

#### `.carousel('prev')`

이전 항목으로 이동합니다. 이전 항목이 표시되기 전에 (즉, `slid.bs.carousel` 이벤트가 발생하기 전에) 호출자에게 반환됩니다.

#### `.carousel('next')`

다음 항목으로 이동합니다. 다음 항목이 표시되기 전에 (즉, `slid.bs.carousel` 이벤트가 발생하기 전에) 호출자에게 반환됩니다.

### 이벤트

부트스트랩의 캐러셀 클래스는 캐러셀 기능에 연결하기 위한 두가지 이벤트를 노출합니다. 두 이벤트 모두 다음과 같은 추가 속성을 가집니다.

- `direction`: 캐러셀이 슬라이드 되는 방향 ( `"left"` 또는 `"right"`).
- `relatedTarget`: 활성화된(active) 아이템으로 제자리에 들어간 DOM 요소입니다. The DOM element that is being slid into place as the active item.
- `from`: 현재 아이템의 색인(index)
- `to`: 다음 아이템의 색인(index)

모든 이벤트는 캐러셀 자체에서 발생(fired) 됩니다. (즉, `<div class="carousel">` 에서)

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <th style="width: 150px;">이벤트</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>slide.bs.carousel</td>
      <td>이 이벤트는 슬라이드 인스턴스 메서드가 호출 될 때 즉시 발생합니다.</td>
    </tr>
    <tr>
      <td>slid.bs.carousel</td>
      <td>이 이벤트는 회전식 슬라이드 전환(transition)이 완료되면 시작됩니다.</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
$('#myCarousel').on('slide.bs.carousel', function () {
  // do something…
})
{% endhighlight %}
