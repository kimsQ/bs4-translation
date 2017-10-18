---
layout: docs
title: 버튼 그룹
description: 버튼 그룹으로 한줄에 버튼을 그룹화 하고, 자바스크립트를 사용하여 슈퍼 파워를 부여합니다.
group: components
toc: true
---

## 기본 예제

 `.btn-group` 으로 `.btn`이 있는 일련의 버튼을 감싸세요. [버튼 플러그인]({{ site.baseurl }}/docs/{{ site.docs_version }}/components/buttons/#버튼-플러그인)으로 자바스크립트 라디오 및 체크박스 스타일 동작을 선택적으로 추가 할 수도 있습니다.


{% example html %}
<div class="btn-group" role="group" aria-label="기본 예제">
  <button type="button" class="btn btn-secondary">좌측</button>
  <button type="button" class="btn btn-secondary">가운데</button>
  <button type="button" class="btn btn-secondary">우측</button>
</div>
{% endexample %}

{% callout warning %}
#### Ensure correct `role` and provide a label

In order for assistive technologies (such as screen readers) to convey that a series of buttons is grouped, an appropriate `role` attribute needs to be provided. For button groups, this would be `role="group"`, while toolbars should have a `role="toolbar"`.

In addition, groups and toolbars should be given an explicit label, as most assistive technologies will otherwise not announce them, despite the presence of the correct role attribute. In the examples provided here, we use `aria-label`, but alternatives such as `aria-labelledby` can also be used.
{% endcallout %}

## 버튼 툴바

toolbar 안에 버튼그룹 셋을 결합하여 보다 복잡한 구성요소를 만듭니다. 필요에 따라 유틸리티 클래스를 사용하여 그룹, 버튼 등을 배치 하십시오.


{% example html %}
<div class="btn-toolbar" role="toolbar" aria-label="버튼 그룹이 있는 툴바">
  <div class="btn-group mr-2" role="group" aria-label="첫번째 그룹">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="btn-group mr-2" role="group" aria-label="두번째 그룹">
    <button type="button" class="btn btn-secondary">5</button>
    <button type="button" class="btn btn-secondary">6</button>
    <button type="button" class="btn btn-secondary">7</button>
  </div>
  <div class="btn-group" role="group" aria-label="세번째 그룹">
    <button type="button" class="btn btn-secondary">8</button>
  </div>
</div>
{% endexample %}

toolbar 안에서 입력 그룹을 버튼 그룹과 자유롭게 조합하십시오. 위의 예와 비슷하게, 적절히 배치하기 위해서는 유틸리티가 필요할 것입니다.

{% example html %}
<div class="btn-toolbar mb-3" role="toolbar" aria-label="Toolbar with button groups">
  <div class="btn-group mr-2" role="group" aria-label="첫번째 그룹">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="input-group">
    <span class="input-group-addon" id="btnGroupAddon">@</span>
    <input type="text" class="form-control" placeholder="입력그룹 예제" aria-label="입력그룹 예제" aria-describedby="btnGroupAddon">
  </div>
</div>

<div class="btn-toolbar justify-content-between" role="toolbar" aria-label="버튼 그룹이 있는 툴바">
  <div class="btn-group" role="group" aria-label="첫번째 그룹">
    <button type="button" class="btn btn-secondary">1</button>
    <button type="button" class="btn btn-secondary">2</button>
    <button type="button" class="btn btn-secondary">3</button>
    <button type="button" class="btn btn-secondary">4</button>
  </div>
  <div class="input-group">
    <span class="input-group-addon" id="btnGroupAddon2">@</span>
    <input type="text" class="form-control" placeholder="입력그룹 예제" aria-label="입력그룹 예제" aria-describedby="btnGroupAddon2">
  </div>
</div>
{% endexample %}

## 크기 조정

그룹의 모든 버튼에 크기 조정 클래스를 적용하는 대신, 단지 각각의 `.btn-group`에 `.btn-group-*` 을 추가하면 됩니다.

<div class="bd-example">
  <div class="btn-group btn-group-lg" role="group" aria-label="큰 버튼그룹">
    <button type="button" class="btn btn-secondary">왼쪽</button>
    <button type="button" class="btn btn-secondary">중간</button>
    <button type="button" class="btn btn-secondary">오른쪽</button>
  </div>
  <br>
  <div class="btn-group" role="group" aria-label="기본 버튼그룹">
    <button type="button" class="btn btn-secondary">왼쪽</button>
    <button type="button" class="btn btn-secondary">중간</button>
    <button type="button" class="btn btn-secondary">오른쪽</button>
  </div>
  <br>
  <div class="btn-group btn-group-sm" role="group" aria-label="작은 버튼그룹">
    <button type="button" class="btn btn-secondary">왼쪽</button>
    <button type="button" class="btn btn-secondary">중간</button>
    <button type="button" class="btn btn-secondary">오른쪽</button>
  </div>
</div>

{% highlight html %}
<div class="btn-group btn-group-lg" role="group" aria-label="...">...</div>
<div class="btn-group" role="group" aria-label="...">...</div>
<div class="btn-group btn-group-sm" role="group" aria-label="...">...</div>
{% endhighlight %}

## 중첩

Place a `.btn-group` within another `.btn-group` when you want dropdown menus mixed with a series of buttons.

드롭다운 메뉴를 일련의 버튼들과 함께 사용하려면 `.btn-group` 안에 `.btn-group`을 배치 하십시오.

{% example html %}
<div class="btn-group" role="group" aria-label="Button group with nested dropdown">
  <button type="button" class="btn btn-secondary">1</button>
  <button type="button" class="btn btn-secondary">2</button>

  <div class="btn-group" role="group">
    <button id="btnGroupDrop1" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
      드롭다운
    </button>
    <div class="dropdown-menu" aria-labelledby="btnGroupDrop1">
      <a class="dropdown-item" href="#">다롭다운 링크</a>
      <a class="dropdown-item" href="#">다롭다운 링크</a>
    </div>
  </div>
</div>
{% endexample %}

## 수직 변형

한 세트의 버튼을 수평이 아닌 수직으로 수직으로 표시합니다.  **분할 버튼 드롭 다운은 여기에서 지원되지 않습니다.**

<div class="bd-example">
  <div class="btn-group-vertical" role="group" aria-label="세로형 버튼그룹">
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
  </div>
</div>


<div class="bd-example">
  <div class="btn-group-vertical" role="group" aria-label="세로형 버튼그룹">
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop1" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        다롭다운
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop1">
        <a class="dropdown-item" href="#">드롭다운 링크</a>
        <a class="dropdown-item" href="#">드롭다운 링크</a>
      </div>
    </div>
    <button type="button" class="btn btn-secondary">버튼</button>
    <button type="button" class="btn btn-secondary">버튼</button>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop2" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        드롭다운
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop2">
        <a class="dropdown-item" href="#">드롭다운 링크</a>
        <a class="dropdown-item" href="#"드롭다운 링크</a>
      </div>
    </div>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop3" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        드롭다운
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop3">
        <a class="dropdown-item" href="#">드롭다운 링크</a>
        <a class="dropdown-item" href="#">드롭다운 링크</a>
      </div>
    </div>
    <div class="btn-group" role="group">
      <button id="btnGroupVerticalDrop4" type="button" class="btn btn-secondary dropdown-toggle" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
        드롭다운
      </button>
      <div class="dropdown-menu" aria-labelledby="btnGroupVerticalDrop4">
        <a class="dropdown-item" href="#">드롭다운 링크</a>
        <a class="dropdown-item" href="#">드롭다운 링크</a>
      </div>
    </div>
  </div>
</div>

{% highlight html %}
<div class="btn-group-vertical">
  ...
</div>
{% endhighlight %}
