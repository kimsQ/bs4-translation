---
layout: docs
title: 이미지
description: 이미지에 반응형 동작(부모 요소보다 커지지 않도록)을 적용하고 클래스로 경량화된 스타일을 추가하는데 필요한 문서 및 예제.
group: content
toc: true
---



## 반응형 이미지

`.img-fluid`로 반응형 이미지가 됩니다. `max-width: 100%;` 과  `height: auto;` 가 부모 요소와 크기가 같도록 이미지에 적용됩니다.

<div class="bd-example">
  <img data-src="holder.js/100px250" class="img-fluid" alt="Generic responsive image">
</div>

{% highlight html %}
<img src="..." class="img-fluid" alt="반응형 이미지">
{% endhighlight %}

{% callout warning %}
#### SVG 이미지와 IE 10

Internet Explorer 10에서 `.img-fluid`를 사용하는 SVG 이미지는 불균형하게 크기가 지정됩니다. 이 문제를 해결하려면 필요한 경우 `width: 100% \9;` 를 추가하십시오. 이 픽스는 다른 이미지 의 크기를 잘못 지정하므로 부트스트랩이 자동으로 적용하지 않습니다.


{% endcallout %}

## 섬네일 이미지

[border-radius 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/borders/) 외에도 `.img-thumbnail` 을 사용하여 이미지에 둥근 1px 테두리 모양을 부여 할 수 있습니다.

<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="img-thumbnail" alt="A generic square placeholder image with a white border around it, making it resemble a photograph taken with an old instant camera">
</div>

{% highlight html %}
<img src="..." alt="..." class="img-thumbnail">
{% endhighlight %}

## 이미지 정렬하기

이미지를 [float 클래스]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/float)  또는 [텍스트 정렬 클래스]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/text/#text-alignment)로 정렬합니다. `block` 레벨 이미지는 [`.mx-auto` margin 유틸리티 클래스]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/#horizontal-centering)를 사용하여 중앙에 배치 할 수 있습니다.


<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="rounded float-left" alt="A generic square placeholder image with rounded corners">
  <img data-src="holder.js/200x200" class="rounded float-right" alt="A generic square placeholder image with rounded corners">
</div>

{% highlight html %}
<img src="..." class="rounded float-left" alt="...">
<img src="..." class="rounded float-right" alt="...">
{% endhighlight %}

<div class="bd-example bd-example-images">
  <img data-src="holder.js/200x200" class="rounded mx-auto d-block" alt="A generic square placeholder image with rounded corners">
</div>

{% highlight html %}
<img src="..." class="rounded mx-auto d-block" alt="...">
{% endhighlight %}

<div class="bd-example bd-example-images">
  <div class="text-center">
    <img data-src="holder.js/200x200" class="rounded" alt="A generic square placeholder image with rounded corners">
  </div>
</div>

{% highlight html %}
<div class="text-center">
  <img src="..." class="rounded" alt="...">
</div>
{% endhighlight %}


## Picture 요소

`<picture>` 요소를 사용하여 특정 `<img>` 요소에 대해 여러 `<source>` 요소를 지정하는 경우, `<picture>` 태그가 아닌 `<img>`에 `.img-*` 클래스를 추가해야 합니다.


{% highlight html %}
​<picture>
  <source srcset="..." type="image/svg+xml">
  <img src="..." class="img-fluid img-thumbnail" alt="...">
</picture>
{% endhighlight %}
