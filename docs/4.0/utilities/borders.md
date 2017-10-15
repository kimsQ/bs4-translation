---
layout: docs
title: 테두리 Borders
description: 테두리 유틸리티를 사용하여 요소의 테두리 및 테두리 반경의 스타일을 빠르게 지정합니다. 이미지, 버튼 또는 기타 요소에 적합합니다.
group: utilities
redirect_from: "/docs/4.0/utilities/"
toc: true
---



## 테두리

모든 테두리 또는 일부 테두리를 제거하려면 요소에 아래의 클래스를 추가 하십시오.

<div class="bd-example-border-utils">
{% example html %}
<span class="border"></span>
<span class="border-0"></span>
<span class="border-top-0"></span>
<span class="border-right-0"></span>
<span class="border-bottom-0"></span>
<span class="border-left-0"></span>
{% endexample %}
</div>

## 테두리 칼라

테마 색상을 기반으로한 유틸리티를 사용하여 테두리 색상을 변경하십시오.

<div class="bd-example-border-utils">
{% example html %}
{% for color in site.data.theme-colors %}
<span class="border border-{{ color.name }}"></span>{% endfor %}
<span class="border border-white"></span>
{% endexample %}
</div>

## 둥근 테두리 처리

요소에 클래스를 추가하여 모서리를 쉽게 둥글게 만듭니다.

<div class="bd-example bd-example-images">
  <img data-src="holder.js/75x75" class="rounded" alt="Example rounded image">
  <img data-src="holder.js/75x75" class="rounded-top" alt="Example top rounded image">
  <img data-src="holder.js/75x75" class="rounded-right" alt="Example right rounded image">
  <img data-src="holder.js/75x75" class="rounded-bottom" alt="Example bottom rounded image">
  <img data-src="holder.js/75x75" class="rounded-left" alt="Example left rounded image">
  <img data-src="holder.js/75x75" class="rounded-circle" alt="Completely round image">
  <img data-src="holder.js/75x75" class="rounded-0" alt="Example non-rounded image (overrides rounding applied elsewhere)">
</div>

{% highlight html %}
<img src="..." alt="..." class="rounded">
<img src="..." alt="..." class="rounded-top">
<img src="..." alt="..." class="rounded-right">
<img src="..." alt="..." class="rounded-bottom">
<img src="..." alt="..." class="rounded-left">
<img src="..." alt="..." class="rounded-circle">
<img src="..." alt="..." class="rounded-0">
{% endhighlight %}
