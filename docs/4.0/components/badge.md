---
layout: docs
title: 배지 Badges
description: 카운터 숫자 및 라벨 구성요소인 배지에 대한 문서 및 예제
group: components
toc: true
---



## 예제

배지는 상대 글꼴 크기 및 `em` 단위를 사용하여 직계 부모 요소의 크기와 일치하도록 배율을 조정합니다.

<div class="bd-example">
<div class="h1">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
<div class="h2">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
<div class="h3">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
<div class="h4">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
<div class="h5">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
<div class="h6">헤드라인 예제 <span class="badge badge-secondary">New</span></div>
</div>

{% highlight html %}
<h1>헤드라인 예제 <span class="badge badge-secondary">New</span></h1>
<h2>헤드라인 예제 <span class="badge badge-secondary">New</span></h2>
<h3>헤드라인 예제 <span class="badge badge-secondary">New</span></h3>
<h4>헤드라인 예제 <span class="badge badge-secondary">New</span></h4>
<h5>헤드라인 예제 <span class="badge badge-secondary">New</span></h5>
<h6>헤드라인 예제 <span class="badge badge-secondary">New</span></h6>
{% endhighlight %}

배지는 링크 또는 버튼의 일부로 사용하여 카운터를 제공 할 수 있습니다.

{% example html %}
<button type="button" class="btn btn-primary">
  알림 <span class="badge badge-light">4</span>
</button>
{% endexample %}

Note that depending on how they are used, badges may be confusing for users of screen readers and similar assistive technologies. While the styling of badges provides a visual cue as to their purpose, these users will simply be presented with the content of the badge. Depending on the specific situation, these badges may seem like random additional words or numbers at the end of a sentence, link, or button.

Unless the context is clear (as with the "Notifications" example, where it is understood that the "4" is the number of notifications), consider including additional context with a visually hidden piece of additional text.

{% example html %}
<button type="button" class="btn btn-primary">
  프로필 <span class="badge badge-light">9</span>
  <span class="sr-only">unread messages</span>
</button>
{% endexample %}

## Contextual variations

Add any of the below mentioned modifier classes to change the appearance of a badge.

{% example html %}
{% for color in site.data.theme-colors %}
<span class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

## Pill badges

Use the `.badge-pill` modifier class to make badges more rounded (with a larger `border-radius` and additional horizontal `padding`). Useful if you miss the badges from v3.

{% example html %}
{% for color in site.data.theme-colors %}
<span class="badge badge-pill badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endexample %}

## 링크

Using the `.badge` classes with the `<a>` element quickly provide _actionable_ badges with hover and focus states.

{% example html %}
{% for color in site.data.theme-colors %}
<a href="#" class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</a>{% endfor %}
{% endexample %}
