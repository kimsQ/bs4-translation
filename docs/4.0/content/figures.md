---
layout: docs
title: 피규어 Figures
description: 그림 구성요소를 가진 이미지 및 텍스트를 표시하는 문서 및 예제입니다.
group: content
---


캡션이 있는 이미지와 같은 콘텐츠를 표시해야하는 경우, `<figure>` 을 사용하는 것이 좋습니다.

 `.figure` , `.figure-img` 와 `.figure-caption` 클래스를 사용하여 HTML5 `<figure>` 및 `<figcaption>` 요소에 대한 기본 스타일을 제공하십시오. 그림 이미지에는 명시적인 사이즈가 없으므로 `<img>` 에 `.img-fluid` 클래스를 추가하여 반응형으로 만드십시오.

{% example html %}
<figure class="figure">
  <img data-src="holder.js/400x300" class="figure-img img-fluid rounded" alt="모서리가 둥근 일반 사각형 이미지 입니다.">
  <figcaption class="figure-caption">위 이미지의 캡션입니다.</figcaption>
</figure>
{% endexample %}

[텍스트 정렬 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment)를 사용하면 캡션을 쉽게 정렬 할 수 있습니다.

{% example html %}
<figure class="figure">
  <img data-src="holder.js/400x300" class="figure-img img-fluid rounded" alt="모서리가 둥근 일반 사각형 이미지 입니다.">
  <figcaption class="figure-caption text-right">위 이미지의 캡션입니다.</figcaption>
</figure>
{% endexample %}
