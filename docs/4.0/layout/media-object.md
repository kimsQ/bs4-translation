---
layout: docs
title: 미디어 객체
description: 블로그 코멘트, 트윗 등과 같은 반복적인 구성 요소를 구축할 수 있는 미디어 객체에 대한 문서와 예제
group: layout
toc: true
---



## 예제

The [media object](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/) helps build complex and repetitive components where some media is positioned alongside content that doesn't wrap around said media. Plus, it does this with only two required classes thanks to flexbox.

[미디어 객체](http://www.stubbornella.org/content/2010/06/25/the-media-object-saves-hundreds-of-lines-of-code/)는 일부 미디어가 상기 미디어를 둘러싸지 않는 콘텐트와 나란히 배치되는 복잡하고 반복적인 구성 요소를 구축하는 것을 돕습니다. 또한 flexbox 덕분에 두 가지 필수 클래스 만으로 이 작업을 수행 할 수 있습니다.

Below is an example of a single media object. Only two classes are required—the wrapping `.media` and the `.media-body` around your content. Optional padding and margin can be controlled through [spacing utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/).

다음은 단일 미디어 객체의 예제 입니다. 콘텐츠를 주변에 `.media` 와 `.media-body` 라는 두 가지 클래스 만 있으면 됩니다. 선택적으로 padding 및 margin은 [간격 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/)를 통해 제어 할수 있습니다.

{% example html %}
<div class="media">
  <img class="mr-3" data-src="holder.js/64x64" alt="임시 이미지">
  <div class="media-body">
    <h5 class="mt-0">미디어 헤드라인</h5>
    동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
  </div>
</div>
{% endexample %}

{% callout warning %}
##### Flexbug #12: Inline elements aren't treated as flex items

Internet Explorer 10-11 do not render inline elements like links or images (or `::before` and `::after` pseudo-elements) as flex items. The only workaround is to set a non-inline `display` value (e.g., `block`, `inline-block`, or `flex`). We suggest using `.d-flex`, one of our [display utilities]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/display/), as an easy fix.

**Source:** [Flexbugs on GitHub](https://github.com/philipwalton/flexbugs#12-inline-elements-are-not-treated-as-flex-items)
{% endcallout %}

## 중첩

Media objects can be infinitely nested, though we suggest you stop at some point. Place nested `.media` within the `.media-body` of a parent media object.

{% example html %}
<div class="media">
  <img class="mr-3" data-src="holder.js/64x64" alt="임시 이미지">
  <div class="media-body">
    <h5 class="mt-0">미디어 헤드라인</h5>
    동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.

    <div class="media mt-3">
      <a class="pr-3" href="#">
        <img data-src="holder.js/64x64" alt="임시 이미지">
      </a>
      <div class="media-body">
        <h5 class="mt-0">미디어 헤드라인</h5>
        동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
      </div>
    </div>
  </div>
</div>
{% endexample %}

## 정렬

Media in a media object can be aligned with flexbox utilities to the top (default), middle, or end of your `.media-body` content.

{% example html %}
<div class="media">
  <img class="align-self-start mr-3" data-src="holder.js/64x64" alt="임시 이미지">
  <div class="media-body">
    <h5 class="mt-0">상단 정렬 미디어</h5>
    <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.</p>
    <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세. 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세.</p>
  </div>
</div>
{% endexample %}

{% example html %}
<div class="media">
  <img class="align-self-center mr-3" data-src="holder.js/64x64" alt="임시 이미지">
  <div class="media-body">
    <h5 class="mt-0">가운데 정렬 미디어</h5>
    <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.</p>
    <p class="mb-0">동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세. 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세.</p>
  </div>
</div>
{% endexample %}

{% example html %}
<div class="media">
  <img class="align-self-end mr-3" data-src="holder.js/64x64" alt="임시 이미지">
  <div class="media-body">
    <h5 class="mt-0">하단 정렬 미디어</h5>
    <p>동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.</p>
    <p class="mb-0">동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세. 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세.</p>
  </div>
</div>
{% endexample %}

## 순서

Change the order of content in media objects by modifying the HTML itself, or by adding some custom flexbox CSS to set the `order` property (to an integer of your choosing).

{% example html %}
<div class="media">
  <div class="media-body">
    <h5 class="mt-0 mb-1">미디어 객체</h5>
    동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
  </div>
  <img class="ml-3" data-src="holder.js/64x64" alt="임시 이미지">
</div>
{% endexample %}

## 미디어 리스트

Because the media object has so few structural requirements, you can also use these classes on list HTML elements. On your `<ul>` or `<ol>`, add the `.list-unstyled` to remove any browser default list styles, and then apply `.media` to your `<li>`s. As always, use spacing utilities wherever needed to fine tune.

{% example html %}
<ul class="list-unstyled">
  <li class="media">
    <img class="mr-3" data-src="holder.js/64x64" alt="임시 이미지">
    <div class="media-body">
      <h5 class="mt-0 mb-1">리스트 기반 미디어 객체</h5>
      동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
    </div>
  </li>
  <li class="media my-4">
    <img class="mr-3" data-src="holder.js/64x64" alt="임시 이미지">
    <div class="media-body">
      <h5 class="mt-0 mb-1">리스트 기반 미디어 객체</h5>
      동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
    </div>
  </li>
  <li class="media">
    <img class="mr-3" data-src="holder.js/64x64" alt="임시 이미지">
    <div class="media-body">
      <h5 class="mt-0 mb-1">리스트 기반 미디어 객체</h5>
      동해물과 백두산이 마르고 닳도록 하느님이 보우하사 우리나라 만세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세 남산 위에 저 소나무 철갑을 두른듯 바람서리 불변함은 우리 기상일세 무궁화 삼천리 화려 강산 대한사람 대한으로 길이 보전하세.
    </div>
  </li>
</ul>
{% endexample %}
