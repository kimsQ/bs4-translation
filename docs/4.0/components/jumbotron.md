---
layout: docs
title: 점보트론
description: hero 유닛 스타일 콘텐츠를 보여주는 가볍고 유연한 컴포넌트.
group: components
---

가볍고 유연한 컴포넌트로서 선택적으로 전체 뷰포트를 확장하여 주요 마케팅 메시지를 사이트에 표시 할 수 있습니다.

{% example html %}
<div class="jumbotron">
  <h1 class="display-3">안녕하세요!</h1>
  <p class="lead">이것은 특색있는 내용이나 특별히 관심을 불러 일으킬 수있는 간단한 정보에 적용하는 점보트론 스타일의 컴포넌트입니다.</p>
  <hr class="my-4">
  <p>It uses utility classes for typography and spacing to space content out within the larger container.</p>
  <p class="lead">
    <a class="btn btn-primary btn-lg" href="#" role="button">더 알아보기</a>
  </p>
</div>
{% endexample %}

To make the jumbotron full width, and without rounded corners, add the `.jumbotron-fluid` modifier class and add a `.container` or `.container-fluid` within.

{% example html %}
<div class="jumbotron jumbotron-fluid">
  <div class="container">
    <h1 class="display-3">Fluid jumbotron</h1>
    <p class="lead">This is a modified jumbotron that occupies the entire horizontal space of its parent.</p>
  </div>
</div>
{% endexample %}
