---
layout: docs
title: 경로 Breadcrumb
description: CSS를 통해 자동으로 추가된 구분기호로 현재 페이지의 위치를 나타냅니다.
group: components
---



## 개요

구분 기호는 [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) 와 [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content)를 통해 CSS에 자동으로 추가됩니다.

{% example html %}

<nav aria-label="breadcrumb" role="navigation">
  <ol class="breadcrumb">
    <li class="breadcrumb-item active" aria-current="page">홈</li>
  </ol>
</nav>

<nav aria-label="breadcrumb" role="navigation">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">홈</a></li>
    <li class="breadcrumb-item active" aria-current="page">자료실</li>
  </ol>
</nav>

<nav aria-label="breadcrumb" role="navigation">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="#">홈</a></li>
    <li class="breadcrumb-item"><a href="#">자료실</a></li>
    <li class="breadcrumb-item active" aria-current="page">데이터</li>
  </ol>
</nav>
{% endexample %}

## 접근성

경로는 탐색기능을 제공하기 때문에 `<nav>`> 요소에 네비게이션 유형을 설명하기 위해 `aria-label="breadcrumb"` 와 같은 레이블을 추가하는 것이 좋습니다.  현재 페이지를 나타내기 위해 `aria-current="page"`를 마지막 항목에 적용 할 수 있습니다.

자세한 내용은 [경로 패턴에 대한 WAI-ARIA 제작방법](https://www.w3.org/TR/wai-aria-practices/#breadcrumb)을 참조하십시오.
