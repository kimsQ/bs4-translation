---
layout: docs
title: 개요
description: 컨테이너 구성, 강력한 그리드 시스템, 유연한 미디어 객체 및 반응형 유틸리티 클래스를 포함하여 부트스트랩 프로젝트를 구성하는 컴포넌트 및 옵션.
group: layout
redirect_from: "/docs/4.0/layout/"
toc: true
---


## 컨테이너

컨테이너는 부트스트랩에서 가장 기본적인 레이아웃 요소이며 **기본 그리드 시스템** 을 사용하려면 필요합니다. 반응형, 고정폭 컨테이너(각 중단점에서 최대 넓이 변경), 유동폭 컨테이너(항상 '100% 넓이') 중에서 선택할 수 있습니다.

컨테이너는 중첩될 수 있지만 대부분의 레이아웃에는 중첩된 컨테이너가 필요하지 않습니다.

<div class="bd-example">
  <div class="bd-example-container">
    <div class="bd-example-container-header"></div>
    <div class="bd-example-container-sidebar"></div>
    <div class="bd-example-container-body"></div>
  </div>
</div>

{% highlight html %}
<div class="container">
  <!-- 내용은 여기에 -->
</div>
{% endhighlight %}


뷰포트(viewport)의 전체를 채우는 전체 폭 컨테이너가 필요한 경우 `.container-fluid` 를 사용하세요.

<div class="bd-example">
  <div class="bd-example-container bd-example-container-fluid">
    <div class="bd-example-container-header"></div>
    <div class="bd-example-container-sidebar"></div>
    <div class="bd-example-container-body"></div>
  </div>
</div>

{% highlight html %}
<div class="container-fluid">
  ...
</div>
{% endhighlight %}


## 반응형 브레이크 포인트

부트스트랩은 모바일(우선)용으로 개발되었기 때문에 우리는 몇가지 [미디어 쿼리](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)를 사용하여 레이아웃과 인터페이스를 위한 현명한 브레이크 포인트를 만듭니다. 이러한 브레이크 포인트는 뷰포트의 최소너비를 기반으로 하며 뷰포트가 변경될때 요소의 크기를 조정할 수 있습니다.

부트스트랩은 주로 레이아웃, 그리드 시스템 및 컴포넌트에 대해 Sass 파일에서 다음과 같은 미디어 쿼리 범위(breakpoints)를 사용합니다.

{% highlight scss %}
// Extra small devices (portrait phones, 576px 미만)
// 부트스트랩의 기본값이므로 미디어 쿼리가 없습니다.

// Small devices (landscape phones, 576px 이상)
@media (min-width: 576px) { ... }

// Medium devices (tablets, 768px 이상)
@media (min-width: 768px) { ... }

// Large devices (desktops, 992px 이상)
@media (min-width: 992px) { ... }

// Extra large devices (large desktops, 1200px 이상)
@media (min-width: 1200px) { ... }
{% endhighlight %}

Sass에서 CSS를 작성 했으므로 Sass mixins를 통해 모든 미디어쿼리를 사용할 수 있습니다.

{% highlight scss %}
@include media-breakpoint-up(xs) { ... }
@include media-breakpoint-up(sm) { ... }
@include media-breakpoint-up(md) { ... }
@include media-breakpoint-up(lg) { ... }
@include media-breakpoint-up(xl) { ... }

// 사용예:
@include media-breakpoint-up(sm) {
  .some-class {
    display: block;
  }
}
{% endhighlight %}

때때로 다른 방향으로 진행되는 미디어 쿼리를 사용합니다 (주어진 화면 크기 또는 *작은 크기*):

{% highlight scss %}
// Extra small devices (portrait phones, 576px 미만)
@media (max-width: 575px) { ... }

// Small devices (landscape phones, 768px 미만)
@media (max-width: 767px) { ... }

// Medium devices (tablets, 992px 미만)
@media (max-width: 991px) { ... }

// Large devices (desktops, 1200px 미만)
@media (max-width: 1199px) { ... }

// Extra large devices (large desktops)
// extra-large 브레이크 포인트에는 너비의 상한이 없으므로 미디어쿼리를 적용하지 않습니다.

{% endhighlight %}

다시 말해, 이러한 미디어 쿼리는 Sass 믹스인(mixins)을 통해서도 사용할 수 있습니다 :

{% highlight scss %}
@include media-breakpoint-down(xs) { ... }
@include media-breakpoint-down(sm) { ... }
@include media-breakpoint-down(md) { ... }
@include media-breakpoint-down(lg) { ... }
{% endhighlight %}

최소 및 최대 브레이크 포인트의 너비를 사용하여 화면 크기를 단일 세그먼트로 지정하는 미디어 쿼리와 믹스인(mixins)도 있습니다.

{% highlight scss %}
// Extra small devices (portrait phones, 576px 미만)
@media (max-width: 575px) { ... }

// Small devices (landscape phones, 576px 이상)
@media (min-width: 576px) and (max-width: 767px) { ... }

// Medium devices (tablets, 768px 이상)
@media (min-width: 768px) and (max-width: 991px) { ... }

// Large devices (desktops, 992px 이상)
@media (min-width: 992px) and (max-width: 1199px) { ... }

// Extra large devices (large desktops, 1200px 이상)
@media (min-width: 1200px) { ... }
{% endhighlight %}


이 미디어 쿼리는 Sass 믹스인(mixins)을 통해서도 얻을 수 있습니다.

{% highlight scss %}
@include media-breakpoint-only(xs) { ... }
@include media-breakpoint-only(sm) { ... }
@include media-breakpoint-only(md) { ... }
@include media-breakpoint-only(lg) { ... }
@include media-breakpoint-only(xl) { ... }
{% endhighlight %}

마찬가지로 미디어 쿼리는 여러 브레이크 포인트 너비에 걸쳐 적용할수 있습니다.

{% highlight scss %}
// 사용예
// medium devices부터 extra large devices까지 스타일 적용
@media (min-width: 768px) and (max-width: 1199px) { ... }
{% endhighlight %}

동일한 화면 크기 범위를 타겟팅하는 Sass 믹스인은 다음과 같습니다.

{% highlight scss %}
@include media-breakpoint-between(md, xl) { ... }
{% endhighlight %}

## Z-index

여러 부트스트랩 컴포넌트는 `z-index`를 사용합니다. 이 CSS 속성은 컨텐츠를 정렬하는 또 다른 축을 제공하여 레이아웃을 컨트롤 하는데 도움을 줍니다.  부트스트랩의 기본 z-index 스케일은 네이게이션, 툴팁 및 팝오버, 모달 등을 적절하게 구성하도록 설계 되었습니다.

우리는 이 설정값의 커스터마이징을 권장하지 않습니다. 하나를 변경 할 경우, 모두 변경해야 하기 때문입니다.

```scss
$zindex-dropdown:          1000 !default;
$zindex-fixed:             1030 !default;
$zindex-sticky:            1030 !default;
$zindex-modal-backdrop:    1040 !default;
$zindex-modal:             1050 !default;
$zindex-popover:           1060 !default;
$zindex-tooltip:           1070 !default;
```

배경요소(백드롭)는 낮은 `z-index`를 적용하는 경향이 있는 반면, 네비게이션 및 팝오버는 높은 `z-index`를 사용하여 주변 콘텐츠에 상위에 배치(overlay) 합니다.
