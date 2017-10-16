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

Since breadcrumbs provide a navigation, it's a good idea to add a meaningful label such as `aria-label="breadcrumb"` to describe the type of navigation provided in the `<nav>` element, as well as applying an `aria-current="page"` to the last item of the set to indicate that it represents the current page.

For more information, see the [WAI-ARIA Authoring Practices for the breadcrumb pattern](https://www.w3.org/TR/wai-aria-practices/#breadcrumb).
