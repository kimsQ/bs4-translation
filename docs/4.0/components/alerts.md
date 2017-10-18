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
  이것은 {{ color.name }} 입니다. 확인해 보세요.!
</div>{% endfor %}
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

### 링크 칼라

`.alert-link` 유틸리티 클래스를 사용하여 모든 경고에서 일치하는 컬러 링크를 빠르게 제공하십시오.

{% example html %}
{% for color in site.data.theme-colors %}
<div class="alert alert-{{ color.name }}" role="alert">
  이것은 <a href="#" class="alert-link">링크</a>를 포함한 {{ color.name }} 경고 예제 입니다. 원한다면 클릭하십시오.
</div>{% endfor %}
{% endexample %}

### 추가 컨텐츠

경고에는 제목, 단락 및 구분선과 같은 추가 HTML 요소가 포함될 수도 있습니다.

{% example html %}
<div class="alert alert-success" role="alert">
  <h4 class="alert-heading">잘하셨습니다!</h4>
  <p>네, 중요한 경고 메시지를 성공적으로 읽으셨군요. 이 예제 텍스트는 경고를 조금 더 오래 실행하여 알림 내부에서 간격이 이 종류의 콘텐츠와 어떻게 연동되는지 확인할 수 있습니다.</p>
  <hr>
  <p class="mb-0">그럴 필요가 있을 때마다 margin 유틸리티를 사용하여 멋지고 깔끔하게 유지하십시오.</p>
</div>
{% endexample %}


### 닫기 Dismissing

alert 자바스크립트 플러그인을 사용하면 모든 알림을 인라인에서 해제 할 수 있습니다. 방법은 다음과 같습니다.

- alert 플러그인 이나 컴파일된 부트스트랩 JS를 로드했는지 확인하십시오.
- 소스에서 JS를 빌드하는 경우 [`util.js`]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/javascript/#유틸-util)가 필요합니다. 컴파일된 버전에는 이것이 포함되어 있습니다.
- 해제 버튼과 `.alert-dismissible` 클래스를 추가합니다. 알림의 오른쪽에 패딩을 추가하고 `.close` 버튼 위치를 지정합니다.
- 닫기버튼에서 `data-dismiss="alert"` 속성을 추가하면 JavaScript 기능이 트리거 됩니다. 모든 디바이스에서 올바르게 동작하려면 `<button>` 요소를 사용하십시오.
- 알림이 해제될 때 애니메이션을 적용하려면 `.fade` 와 `.show` 클래스를 추가 해야합니다.

라이브 데모로 실제 동작해 볼 수 있습니다.

{% example html %}
<div class="alert alert-warning alert-dismissible fade show" role="alert">
  <strong>맙소사!</strong> 아래의 몇가지 필드를 확인해야 합니다.
  <button type="button" class="close" data-dismiss="alert" aria-label="Close">
    <span aria-hidden="true">&times;</span>
  </button>
</div>
{% endexample %}

## 자바스크립트 동작

### 트리거 Triggers

자바스크립트를 통해 알림을 해제 할 수 있습니다.

{% highlight js %}
$(".alert").alert()
{% endhighlight %}

또는 위에서 설명한 바와 같이 **알림 내부** 버튼에 `data` 속성을 사용하여 다음을 수행할 수 있습니다.

{% highlight html %}
<button type="button" class="close" data-dismiss="alert" aria-label="Close">
  <span aria-hidden="true">&times;</span>
</button>
{% endhighlight %}

알림을 닫으면 알림이 DOM에서 제거됩니다.

### 메소드 Methods

| 메소드 | 설명 |
| --- | --- |
| `$().alert()` | Makes an alert listen for click events on descendant elements which have the `data-dismiss="alert"` attribute. (Not necessary when using the data-api's auto-initialization.) `data-dismiss="alert"` 속성이 있는 하위 요소에 대한 클릭 이벤트를 수신합니다. (datai-api의 자동 초기화를 사용할 때는 필요 없음) |
| `$().alert('close')` | 알림을 DOM에서 제거하여 닫습니다. 요소에 `.fade` 와 `.show` 클래스가 있으면 알림이 제거되기 전에 fade out 됩니다. |

{% highlight js %}$(".alert").alert('close'){% endhighlight %}

### 이벤트 Events

Bootstrap's alert plugin exposes a few events for hooking into alert functionality.
부트스트랩 알림 플러그인은 경고 기능에 연결 하기위한 몇가지 이벤트를 노출합니다.

| 이벤트 | 설명 |
| --- | --- |
| `close.bs.alert` |  <code>close</code> 메서드가 호출될 때 이 이벤트가 즉시 발생 합니다. |
| `closed.bs.alert` | 이 이벤트는 알림 닫힘이 완료되면 시작됩니다 (CSS 전환이 완료 될 때까지 대기합니다).|

{% highlight js %}
$('#myAlert').on('closed.bs.alert', function () {
  // do something…
})
{% endhighlight %}
