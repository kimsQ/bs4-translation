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

그것들이 사용되는 방법에 따라서, 스크린리더 사용자 및 유사한 보조 기술 사용자는 배지를 혼동 할 수 있습니다. 배지 스타일링은 목적에 따라 시각적 신호를 제공하지만 배지의 내용은 간단하게 표시됩니다. 배지들은 문장이나 링크 또는 버튼의 끝에 추가 단어나 숫자처럼 보일 수 있다

Unless the context is clear (as with the "Notifications" example, where it is understood that the "4" is the number of notifications), consider including additional context with a visually hidden piece of additional text.

문맥이 분명하지 않으면 (예 : "알림" 예제에서와 같이 "4"가 알림 수 임을 인식하는 경우) 시각적으로 숨겨진 추가 텍스트를 포함한 추가 컨텍스트를 포함하는 것을 고려하십시오.

{% example html %}
<button type="button" class="btn btn-primary">
  프로필 <span class="badge badge-light">9</span>
  <span class="sr-only">읽지 않은 메시지</span>
</button>
{% endexample %}

## 문맥의 변형 Contextual variations

Add any of the below mentioned modifier classes to change the appearance of a badge. 배지의 모양을 변경하려면 아래에 언급된 클래스 중 하나를 추가하십시오.

{% example html %}
{% for color in site.data.theme-colors %}
<span class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

## 알약형 배지 Pill badges

배지를 더 둥글게 만들려면 `.badge-pill` 클래스를 사용 하십시오 (보다 큰 `border-radius`와 가로 `padding` 사용). v3에서 배지를 놓친 경우 유용합니다.

{% example html %}
{% for color in site.data.theme-colors %}
<span class="badge badge-pill badge-{{ color.name }}">{{ color.name | capitalize }}</span>{% endfor %}
{% endexample %}

## 링크

`<a>` 요소와 함께 `.badge` 클래스를 사용하면 hover 와 focus 상태가 있는  _실행가능한_ 배지를 신속하게 제공 할 수 있습니다.

{% example html %}
{% for color in site.data.theme-colors %}
<a href="#" class="badge badge-{{ color.name }}">{{ color.name | capitalize }}</a>{% endfor %}
{% endexample %}
