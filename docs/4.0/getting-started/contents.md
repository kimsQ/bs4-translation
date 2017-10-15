---
layout: docs
title: 컨텐츠
description: 미리 컴파일된 소스코드와 함께 부트스트랩에 포함 된 내용을 살펴보십시오. Bootstrap의 JavaScript 플러그인에는 jQuery가 필요하다는 것을 기억하십시오.
group: getting-started
toc: true
---



## 미리 컴파일 된 부트스트랩

다운로드가 완료되고, 압축을 풀면 다음과 같은 내용이 표시됩니다.

<!-- NOTE: This info is intentionally duplicated in the README. Copy any changes made here over to the README too. -->

{% highlight plaintext %}
bootstrap/
├── css/
│   ├── bootstrap.css
│   ├── bootstrap.css.map
│   ├── bootstrap.min.css
│   └── bootstrap.min.css.map
└── js/
    ├── bootstrap.js
    └── bootstrap.min.js
{% endhighlight %}


모든 웹 프로젝트에서 빠른 사용을 위한 미리 컴파일 된 부트스트랩의 가장 기본적인 형태입니다. 우리는 컴파일 된 CSS 및 JS (`bootstrap.*`) 뿐만 아니라 컴파일 되고 축소된(minified) CSS 및 JS (`bootstrap.min.*`) 도 제공 합니다. CSS [source maps](https://developers.google.com/web/tools/chrome-devtools/javascript/source-maps) (`bootstrap.*.map`)은 특정 브라우저의 개발자 도구에서 사용할 수 있습니다.

## 부트스트랩 소스코드

부트스트랩 소스코드 다운로드에는 미리 컴파일 된 CSS 및 JavaScript 에셋과 원본 Sass, JavaScript 및 설명서가 포함되어 있습니다. 보다 구체적으로, 다음과 같은 것을 포함합니다 :

{% highlight plaintext %}
bootstrap/
├── dist/
│   ├── css/
│   └── js/
├── docs/
│   └── examples/
├── js/
└── scss/
{% endhighlight %}

`scss/`와 `js/`는 CSS와 자바스크립트의 소스 코드 입니다. `dist/` 폴더는 위의 미리 컴파일 된 다운로드 섹션에 나열된 모든 것을 포함합니다. `docs/` 폴더에는 문서의 소스코드가  `examples/`에는 사용예제가 포함되어 있습니다. 그 밖의 다른 파일은 패키지, 라이센스 정보 및 개발을 지원합니다.
