---
layout: docs
title: 레이아웃 유틸리티
description: 모바일 친화적이고 반응형웹 개발을 좀더 빠르게 하기위해 부트스트랩에는 콘텐츠를 표시, 숨기기, 정렬 및 간격을 조정하기 위한 수십가지 유틸리티 클래스가 포함되어 있습니다.
group: layout
toc: true
---





## `display` 변경

`display` 유틸리티의 일반값을 적절하게 변경하려면 `display` 유틸리티를 사용하십시오. 그리드 시스템, 컨텐츠 또는 컴포넌트와 혼합하여 특정 뷰포트에 표시하거나 숨깁니다.


## Flexbox 옵션

부트스트랩 4는 flexbox로 만들어졌지만, 불필요한 재정의 코드가 필요하고 예기치 않게 변경되는 주요 브라우저 때문에 모든 요소의 `display`가 `display: flex`로 변경되지는 않았습니다. 대부분의 구성 요소는 flexbox 적용이 가능하도록 구현되었습니다.

`display: flex` 를 요소에 추가 해야하는 경우, `.d-flex` 또는 관련 반응형 처리 클래스 (예 : `.d-sm-flex`)를 사용하십시오.
크기조정, 정렬, 간격조정 등을 위해 [flexbox 유틀리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/flex/)를 사용하려면 이 클래스 또는 `display` 값의 변경이 필요합니다.

## Margin 과 padding

[spacing 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/spacing/)를 사용하여 요소 및 컴포넌트의 간격 및 크기 조정을 제어 하십시오. 부트스트랩 4에는 `1rem` 값인 `$spacer` 변수를 기반으로 하는 5단계의 spacing 유틸리티가 포함 되어있습니다. 모든 뷰포트에 대응하거나(예 : `margin-right: 1rem` 의 경우 `.mr-3`) 특정 뷰포트를 지정하려면 (예 : `md` breakpoint에서 시작되는 `margin-right: 1rem`의 경우 `.mr-md-3`) 반응형 응용방법을 참조 하십시오.


## `visibility` 전환

`display`를 전환할 필요가 없는 경우, [visibility 유틸리티]({{ site.baseurl }}/docs/{{ site.docs_version }}/utilities/visibility/)를 사용하여 요소의 `visibility`을 전환 할 수 있습니다. 보이지 않는 요소는 여전히 페이지의 레이아웃에 영향을 미치지만 방문자에게 시각적으로 숨길 수 있습니다.
