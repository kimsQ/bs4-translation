---
layout: docs
title: 코드
description: 인라인 및 멀티라인 코드블록을 표시 하기위한 문서 및 예제.
group: content
toc: true
---



## 인라인 코드

`<code>`를 사용하여 인라인 코드 스니핏을 감사세요. HTML 꺾쇠 괄호를 이스케이프 해야합니다.

{% example html %}
예를 들어, <code>&lt;section&gt;</code> 은 인라인으로 감싸져야 합니다..
{% endexample %}

## 코드 블럭

여러 줄의 코드에는 `<pre>`를 사용하십시오. 다시 한번, 올바른 렌더링을 위해 코드에서 꺾쇠 괄호를 이스케이프 해야합니다. 350px의 최대 높이를 설정하고 세로 스크롤 막대를 제공하는 `.pre-scrollable` 클래스를 선택적으로 추가 할 수 있습니다.

{% example html %}
<pre><code>&lt;p&gt;샘플 텍스트는 여기에 ...&lt;/p&gt;
&lt;p&gt;그리고 또 다른 샘플 텍스트는 여기에 ....&lt;/p&gt;
</code></pre>
{% endexample %}

## 변수

지시 변수(indicating variables)의 경우 `<var>` 태그를 사용하십시오.

{% example html %}
<var>y</var> = <var>m</var><var>x</var> + <var>b</var>
{% endexample %}

## 사용자 입력

키보드를 통해 일반적으로 입력되는 사항을 나타내려면 <`<kbd>`를 사용하십시오.

{% example html %}
디렉토리를 전환하려면 <kbd>cd</kbd> 다음에 디렉토리 이름을 입력하십시오.<br>
설정을 편집하려면 <kbd><kbd>ctrl</kbd> + <kbd>,</kbd></kbd> 를 누르세요.
{% endexample %}

## 샘플 출력

프로그램의 샘플 출력을 표시하려면 `<samp>` 태그를 사용하십시오.

{% example html %}
<samp>이 텍스트는 컴퓨터 프로그램의 샘플 출력으로 처리됩니다.</samp>
{% endexample %}
