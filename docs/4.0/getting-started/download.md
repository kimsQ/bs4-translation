---
layout: docs
title: 다운로드
description: 부트스트랩을 다운로드하여 컴파일 된 CSS 및 JavaScript, 소스 코드를 얻거나 npm, RubyGems 등과 같은 자주 사용하는 패키지 매니저로 프로젝트에 포함 시키십시오.
group: getting-started
toc: true
---



## 컴파일된 CSS 와 JS

바로 사용할 수 있도록 컴파일된 **부트스트랩 v{{ site.current_version}}** 을 다운로드하여 쉽게 프로젝트에 추가할 수 있습니다. 여기에는 다음이 포함되어 있습니다.  :

- 컴파일 되고 축소 된 CSS 번들 (기본값, 그리드 전용 및 리부트 전용)
- 컴파일 되고 축소 된 JavaScript 플러그인

여기에는 문서, 소스 파일 또는 JavaScript 의존성(jQuery 및 Popper.js)이 포함되지 않습니다.

<a href="{{ site.download.dist }}" class="btn btn-bd-purple" onclick="ga('send', 'event', 'Getting started', 'Download', 'Download Bootstrap');">다운로드</a>

## 소스코드 파일

Sass 소스, JavaScript 및 문서 파일을 다운로드하여 자신만의 에셋 파이프 라인으로 부트스트랩을 컴파일 하십시오. 이 옵션을 사용하려면 다음과 같은 추가 도구가 필요합니다.

- CSS 컴파일을 위한 Sass 컴파일러 (Libsass 또는 Ruby Sass 지원).
- CSS vendor prefixing을 위한 [Autoprefixer](https://github.com/postcss/autoprefixer)

[빌드 툴]({{ site.baseurl }}/docs/{{ site.docs_version }}/getting-started/build-tools/#tooling-setup)이 필요하다면 부트스트랩과 그 문서를 개발하기 위해 포함되어 있지만, 그것들은 당신의 목적에 적합하지 않을 것입니다.

<a href="{{ site.download.source }}" class="btn btn-bd-purple" onclick="ga('send', 'event', 'Getting started', 'Download', 'Download source');">소스 다운로드</a>

## 부트스트랩 CDN

부트스트랩 CDN을 사용하여 다운로드를 건너 뛰면 컴파일 된 CSS와 JS의 캐시된 버전을 프로젝트에 전달할 수 있습니다.

{% highlight html %}
<link rel="stylesheet" href="{{ site.cdn.css }}" integrity="{{ site.cdn.css_hash }}" crossorigin="anonymous">
<script src="{{ site.cdn.js }}" integrity="{{ site.cdn.js_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

컴파일 된 자바 스크립트를 사용하는 경우 jQuery 및 Popper.js의 CDN 버전을 포함 시켜야합니다.

{% highlight html %}
<script src="{{ site.cdn.jquery }}" integrity="{{ site.cdn.jquery_hash }}" crossorigin="anonymous"></script>
<script src="{{ site.cdn.popper }}" integrity="{{ site.cdn.popper_hash }}" crossorigin="anonymous"></script>
{% endhighlight %}

## 패키지 매니저

Pull in Bootstrap's **source files** into nearly any project with some of the most popular package managers. No matter the package manager, Bootstrap will **require a Sass compiler and [Autoprefixer](https://github.com/postcss/autoprefixer)** for a setup that matches our official compiled versions.

### npm

Install Bootstrap in your Node.js powered apps with [the npm package](https://www.npmjs.com/package/bootstrap):

{% highlight sh %}
npm install bootstrap@{{ site.current_version }}
{% endhighlight %}

`require('bootstrap')` will load all of Bootstrap's jQuery plugins onto the jQuery object. The `bootstrap` module itself does not export anything. You can manually load Bootstrap's jQuery plugins individually by loading the `/js/*.js` files under the package's top-level directory.

Bootstrap's `package.json` contains some additional metadata under the following keys:

- `sass` - path to Bootstrap's main [Sass](http://sass-lang.com/) source file
- `style` - path to Bootstrap's non-minified CSS that's been precompiled using the default settings (no customization)

### RubyGems

Install Bootstrap in your Ruby apps using [Bundler](https://bundler.io/) (**recommended**) and [RubyGems](https://rubygems.org/) by adding the following line to your [`Gemfile`](https://bundler.io/gemfile.html):

{% highlight ruby %}
gem 'bootstrap', '~> 4.0.0.beta'
{% endhighlight %}

Alternatively, if you're not using Bundler, you can install the gem by running this command:

{% highlight sh %}
gem install bootstrap -v 4.0.0.beta
{% endhighlight %}

[See the gem's README](https://github.com/twbs/bootstrap-rubygem/blob/master/README.md) for further details.

### Composer

You can also install and manage Bootstrap's Sass and JavaScript using [Composer](https://getcomposer.org/):

{% highlight sh %}
composer require twbs/bootstrap:{{ site.current_version }}
{% endhighlight %}

### NuGet

If you develop in .NET, you can also install and manage Bootstrap's [CSS](https://www.nuget.org/packages/bootstrap/) or [Sass](https://www.nuget.org/packages/bootstrap.sass/) and JavaScript using [NuGet](https://www.nuget.org/):

{% highlight powershell %}
Install-Package bootstrap -Pre
{% endhighlight %}

{% highlight powershell %}
Install-Package bootstrap.sass -Pre
{% endhighlight %}

The `-Pre` is required until Bootstrap v4 has a stable release.
