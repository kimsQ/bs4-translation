---
layout: docs
title: 빌드툴
description: 부트스트랩에 포함 된 npm 스크립트를 사용하여 문서를 작성하고, 소스코드를 컴파일하고, 테스트를 실행하는 방법 등에 대해 배웁니다.
group: getting-started
toc: true
---



## 툴링 설정 (Tooling setup)

Bootstrap uses [NPM scripts](https://docs.npmjs.com/misc/scripts) for its build system. Our [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) includes convenient methods for working with the framework, including compiling code, running tests, and more.

To use our build system and run our documentation locally, you'll need a copy of Bootstrap's source files and Node. Follow these steps and you should be ready to rock:

1. [Download and install Node.js](https://nodejs.org/download/), which we use to manage our dependencies.
2. Navigate to the root `/bootstrap` directory and run `npm install` to install our local dependencies listed in [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json).
3. [Install Ruby][install-ruby], install [Bundler][gembundler] with `gem install bundler`, and finally run `bundle install`. This will install all Ruby dependencies, such as Jekyll and plugins.
  - **Windows users:** Read [this guide](https://jekyllrb.com/docs/windows/) to get Jekyll up and running without problems.

When completed, you'll be able to run the various commands provided from the command line.

[install-ruby]: https://www.ruby-lang.org/en/documentation/installation/
[gembundler]: https://bundler.io/

## NPM 스크립트 사용

Our [package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) includes the following commands and tasks:

| Task | Description |
| --- | --- |
| `npm test` | Run `npm test` to run tests locally and compile the CSS and JavaScript into `/dist`. **Uses [Sass](http://sass-lang.com/), [Autoprefixer][autoprefixer], and [UglifyJS](http://lisperator.net/uglifyjs/).** |
| `npm run dist` | `npm run dist` creates the `/dist` directory with compiled files. **Uses [Sass](http://sass-lang.com/), [Autoprefixer][autoprefixer], and [UglifyJS](http://lisperator.net/uglifyjs/).** |
| `npm run docs` | Builds and tests CSS, JavaScript, and other assets which are used when running the documentation locally via `npm run docs-serve`. |

## 오토프리픽서 (Autoprefixer)

Bootstrap uses [Autoprefixer][autoprefixer] (included in our build process) to automatically add vendor prefixes to some CSS properties at build time. Doing so saves us time and code by allowing us to write key parts of our CSS a single time while eliminating the need for vendor mixins like those found in v3.

We maintain the list of browsers supported through Autoprefixer in a separate file within our GitHub repository. See [/package.json]({{ site.repo }}/blob/v{{ site.current_version }}/package.json) for details.

## 로컬 문서 (Local documentation)

Running our documentation locally requires the use of Jekyll, a decently flexible static site generator that provides us: basic includes, Markdown-based files, templates, and more. Here's how to get it started:

1. Run through the [tooling setup](#tooling-setup) above to install Jekyll (the site builder) and other Ruby dependencies with `bundle install`.
2. From the root `/bootstrap` directory, run `npm run docs-serve` in the command line.
3. Open <http://localhost:9001> in your browser, and voilà.

Learn more about using Jekyll by reading its [documentation](https://jekyllrb.com/docs/home/).

## 문제해결

Should you encounter problems with installing dependencies, uninstall all previous dependency versions (global and local). Then, rerun `npm install`.

[autoprefixer]: https://github.com/postcss/autoprefixer
