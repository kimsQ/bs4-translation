---
layout: docs
title: 알림 Alerts
description: 유연한 알림 메시지를 통해 일반적 사용자 작업에 대한 상황별 피드백 메시지를 제공하십시오.
group: components
toc: true
---



## 예제

알림은 임의의 텍스트 길이를 사용할 뿐만 아니라 닫기 버튼도 사용할 수 있습니다. 올바른 스타일링을 위해서는 8가지 상황별 클래스 중 하나를 사용 하십시오 (예 : `.alert-success`). 닫기를 원할 경우, [alerts jQuery plugin](#dismissing)을 사용하십시오.


{% example html %}
{% for color in site.data.theme-colors %}
<div class="alert alert-{{ color.name }}" role="alert">
  This is a {{ color.name }} alert—check it out!
</div>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

### 링크 칼라

Use the `.alert-link` utility class to quickly provide matching colored links within any alert.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="alert alert-{{ color.name }}" role="alert">
  This is a {{ color.name }} alert with <a href="#" class="alert-link">an example link</a>. Give it a click if you like.
</div>{% endfor %}
{% endexample %}

### 추가 컨텐츠

Alerts can also contain additional HTML elements like headings, paragraphs and dividers.

{% example html %}
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">Well done!</h4>
  <p>Aww yeah, you successfully read this important alert message. This example text is going to run a bit longer so that you can see how spacing within an alert works with this kind of content.</p>
  <hr>
  <p class="mb-0">Whenever you need to, be sure to use margin utilities to keep things nice and tidy.</p>
</div>
{% endexample %}


### 닫기 Dismissing

Using the alert JavaScript plugin, it's possible to dismiss any alert inline. Here's how:

- Be sure you've loaded the alert plugin, or the compiled Bootstrap JavaScript.
- If you're building our JS from source, it [requires `util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#util). The compiled version includes this.
- Add a dismiss button and the `.alert-dismissible` class, which adds extra padding to the right of the alert and positions the `.close` button.
- On the dismiss button, add the `data-dismiss="alert"` attribute, which triggers the JavaScript functionality. Be sure to use the `<button>` element with it for proper behavior across all devices.
- To animate alerts when dismissing them, be sure to add the `.fade` and `.show` classes.

You can see this in action with a live demo:

{% example html %}
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>Holy guacamole!</strong> You should check in on some of those fields below.
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
{% endexample %}

## 자바스크립트 동작

### 트리거 Triggers

Enable dismissal of an alert via JavaScript:

{% highlight js %}
$(".alert").alert()
{% endhighlight %}

Or with `data` attributes on a button **within the alert**, as demonstrated above:

{% highlight html %}
<button type="button" class="close" data-dismiss="alert" aria-label="Close">
  <span aria-hidden="true">&times;</span>
</button>
{% endhighlight %}

Note that closing an alert will remove it from the DOM.

### 메소드 Methods

| Method | Description |
| --- | --- |
| `$().alert()` | Makes an alert listen for click events on descendant elements which have the `data-dismiss="alert"` attribute. (Not necessary when using the data-api's auto-initialization.) |
| `$().alert('close')` | Closes an alert by removing it from the DOM. If the `.fade` and `.show` classes are present on the element, the alert will fade out before it is removed. |

{% highlight js %}$(".alert").alert('close'){% endhighlight %}

### 이벤트 Events

Bootstrap's alert plugin exposes a few events for hooking into alert functionality.

| Event | Description |
| --- | --- |
| `close.bs.alert` | This event fires immediately when the <code>close</code> instance method is called. |
| `closed.bs.alert` | This event is fired when the alert has been closed (will wait for CSS transitions to complete). |

{% highlight js %}
$('#myAlert').on('closed.bs.alert', function () {
  // do something…
})
{% endhighlight %}
