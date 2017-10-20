---
layout: docs
title: 그리드 시스템
description: 12개의 컬럼 시스템, 5개의 반응형 계층, Sass 변수 및 믹스인 및 수십 개의 미리 정의 된 클래스를 사용하여 강력한 mobile-first 플렉스박스 그리드로 모든 형태의 레이아웃을 만듭니다.
group: layout
toc: true
---

## 작동원리

부트스트랩의 그리드 시스템은 일련의 컨테이너, 행 및 열을 사용하여 내용을 정렬하고 구성합니다. 그것은 [플렉스 박스](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Using_CSS_flexible_boxes)로 제작되었으며 완전히 반응형 입니다. 다음은 그리드가 어떻게 함께 나타나는지에 대한 심층예제 입니다.

**플렉스 박스에 익숙하지 않은가요?**  등장배경,용어,가이드라인 및 스니핏을 알기 위해 [플렉스박스 가이드](https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-background)를 읽어보세요.


<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col-sm">
      세 칼럼 중 하나
    </div>
    <div class="col-sm">
      세 칼럼 중 하나
    </div>
    <div class="col-sm">
      세 칼럼 중 하나
    </div>
  </div>
</div>
{% endexample %}
</div>

위의 예는 사전 정의 된 그리드 클래스를 사용하여 small, medium, large 및 extra large 디바이스를 고려하여 세개의 동일폭(equal-width) 칼럼으로 작성 되었습니다. 이 칼럼들은 부모에 `.container`가 적용된 페이지의 가운데에 배치 됩니다.

이것을 변경하는 방법은 다음과 같습니다.

- 컨테이너는 사이트 콘텐츠를 중앙에 배치하게 합니다. 반응형 픽셀 너비를 위해서는 `.container`를,  모든 뷰포트 와 디바이스 크기에 꽉차는 `width: 100%` 너비를 위해서는  `.container-fluid` 를 사용하세요.
- 행(row)은 칼럼(column)을 감싸고 있습니다. 각 칼럼은 그들 사이의 공간을 제어하기 위해 수평 `padding` (gutter라고 부름)을 가지고 있습니다. 이 `padding`은 마이너스 마진이 적용된  행(row)의 양쪽 끝에서는 상쇄 됩니다. 이렇게 하면 칼럼에 있는 모든 콘텐츠가 왼쪽에서 수평방향으로 정렬됩니다.
- 그리드 레이아웃에서 컨텐츠는 칼럼 안에 배치되어야 하며 칼럼은 행(row)의 직계 자손이어야 합니다.
- flexbox 덕분에 지정된 `width`가 없는 그리드 칼럼은 자동으로 동일한 폭의 칼럼으로 배치됩니다. 예를 들어, `.col-sm`이 적용된 네개의 칼럼은 자동으로 small breakpoint에서 25% 폭이 됩니다. 자세한 예는 [auto-layout 칼럼](#auto-layout-columns) 섹션을 참조하십시오.
- 칼럼 클래스는 행(row)당 12개의 가능한 칼럼 중에서 사용하려는 칼럼의 수(number)를 나타냅니다. 따라서 동일한 폭의 3개의 칼럼이 필요하다면 `.col-4`를 사용할 수 있습니다.
- 칼럼의 `width`는 퍼센트(%)로 설정되므로 항상 부모요소를 기준으로 유동적으로 크기가 조정됩니다.
- 칼럼 사이에 여백(gutter)를 만들기 위해 가로 `padding`이 적용되어 있지만, `.row`에 `.no-gutters`를 적용하여 행(row)에서 `margin` 과 칼럼에서 `padding` 을 제거할 수 있습니다.
- 반응형 그리드를 만들기 위해 5개의 중단점(breakpoint)이 있습니다. 각각의 [반응형 중단점]({{ site.baseurl }}/docs/{{ site.docs_version }}/layout/overview/#responsive-breakpoints)에는 all breakpoints (extra small), small, medium, large, 그리고 extra large 가 있습니다.
- 그리드 중단점(breakpoint)은 최소 폭(minimum width)의 미디어 쿼리를 기반으로 합니다. 즉, **하나의 중단점은 상위에 있는 모든 항목에 적용됩니다** (예 : `.col-sm-4`는 small, medium, large, 그리고 extra large 디바이스에 적용되지만 첫번째 `xs` 중단점에는 적용되지 않음).
- 보다 의미있는(semantic) 마크업을 위해 사전 정의된 그리드 클래스 (`.col-4`와 같은) 또는 [Sass 믹스인](#sass-mixins)을 사용할 수 있습니다.

[Flex 컨테이너로 일부 HTML 요소를 사용할 수 없는 것](https://github.com/philipwalton/flexbugs#9-some-html-elements-cant-be-flex-containers)과 같은 flexbox 관련 제한 사항 과 [버그](https://github.com/philipwalton/flexbugs)를 알고 있어야 합니다.


## 그리드 옵션

부트스트랩은 대부분 크기를 정의 할 때 `em` 이나 `rem`을 사용하지만, `px`은 그리드 중단점(breakpoint)과 컨테이너의 폭(width)에 사용됩니다. 이유는 뷰포트 너비가 픽셀 단위이며 [폰트 사이즈](https://drafts.csswg.org/mediaqueries-3/#units)에 따라 변하지 않기 때문입니다.

부트스트랩 그리드 시스템이 여러 디바이스에서 어떻게 작동하는지 표에서 확인해 보세요.

<table class="table table-bordered table-striped table-responsive">
  <thead>
    <tr>
      <th></th>
      <th class="text-center">
        Extra small<br>
        <small>&lt;576px</small>
      </th>
      <th class="text-center">
        Small<br>
        <small>&ge;576px</small>
      </th>
      <th class="text-center">
        Medium<br>
        <small>&ge;768px</small>
      </th>
      <th class="text-center">
        Large<br>
        <small>&ge;992px</small>
      </th>
      <th class="text-center">
        Extra large<br>
        <small>&ge;1200px</small>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th class="text-nowrap" scope="row">컨테이너 최대폭</th>
      <td>None (auto)</td>
      <td>540px</td>
      <td>720px</td>
      <td>960px</td>
      <td>1140px</td>
    </tr>
    <tr>
      <th class="text-nowrap" scope="row">Class 접두사</th>
      <td><code>.col-</code></td>
      <td><code>.col-sm-</code></td>
      <td><code>.col-md-</code></td>
      <td><code>.col-lg-</code></td>
      <td><code>.col-xl-</code></td>
    </tr>
    <tr>
      <th class="text-nowrap" scope="row">칼럼 갯수</th>
      <td colspan="5">12</td>
    </tr>
    <tr>
      <th class="text-nowrap" scope="row">여백(Gutter) 폭</th>
      <td colspan="5">30px (각칼럼의 사이드는 15px)</td>
    </tr>
    <tr>
      <th class="text-nowrap" scope="row">Nestable</th>
      <td colspan="5">Yes</td>
    </tr>
    <tr>
      <th class="text-nowrap" scope="row">칼럼 순서지정</th>
      <td colspan="5">Yes</td>
    </tr>
  </tbody>
</table>

## Auto-layout 칼럼

`.col-sm-6` 과 같이 명시적으로 번호가 매겨진 클래스가 없으면  쉽게 칼럼폭 크기조절을 위해 브레이크 포인트 관련 칼럼 클래스를 활용하십시오.

### 동일 폭

예를 들어 `xs`에서`xl`까지 모든 디바이스와 뷰포트에 적용되는 두개의 그리드 레이아웃이 있습니다. 필요한 각 중단점에 대해 단위숫자 없이 클래스를 추가하면 모든 칼럼은 동일한 폭이 됩니다.

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col">
      1 of 2
    </div>
    <div class="col">
      2 of 2
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col">
      2 of 3
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
</div>
{% endexample %}
</div>

동일폭 칼럼은 여러 라인으로 나뉠 수 있지만, Safari 에서 `flex-basis` 또는 `border` 없이는 작동하지 않는 [Safari flexbox bug](https://github.com/philipwalton/flexbugs#11-min-and-max-size-declarations-are-ignored-when-wrapping-flex-items)가 있습니다. 예제는 `border`가 설정 되어있어 작동합니다. 당신도 `.col { border: 1px solid transparent; }` 또는 flex-basis을 칼럼 너비로 설정할 수 있습니다. (예 : `.col { flex: 1 0 50%; }`)

이 두가지 수정 사항은 [reduced test case outside Bootstrap](https://output.jsbin.com/micohor)에 문서화 되었습니다.

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col">Column</div>
    <div class="col">Column</div>
    <div class="w-100"></div>
    <div class="col">Column</div>
    <div class="col">Column</div>
  </div>
</div>
{% endexample %}
</div>

### 특정 칼럼 너비 셋팅

Auto-layout은 한 칼럼의 폭을 지정하면 다른 형제 칼럼의 폭은 자동으로 다시 조정 된다는 뜻입니다.
그리드 클래스, 믹스인(mixin) 또는 인라인으로 너비(width)를 지정할 수 있으며, 폭이 지정된 중앙 칼럼의 너비에 따라 다른 칼럼은 크기가 조정됩니다.(아래 그림 참조)

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col-6">
      2 of 3 (넓음)
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col-5">
      2 of 3 (넓음)
    </div>
    <div class="col">
      3 of 3
    </div>
  </div>
</div>
{% endexample %}
</div>

### 가변 폭 콘텐츠

`col-{breakpoint}-auto` 클래스를 사용하여 컨텐츠의 너비에 따라 칼럼 폭이 가변적으로 변경될 수 있도록 하세요.

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row justify-content-md-center">
    <div class="col col-lg-2">
      1 of 3
    </div>
    <div class="col-md-auto">
      가변 폭 콘텐츠
    </div>
    <div class="col col-lg-2">
      3 of 3
    </div>
  </div>
  <div class="row">
    <div class="col">
      1 of 3
    </div>
    <div class="col-md-auto">
      가변 폭 콘텐츠
    </div>
    <div class="col col-lg-2">
      3 of 3
    </div>
  </div>
</div>
{% endexample %}
</div>

### 동일 폭-멀티 라인

칼럼을 줄바꿈할 위치에 `.w-100`을 삽입하여 멀티 라인 동일폭 칼럼을 작성합니다. `.w-100`을 [반응형 디스플레이 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/)와 혼합하여 행을 구분하세요.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col">col</div>
  <div class="col">col</div>
  <div class="w-100"></div>
  <div class="col">col</div>
  <div class="col">col</div>
</div>
{% endexample %}
</div>

## 반응형 클래스

부트스트랩의 그리드에는 복잡한 반응형 레이아웃을 작성하기 위한 5개 계층의 클래스가 있습니다. extra small, small, medium, large 또는 extra large 디바이스에서 칼럼의 크기를 맞춤 설정할 수 있습니다.

### 전체 디바이스 포괄

가장 작은 디바이스 부터 가장 큰 디바이스 까지 동일한 그리드를 사용할 경우 `.col` 및 `.col-*` 클래스를 사용 하십시오. 특히 크기가 지정된 칼럼이 필요할 때는 번호가 매겨진 클래스를 지정 하십시오. 그렇지 않으면 주저하지 말고 `.col`을 사용 하십시오.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col">col</div>
  <div class="col">col</div>
  <div class="col">col</div>
  <div class="col">col</div>
</div>
<div class="row">
  <div class="col-8">col-8</div>
  <div class="col-4">col-4</div>
</div>
{% endexample %}
</div>

### 수평으로 쌓기

단일 계층의 `.col-sm-*` 클래스 세트를 사용하여 스마트폰(extra small)에서는 수직으로 쌓이게 하고, 데스크탑(medium)에서는 수평으로 쌓이는 기본 그리드 시스템을 만들 수 있습니다.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-sm-8">col-sm-8</div>
  <div class="col-sm-4">col-sm-4</div>
</div>
<div class="row">
  <div class="col-sm">col-sm</div>
  <div class="col-sm">col-sm</div>
  <div class="col-sm">col-sm</div>
</div>
{% endexample %}
</div>

### 클래스의 조합

반응형 그리드 계층별로 다르게 칼럼을 배치하기를 원한다면, 각 계층마다 다른 클래스의 조합을 사용하십시오. 아래의 예를 참조하면 모든것이 어떻게 작동하는지 더 잘 알 수 있습니다.

<div class="bd-example-row">
{% example html %}
<!-- 모바일에서는 전체너비와 절반너비의 칼럼으로 수직 배치합니다. -->
<div class="row">
  <div class="col-12 col-md-8">.col-12 .col-md-8</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- 모바일에서는 50%, 데스크탑에서는 33.3% 로 칼럼 폭이 변경됩니다. -->
<div class="row">
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>

<!-- 모바일 및 데스크톱에서 항상 칼럼폭이 50% 입니다. -->
<div class="row">
  <div class="col-6">.col-6</div>
  <div class="col-6">.col-6</div>
</div>
{% endexample %}
</div>

## 정렬

Flexbox 정렬 유틸리티를 사용하여 수직 및 수평으로 칼럼을 정렬 하십시오.

### 수직 정렬

<div class="bd-example-row bd-example-row-flex-cols">
{% example html %}
<div class="container">
  <div class="row align-items-start">
    <div class="col">
      세 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
  </div>
  <div class="row align-items-center">
    <div class="col">
      세개의 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
  </div>
  <div class="row align-items-end">
    <div class="col">
      세 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
    <div class="col">
      세 칼럼 중 하나
    </div>
  </div>
</div>
{% endexample %}
</div>

<div class="bd-example-row bd-example-row-flex-cols">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col align-self-start">
      세 칼럼 중 하나
    </div>
    <div class="col align-self-center">
      세 칼럼 중 하나
    </div>
    <div class="col align-self-end">
      세 칼럼 중 하나
    </div>
  </div>
</div>
{% endexample %}
</div>

### 수평 정렬

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row justify-content-start">
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
  </div>
  <div class="row justify-content-center">
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
  </div>
  <div class="row justify-content-end">
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
  </div>
  <div class="row justify-content-around">
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
  </div>
  <div class="row justify-content-between">
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
    <div class="col-4">
      두개의 칼럼중 하나
    </div>
  </div>
</div>
{% endexample %}
</div>

### 여백 없애기

칼럼 사이에 있는 여백(gutter)은 `.no-gutters`로 제거 할 수 있습니다. 이렇게하면 `.row` 에 적용된 마이너스 `margin`과 직계 하위 칼럼의 가로 `padding`이 제거됩니다.

Here's the source code for creating these styles. Note that column overrides are scoped to only the first children columns and are targeted via [attribute selector](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors). While this generates a more specific selector, column padding can still be further customized with [spacing utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/).

다음은 이러한 스타일을 만드는데 필요한 소스코드 입니다. 칼럼의 재정의(override)는 첫번째 하위 칼럼에만 적용되고 [속성 선택자](https://developer.mozilla.org/en-US/docs/Web/CSS/Attribute_selectors)를 통해 대상으로 지정됩니다. 이 과정에서 더 구체적인 선택자가 적용되지만, 칼럼의 padding은 여전히 [spacing 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/)를 사용하여 사용자 지정 할 수 있습니다.


**edge-to-edge 디자인이 필요하십니까?** 부모요소의 `.container` 또는 `.container-fluid` 를 삭제하십시오.

{% highlight sass %}
.no-gutters {
  margin-right: 0;
  margin-left: 0;

  > .col,
  > [class*="col-"] {
    padding-right: 0;
    padding-left: 0;
  }
}
{% endhighlight %}

실제로 이렇게 보입니다. 다른 모든 그리드 클래스 (칼럼 너비, 반응형 계층, 재정렬 등)는 계속 사용할 수 있습니다.

<div class="bd-example-row">
{% example html %}
<div class="row no-gutters">
  <div class="col-12 col-sm-6 col-md-8">.col-12 .col-sm-6 .col-md-8</div>
  <div class="col-6 col-md-4">.col-6 .col-md-4</div>
</div>
{% endexample %}
</div>

### 칼럼 묶기

하나의 행(row)에 12개 이상의 칼럼 유닛이 있으면, 초과된 유닛이 포함된 칼럼은 새 행(row)으로 묶입니다.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-9">.col-9</div>
  <div class="col-4">.col-4<br>9 + 4 = 13 &gt; 12 이므로, 이 div는 하나의 연속된 유닛으로서 새로운 라인에 래핑 됩니다.</div>
  <div class="col-6">.col-6<br>후속 칼럼은 계속해서 새 라인을 따라 이어집니다.</div>
</div>
{% endexample %}
</div>

### 칼럼 줄바꿈

flexbox에서 새로운 라인으로 컬럼을 줄바꿈하는 것은 약간의 해킹이 필요합니다 : 컬럼을 새로운 라인에 래핑하고자 할 때마다 `width: 100%` 요소를 추가하십시오. 일반적으로 이것은 여러개의 `.row`가 수반 됩니다.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
  <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>

  <!-- 다음 칼럼을 강제로 새 라인으로 나눕니다. -->
  <div class="w-100"></div>

  <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
  <div class="col-6 col-sm-3">.col-6 .col-sm-3</div>
</div>
{% endexample %}
</div>

[반응형 디스플레이 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/)를 사용하여 특정 중단점에서 이러한 줄바꿈을 적용 할 수도 있습니다.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
  <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>

  <!-- 다음 컬럼을 강제로 md 중단점에서 새로운 라인으로 나눕니다. -->
  <div class="w-100 d-none d-md-block"></div>

  <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
  <div class="col-6 col-sm-4">.col-6 .col-sm-4</div>
</div>
{% endexample %}
</div>

## 컬럼 순서지정

### 순서지정 클래스

`.order-` 클래스를 사용하여 콘텐츠의 **시각적 순서** 를 제어하십시오. 이 클래스는 반응형이어서, 중단점(예 : `.order-1.order-md-2`)별로 `order`를 설정할 수 있습니다. 5단계 그리드 계층에서 대해 `1` 에서 `12` 까지의 순서지정을 지원합니다.

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col">
      첫번재, 순서 미지정됨
    </div>
    <div class="col order-12">
      두번째, 하지만 마지막
    </div>
    <div class="col order-1">
      세번째, 하지만 첫번째
    </div>
  </div>
</div>
{% endexample %}
</div>

`order: -1`를 적용하여 요소의 순서를 빠르게 변경하는 `.order-first` 라는 반응형 클래스가 있습니다.  이 클래스는 필요에 따라 번호가 매겨진 `.order-*` 클래스와 섞일 수도 있습니다.

<div class="bd-example-row">
{% example html %}
<div class="container">
  <div class="row">
    <div class="col">
      첫번째, 순서 미지정
    </div>
    <div class="col">
      두번째, 순서 미지정
    </div>
    <div class="col order-first">
      세번째, 그러나 첫번째
    </div>
  </div>
</div>
{% endexample %}
</div>

### 컬럼 간격 띄우기

그리드 칼럼의 간격을 띄우는 방법에는 두가지가 있습니다: `.offset-` 그리드 클래스 와  [margin 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/) 를 사용하는 것 입니다. 그리드 클래스는 칼럼과 일치하도록 크기가 조정되는 반면, margin을 적용하는 방법은 오프셋의 폭이 가변적인 레이아웃에 더 유용합니다.

#### 오프셋 클래스

`.offset-md-*` 클래스를 사용하여 칼럼을 오른쪽으로 이동 하세요. 이러한 클래스는 칼럼의 왼쪽 여백을 `*` 만큼 늘립니다. 예를 들어, `.offset-md-4`는 4개 칼럼 유닛 만큼 `.col-md-4`를 이동 시킵니다..

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-md-4">.col-md-4</div>
  <div class="col-md-4 offset-md-4">.col-md-4 .offset-md-4</div>
</div>
<div class="row">
  <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
  <div class="col-md-3 offset-md-3">.col-md-3 .offset-md-3</div>
</div>
<div class="row">
  <div class="col-md-6 offset-md-3">.col-md-6 .offset-md-3</div>
</div>
{% endexample %}
</div>

게다가 반응형 중단점에서 칼럼을 초기화 하기 위해 오프셋을 재설정해야 할 수도 있습니다. [그리드 예제]({{ site.baseurl }}/docs/{{ site.docs_version }}/examples/grid/)에서 실제로 확인해 보세요.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-sm-5 col-md-6">.col-sm-5 .col-md-6</div>
  <div class="col-sm-5 offset-sm-2 col-md-6 offset-md-0">.col-sm-5 .offset-sm-2 .col-md-6 .offset-md-0</div>
</div>

<div class="row">
  <div class="col-sm-6 col-md-5 col-lg-6">.col.col-sm-6.col-md-5.col-lg-6</div>
  <div class="col-sm-6 col-md-5 offset-md-2 col-lg-6 offset-lg-0">.col-sm-6 .col-md-5 .offset-md-2 .col-lg-6 .offset-lg-0</div>
</div>
{% endexample %}
</div>

#### Margin 유틸리티

부트스트랩 v4의 flexbox를 사용하면서 `.mr-auto` 같은 margin 유틸리티를 사용하여 형제 칼럼을 서로 멀리 떨어 뜨릴 수 있습니다.

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-md-4">.col-md-4</div>
  <div class="col-md-4 ml-auto">.col-md-4 .ml-auto</div>
</div>
<div class="row">
  <div class="col-md-3 ml-md-auto">.col-md-3 .ml-md-auto</div>
  <div class="col-md-3 ml-md-auto">.col-md-3 .ml-md-auto</div>
</div>
<div class="row">
  <div class="col-auto mr-auto">.col-auto .mr-auto</div>
  <div class="col-auto">.col-auto</div>
</div>
{% endexample %}
</div>

## 컬럼 중첩

콘텐츠를 기본 그리드로 중첩(nest) 시키려면, 기존 `.col-sm-*` 칼럼 안에 새로운 .`.row` 및 `.col-sm-*` 칼럼 셋을 추가하세요. 중첩된 행(row)에는 최대 12개 이하의 칼럼이 포함 되어야 합니다 (12개 칼럼을 모두 사용할 필요는 없음).

<div class="bd-example-row">
{% example html %}
<div class="row">
  <div class="col-sm-9">
    레벨 1: .col-sm-9
    <div class="row">
      <div class="col-8 col-sm-6">
        레벨 2: .col-8 .col-sm-6
      </div>
      <div class="col-4 col-sm-6">
        레벨 2: .col-4 .col-sm-6
      </div>
    </div>
  </div>
</div>
{% endexample %}
</div>

## Sass 믹스인

부트스트랩의 Sass 소스파일을 사용할 때, Sass 변수와 믹스인을 사용하여 사용자 맞춤, 시멘틱 그리고 반응형 페이지 레이아웃을 생성 할 수 있습니다. 미리 정의된 그리드 클래스는 빠르게 반응형 레이아웃 제작을 위한 바로 사용할 수 있는 클래스 모음을 제공하기 위해 이러한 동일한 변수와 믹스 인을 사용합니다.


### 변수

변수 및 맵에서는 칼럼의 수, 간격(gutter) 폭 및 칼럼이 플로팅 될 미디어 쿼리 포인트를 결정합니다. 변수는 위에서 설명한 대로 미리 정의된 그리드 클래스를 생성하고 또한, 아래에 나열된 커스텀 믹스인을 생성하기 위해 사용합니다.

{% highlight scss %}
$grid-columns:      12;
$grid-gutter-width: 30px;

$grid-breakpoints: (
  // Extra small screen / phone
  xs: 0,
  // Small screen / phone
  sm: 576px,
  // Medium screen / tablet
  md: 768px,
  // Large screen / desktop
  lg: 992px,
  // Extra large screen / wide desktop
  xl: 1200px
);

$container-max-widths: (
  sm: 540px,
  md: 720px,
  lg: 960px,
  xl: 1140px
);
{% endhighlight %}

### 믹스인

믹스인(Mixin)은 그리드 변수와 함께 사용되어 개별 그리드 칼럼에 대한 시멘틱 CSS를 생성합니다.

{% highlight scss %}
// 일련의 칼럼들을 감싸기 위한 wrapper 생성
@include make-row();

// grid-ready 요소를 만듭니다.(width 제외)  
@include make-col-ready();
@include make-col($size, $columns: $grid-columns);

// 오프셋을 사용하거나 정렬 순서를 변경하여 멋지게 표현하세요.
@include make-col-offset($size, $columns: $grid-columns);
{% endhighlight %}

### 사용 예

변수를 사용자 맞춤 값으로 수정하거나 기본값을 사용하여 믹스인을 사용할 수 있습니다. 다음은 기본 설정을 사용하여 간격이 있는 두개의 칼럼을 가진 레이아웃을 만드는 예입니다.

{% highlight scss %}
.example-container {
  width: 800px;
  @include make-container();
}

.example-row {
  @include make-row();
}

.example-content-main {
  @include make-col-ready();

  @include media-breakpoint-up(sm) {
    @include make-col(6);
  }
  @include media-breakpoint-up(lg) {
    @include make-col(8);
  }
}

.example-content-secondary {
  @include make-col-ready();

  @include media-breakpoint-up(sm) {
    @include make-col(6);
  }
  @include media-breakpoint-up(lg) {
    @include make-col(4);
  }
}
{% endhighlight %}

{% example html %}
<div class="example-container">
  <div class="example-row">
    <div class="example-content-main">메인 컨텐츠</div>
    <div class="example-content-secondary">보조 컨텐츠</div>
  </div>
</div>
{% endexample %}

## 그리드 맞춤설정

내장된 그리드 Sass 변수와 맵을 사용하여 사전 정의 된 그리드 클래스를 완벽하게 사용자 맞춤(Customizing) 할 수 있습니다. 계층 수, 미디어 쿼리 치수 및 컨테이너 너비를 변경 한 다음 다시 컴파일 하십시오.

### 칼럼과 여백

그리드 칼럼 수는 Sass 변수를 통해 수정할 수 있습니다. `$grid-columns` 는 각 개별 칼럼의 너비(퍼센트)를 생성하는데 사용되는 반면 `$grid-gutter-width` 는  칼럼의 여백(gutter)에 대해 `padding-left`와 `padding-right`에 균등하게 나뉘어 적용되어 중단점 별 너비를 제공 합니다.

{% highlight scss %}
$grid-columns: 12 !default;
$grid-gutter-width: 30px !default;
{% endhighlight %}

### 그리드 계층

그리드 계층 수를 사용자 맞춤 할 수도 있습니다. 네개의 그리드 계층만 원한다면 `$grid-breakpoints` 와 `$container-max-widths`를 다음과 같이 갱신 할 것입니다 :

{% highlight scss %}
$grid-breakpoints: (
  xs: 0,
  sm: 480px,
  md: 768px,
  lg: 1024px
);

$container-max-widths: (
  sm: 420px,
  md: 720px,
  lg: 960px
);
{% endhighlight %}

Sass 변수나 맵을 변경할 때, 변경사항을 저장하고 다시 컴파일 해야합니다. 이렇게 하면 수정된 칼럼 너비, 간격 띄우기 및 정렬에 맞게 새로운 클래스 셋이 산출 됩니다. 반응형 가시성 유틸리티는 수정된 중단점을 사용하도록 업데이트 됩니다. 그리드 값을 `px` (`rem`, `em` 또는 `%` 가 아님)로 설정 해야합니다.
