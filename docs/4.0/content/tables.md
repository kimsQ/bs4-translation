---
layout: docs
title: 테이블
description: 테이블 Opt-in 스타일 지정에 대한 문서와 예제. (자바스크립트 플러그인에서 많이 사용됨)
group: content
toc: true
---



## 기본 예제

캘린더 및 날짜선택 도구와 같은 third-party 위젯에서 테이블이 광범위하게 사용되기 때문에 테이블을  **opt-in** 하도록 설계했습니다. 기본 클래스 `.table`을 `<table>`에 추가한 다음, 맞춤 스타일을 적용하거나 내장된 다양한 클래스로 확장하면 됩니다.

가장 기본적인 테이블 마크업 방식을 사용하고, `.table` 이 적용된 테이블이 부트스트랩에서 어떻게 보이는지 살펴봅니다. **모든 테이블 스타일은 부트스트랩 4에서 상속되며**, 중첩된 테이블은 부모와 동일한 방식으로 스타일이 지정됩니다.


{% example html %}
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}


`.table-dark`로 색상을 반전시킬 수도 있습니다.(어두운 배경에 밝은 텍스트)

{% example html %}
<table class="table table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## 테이블 헤드 옵션

테이블 및 dark 테이블과 마찬가지로, `.thead-light` 또는 `.thead-dark` 를 사용하여 `<thead>` 를 밝게 또는 어둡게 표시 합니다.

{% example html %}
<table class="table">
  <thead class="thead-dark">
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>

<table class="table">
  <thead class="thead-light">
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## 줄무늬 행

Use `.table-striped` to add zebra-striping to any table row within the `<tbody>`.

`<tbody>` 내의 모든 테이블 행에 얼룩말 줄무늬를 추가하려면 `.table-striped` 를 사용하십시오.

{% example html %}
<table class="table table-striped">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-striped table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## 테두리가 적용된 테이블

테이블 과 셀의 모든면에 테두리를 적용하려면 `.table-bordered` 를 추가하십시오.

{% example html %}
<table class="table table-bordered">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@TwBootstrap</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">4</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-bordered table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@TwBootstrap</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">4</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## Hover가 적용된 행

`<tbody>` 내의 행에 hover 상태를 적용하려면 `.table-hover` 를 추가하십시오.

{% example html %}
<table class="table table-hover">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-hover table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## 작은 테이블

셀 padding을 절반으로 줄임으로써 테이블을 더 작게 만들려면 `.table-sm` 을 추가하십시오.

{% example html %}
<table class="table table-sm">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

{% example html %}
<table class="table table-sm table-dark">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}

## 상황별 클래스

상황별 클래스를 사용하여 행이나 셀에 색상을 지정합니다.

<div class="bd-example">
  <table class="table">
    <thead>
      <tr>
        <th scope="col">Type</th>
        <th scope="col">칼럼 제목</th>
        <th scope="col">칼럼 제목</th>
        <th scope="col">칼럼 제목</th>
      </tr>
    </thead>
    <tbody>
      <tr class="table-active">
        <th scope="row">Active</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr>
        <th scope="row">Default</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>

      {% for color in site.data.theme-colors %}
      <tr class="table-{{ color.name }}">
        <th scope="row">{{ color.name | capitalize }}</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>{% endfor %}
    </tbody>
  </table>
</div>

{% highlight html %}
<!-- 행(row)에 적용 -->
<tr class="table-active">...</tr>
{% for color in site.data.theme-colors %}
<tr class="table-{{ color.name }}">...</tr>{% endfor %}

<!-- 셀에 적용 (`td` 또는 `th`) -->
<tr>
  <td class="table-active">...</td>
  {% for color in site.data.theme-colors %}
  <td class="table-{{ color.name }}">...</td>{% endfor %}
</tr>
{% endhighlight %}

Dark 테이블에서는 기본 테이블 배경속성을 사용할 수 없지만 [텍스트 또는 백그라운드 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/colors/)를 사용하여 비슷한 스타일을 얻을 수 있습니다.

<div class="bd-example">
  <table class="table table-dark">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">칼럼 제목</th>
        <th scope="col">칼럼 제목</th>
        <th scope="col">칼럼 제목</th>
      </tr>
    </thead>
    <tbody>
      <tr class="bg-primary">
        <th scope="row">1</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr class="bg-success">
        <th scope="row">3</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr>
        <th scope="row">4</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr class="bg-info">
        <th scope="row">5</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr>
        <th scope="row">6</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr class="bg-warning">
        <th scope="row">7</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr>
        <th scope="row">8</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
      <tr class="bg-danger">
        <th scope="row">9</th>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
        <td>칼럼 내용</td>
      </tr>
    </tbody>
  </table>
</div>

{% highlight html %}
<!-- 행에 적용 -->
<tr class="bg-primary">...</tr>
<tr class="bg-success">...</tr>
<tr class="bg-warning">...</tr>
<tr class="bg-danger">...</tr>
<tr class="bg-info">...</tr>

<!-- 셀에 적용 (`td` 또는 `th`) -->
<tr>
  <td class="bg-primary">...</td>
  <td class="bg-success">...</td>
  <td class="bg-warning">...</td>
  <td class="bg-danger">...</td>
  <td class="bg-info">...</td>
</tr>
{% endhighlight %}

{% capture callout-include %}{% include callout-warning-color-assistive-technologies.md %}{% endcapture %}
{{ callout-include | markdownify }}

## 반응형 테이블

`.table`에 `.table-responsive{-sm|-md|-lg|-xl}` 을 추가하여 각각의 최대 너비 중단점 575px, 767px, 991px 및 1199px에서 각각 가로 스크롤 하도록 하여 반응형 테이블을 만듭니다.

테이블이 컨테이너 보다 넓어서 항상 가로 스크롤이 필요한 경우, `.table` 에 `.table-responsive` 클래스를 추가하세요.

{% callout warning %}
#### 수직 클리핑/자르기

반응형 테이블은 `overflow-y: hidden` 을 사용합니다. 이 overflow는 테이블의 아래쪽이나 위쪽 가장자리를 넘어서는 모든 내용을 잘라냅니다. 특히 이것은 드롭다운 메뉴 및 기타 third-party 위젯을 잘라낼 수 있습니다.

{% endcallout %}

<div class="bd-example">
  <table class="table table-responsive">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">1</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <th scope="row">3</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
    </tbody>
  </table>

  <table class="table table-bordered table-responsive-lg">
    <thead>
      <tr>
        <th scope="col">#</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
        <th scope="col">Table heading</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <th scope="row">1</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <th scope="row">2</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
      <tr>
        <th scope="row">3</th>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
        <td>Table cell</td>
      </tr>
    </tbody>
  </table>
</div>

{% highlight html %}
<table class="table table-responsive">
  ...
</table>
{% endhighlight %}


## 캡션

`<caption>`은 제목과 같은 기능을 합니다. 그것은 스크린리더를 사용하는 사용자들이 테이블을 찾고 그것이 무엇인지 이해하고 '그것을 읽고 싶은지'를 결정하는 것을 도와 줍니다.

{% example html %}
<table class="table">
  <caption>회원목록</caption>
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">이름</th>
      <th scope="col">성</th>
      <th scope="col">아이디</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td>Larry</td>
      <td>the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
{% endexample %}
