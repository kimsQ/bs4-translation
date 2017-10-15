---
layout: docs
title: 닫기 아이콘
description: 모달 및 경고와 같은 콘텐츠를 닫으려면 닫기 아이콘을 사용합니다.
group: utilities
toc: true
---

아래 예제에서 `aria-label`을 사용한 것처럼 **스크린 리더를 위해 닫기 텍스트를 포함 시켜야합니다.**

{% example html %}
<button type="button" class="close" aria-label="닫기">
  <span aria-hidden="true">&times;</span>
</button>
{% endexample %}
