---
layout: docs
title: 클리어 픽스 Clearfix
description: clearfix 유틸리티를 추가하여 컨테이너 내에서 플로팅 된 내용을 쉽고 빠르게 초기화 할 수 있습니다.
group: utilities
toc: true
---

**부모 요소** 에 `.clearfix`를 추가하여 쉽게 `float` 를 초기화 하세요. 믹스인(mixin) 으로 사용할 수도 있습니다.

{% highlight html %}
<div class="clearfix">...</div>
{% endhighlight %}

{% highlight scss %}
// 믹스인(mixin) 정의
@mixin clearfix() {
  &::after {
    display: block;
    content: "";
    clear: both;
  }
}

// 믹스인(mixin)의 적용
.element {
  @include clearfix;
}
{% endhighlight %}

다음 예제에서는 clearfix를 사용하는 방법을 보여줍니다. `.clearfix`가 없으면 버튼 상위의 div가 버튼들을 감싸지 못해, 레이아웃이 깨질 수 있습니다.

{% example html %}
<div class="bg-info clearfix">
  <button type="button" class="btn btn-secondary float-left">왼쪽으로 플로팅된 예제 버튼</button>
  <button type="button" class="btn btn-secondary float-right">오른쪽으로 플로팅된 예제 버튼</button>
</div>
{% endexample %}
