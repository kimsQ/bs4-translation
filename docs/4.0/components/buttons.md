---
layout: docs
title: 버튼
description: 폼 액션, 대화상자 등의 작업에 다양한 크기, 상태 등을 지원하는 부트스트랩의 사용자 정의 버튼 스타일을 사용하십시오.
group: components
redirect_from: "/docs/4.0/components/"
toc: true
---


## 예제

부트스트랩에는 몇가지 미리 정의 된 버튼 스타일이 포함되어 있으며 각 스타일은 자체 의미론적 목적을 제공하며 더 많은 제어를 위해 몇가지 추가 기능이 포함되어 있습니다.

{% example html %}
{% for color in site.data.theme-colors %}
<button type="button" class="btn btn-{{ color.name }}">{{ color.name | capitalize }}</button>{% endfor %}

<button type="button" class="btn btn-link">Link</button>
{% endexample %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

## 버튼 태그

`.btn` 클래스는 `<button>` 요소와 함께 사용하도록 설계 되었습니다. 그러나 이 클래스는 `<a>` 또는 `<input>` 요소에서 사용할 수도 있습니다 (일부 브라우저는 약간 다른 렌더링을 적용 할수 있음).

When using button classes on `<a>` elements that are used to trigger in-page functionality (like collapsing content), rather than linking to new pages or sections within the current page, these links should be given a `role="button"` to appropriately convey their purpose to assistive technologies such as screen readers.

`<a>`요소에 `.btn` 클래스를 사용하여 페이지 내에서 기능 (예 : 컨텐츠 컬랩스)을 트리거하는 경우, 현재 페이지의 새 페이지 또는 섹션에 링크하는 대신 이러한 링크에 적절하게 `role="button"` 을 지정해야 합니다 목적을 스크린리더와 같은 보조 기술로 전달합니다.

{% example html %}
<a class="btn btn-primary" href="#" role="button">Link</a>
<button class="btn btn-primary" type="submit">Button</button>
<input class="btn btn-primary" type="button" value="Input">
<input class="btn btn-primary" type="submit" value="Submit">
<input class="btn btn-primary" type="reset" value="Reset">
{% endexample %}

## 아웃라인 버튼

무거운 배경색이 아닌 버튼이 필요 합니까? 기본 클래스를 `.btn-outline-*` 로 바꾸면 모든 버튼의 모든 배경 이미지와 색상이 제거 됩니다.


{% example html %}
{% for color in site.data.theme-colors %}
<button type="button" class="btn btn-outline-{{ color.name }}">{{ color.name | capitalize }}</button>{% endfor %}
{% endexample %}

## 사이즈

더 크거나 작은 버튼이 있을까요?  `.btn-lg` 또는 `.btn-sm` 을 추가 하십시오.

{% example html %}
<button type="button" class="btn btn-primary btn-lg">큰 버튼</button>
<button type="button" class="btn btn-secondary btn-lg">큰 버튼</button>
{% endexample %}

{% example html %}
<button type="button" class="btn btn-primary btn-sm">작은 버튼</button>
<button type="button" class="btn btn-secondary btn-sm">작은 버튼</button>
{% endexample %}

`.btn-block`을 추가하여 부모의 전체 너비에 걸쳐있는 블록 레벨 버튼을 만듭니다.

{% example html %}
<button type="button" class="btn btn-primary btn-lg btn-block">블록 레벨 버튼</button>
<button type="button" class="btn btn-secondary btn-lg btn-block">블록 레벨 버튼</button>
{% endexample %}

## 활성 상태 (Active)

활성(active) 상태가 되면 버튼이 눌려져 보입니다 (더 어두운 배경과 테두리 그리고 내부 그림자 적용). **가상 클래스를 사용하기 때문에 `<button>`에 클래스를 추가 할 필요가 없습니다.**
하지만 상태를 프로그래밍 방식으로 재현해야 하는 경우에는 `.active` (aria-pressed="true"속성 포함)를 추가하여 동일한 활성(active) 상태를 임의 적용할 수 있습니다.

{% example html %}
<a href="#" class="btn btn-primary btn-lg active" role="button" aria-pressed="true">Primary link</a>
<a href="#" class="btn btn-secondary btn-lg active" role="button" aria-pressed="true">Link</a>
{% endexample %}

## 비활성 상태 (Disabled)

`disabled` 속성을 `<button>` 요소에 추가하여 버튼을 비활성 상태로 만듭니다.

{% example html %}
<button type="button" class="btn btn-lg btn-primary" disabled>Primary button</button>
<button type="button" class="btn btn-secondary btn-lg" disabled>Button</button>
{% endexample %}

`<a>` 요소를 사용하는 비활성 버튼은 조금 다르게 동작합니다.

- `<a>`는 `disabled` 속성을 지원하지 않으므로 비활성화 된 것으로 보이게 하려면 `.disabled` 클래스를 추가 해야합니다.
- 미래지향 스타일이 포함되어 anchor 버튼의 모든 `pointer-events`를 비활성화 합니다. 해당 속성을 지원하는 브라우저에서는 비활성화 된 커서가 전혀 표시되지 않습니다.
- Disabled buttons should include the `aria-disabled="true"` attribute to indicate the state of the element to assistive technologies.
- 비활성화 된 버튼에는 보조 기술에게 요소의 상태를 표시하기 위해 `aria-disabled="true"` 속성이 포함 되어야 합니다.

{% example html %}
<a href="#" class="btn btn-primary btn-lg disabled" role="button" aria-disabled="true">Primary link</a>
<a href="#" class="btn btn-secondary btn-lg disabled" role="button" aria-disabled="true">Link</a>
{% endexample %}

{% callout warning %}
#### Link functionality caveat

The `.disabled` class uses `pointer-events: none` to try to disable the link functionality of `<a>`s, but that CSS property is not yet standardized. In addition, even in browsers that do support `pointer-events: none`, keyboard navigation remains unaffected, meaning that sighted keyboard users and users of assistive technologies will still be able to activate these links. So to be safe, add a `tabindex="-1"` attribute on these links (to prevent them from receiving keyboard focus) and use custom JavaScript to disable their functionality.
{% endcallout %}

## 버튼 플러그인

Do more with buttons. Control button states or create groups of buttons for more components like toolbars.
버튼으로 더 많은 작업을 수행하십시오. 컨트롤 버튼은 툴바와 같은 더 많은 구성 요소에 대한 버튼 그룹을 작성하거나 만듭니다.

### 토글 상태

`data-toggle="button"` 을 추가하여 버튼 `active` 상태를 토글 합니다. 버튼을 미리 토글할 경우에는 `.active` 클래스 **와** `aria-pressed="true"` 를 수동으로 `<button>`에 추가 해야 합니다.

{% example html %}
<button type="button" class="btn btn-primary" data-toggle="button" aria-pressed="false" autocomplete="off">
  Single toggle
</button>
{% endexample %}

### 체크박스와 라디오 버튼

Bootstrap's `.button` styles can be applied to other elements, such as `<label>`s, to provide checkbox or radio style button toggling. Add `data-toggle="buttons"` to a `.btn-group` containing those modified buttons to enable toggling in their respective styles.

부트스트랩의 `.button` 스타일은 `<label>`과 같은 요소에 적용되어 checkbox나 radio에 버튼 토글할 수 있습니다. 각각의 스타일에서 토글링할 수 있도록 변경된 버튼이 포함 된 `.btn-group`에 `data-toggle="buttons"` 을 추가합니다.

The checked state for these buttons is **only updated via `click` event** on the button. If you use another method to update the input—e.g., with `<input type="reset">` or by manually applying the input's `checked` property—you'll need to toggle `.active` on the `<label>` manually.

이 버튼들의 체크된 상태는 버튼의 **클릭 이벤트를 통해서만** 업데이트 됩니다. 다른 방법을 사용하여 `<input type="reset">` 또는 input의 `checked` 속성을 수동 적용하여 입력을 업데이트하는 경우 `<label>`을 수동으로 토글 해야합니다.

기본 선택된 버튼은 적용하려면 `.active` 클래스를 input의 `<label>`에 수동으로 추가 해야합니다.

{% example html %}
<div class="btn-group" data-toggle="buttons">
  <label class="btn btn-secondary active">
    <input type="checkbox" checked autocomplete="off"> 체크박스 1 (기본선택)
  </label>
  <label class="btn btn-secondary">
    <input type="checkbox" autocomplete="off"> 체크박스 2
  </label>
  <label class="btn btn-secondary">
    <input type="checkbox" autocomplete="off"> 체크박스 3
  </label>
</div>
{% endexample %}

{% example html %}
<div class="btn-group" data-toggle="buttons">
  <label class="btn btn-secondary active">
    <input type="radio" name="options" id="option1" autocomplete="off" checked> 라디오 1 (기본선택)
  </label>
  <label class="btn btn-secondary">
    <input type="radio" name="options" id="option2" autocomplete="off"> 라디오 2
  </label>
  <label class="btn btn-secondary">
    <input type="radio" name="options" id="option3" autocomplete="off"> 라디오 3
  </label>
</div>
{% endexample %}

### 메소드 (Methods)

| 메소드 | 설명 |
| --- | --- |
| `$().button('toggle')` | 푸시 상태를 토글합니다. 버튼에 활성화된 상태를 지정합니다.  |
