---
title: NgModule - JS Modules vs NgModules
layout: post
author: kimchristian3426
permalink: /ngmodule---js-modules-vs-ngmodules/
source-id: 1SKNHXu_cbPREB9LrXqBWqhd4Df7IVcz3uxTzL-ARWqo
published: true
---
## JavaScript Modules vs. NgModules

#### ### Prerequisites

A basic understanding of [JavaScript/ECMAScript modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/).

[JavaScript/ECMAScript modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/)의 기본적인 이해

* * *


JavaScript and Angular use modules to organize code, and though they organize it differently, Angular apps rely on both. 자바스크립트 그리고 앵귤러를 코드를 조직화 하기 위해서 사용하고 ,  비록 이것이 다르더라도, 앵귤러 앱은 각가에 의존한다.

### JavaScript modules

In JavaScript, modules are individual files with JavaScript code in them. To make what's in them available, you write an export statement, usually after the relevant code, like this:

자바 스크립에서 , 모듈들은 그모듈에 있는 자바 코드들의 개개의 파일들이다. 모듈에 접근하게 하도록 만들기 위해서, 우리는 export 선언을 작성하고, 보통 적절한 코드 후에, 이것과 같이:

<pre>
export class AppComponent { ... }
</pre>

Then, when you need that file's code in another file, you import it like this:

그리고나, 우리가 또다른 파일에서 이 파일의 코드를 필요로 할때 , 우리는 이것과 같이 import 한다.

<pre>
import { AppComponent } from './app.component';
</pre>

JavaScript modules help you namespace, preventing accidental global variables.

자바 스크립트 모듈들은 당신의 우발적인 전역 변수들을 마아서, 당신의 namespace 에 도움을 준다.

### [NgModules](https://angular.io/guide/ngmodule-vs-jsmodule#ngmodules)

NgModules are classes decorated with @[NgModule](https://angular.io/api/core/NgModule). The @[NgModule](https://angular.io/api/core/NgModule)decorator's imports array tells Angular what other NgModules the current module needs. The modules in the imports array are different than JavaScript modules because they are NgModules rather than regular JavaScript modules. Classes with an @[NgModule](https://angular.io/api/core/NgModule)decorator are by convention kept in their own files, but what makes them an [NgModule](https://angular.io/api/core/NgModule) isn’t being in their own file, like JavaScript modules; it’s the presence of @[NgModule](https://angular.io/api/core/NgModule) and its metadata.

NgModul들은 @[NgModule](https://angular.io/api/core/NgModule) 로 선언된 클래스들이다. @[NgModule](https://angular.io/api/core/NgModule) 데코레이터의 imports 배열은 앵귤러가 어떤 또다른 NgModule들이 현재 모듈이 필요하지를 말해준다. imports 배열은 JavaScript modules 과는 다르다 왜냐하면 일바적인 자바스크립트 모듈들보다는 NgModule이다.

@[NgModule](https://angular.io/api/core/NgModule)decorator를 포함하고 있는 클래스들은 관습적으로 그들의 파일에서 유지되지만 , 자바 스크립 모듈같이, [NgModule](https://angular.io/api/core/NgModule) 은 그들의 파일안에 포함되어 있는 것이 아니다; @[NgModule](https://angular.io/api/core/NgModule) 의 존재이고 이것은 메타데이터이다.

The AppModule generated from the Angular CLI demonstrates both kinds of modules in action:  Angular CLI 로부터 생성된 AppModule은 각각 종류의 모듈들에 동작에 대한 것을 나타낸다.

<pre>
/* These are JavaScript import statements. Angular doesn't know anything about these. */import {[ BrowserModule](https://angular.io/api/platform-browser/BrowserModule) } from '@angular/platform-browser';import {[ NgModule](https://angular.io/api/core/NgModule) } from '@angular/core';import { AppComponent } from './app.component';/* The @[NgModule](https://angular.io/api/core/NgModule) decorator lets Angular know that this is an NgModule. */@[NgModule](https://angular.io/api/core/NgModule)({  declarations: [    AppComponent  ],  imports: [     /* These are[ NgModule](https://angular.io/api/core/NgModule) imports. */   [ BrowserModule](https://angular.io/api/platform-browser/BrowserModule)  ],  providers: [],  bootstrap: [AppComponent]})export class AppModule { }
</pre>

The NgModule classes differ from JavaScript module in the following key ways:

NgModule 클래스들은 JavaScript module은 다음과 같은 핵심 사항에서 다르다.

* An NgModule bounds [declarable classes](https://angular.io/guide/ngmodule-faq#q-declarable) only. Declarables are the only classes that matter to the [Angular compiler](https://angular.io/guide/ngmodule-faq#q-angular-compiler). NgModule 은 [declarable classes](https://angular.io/guide/ngmodule-faq#q-declarable)를 바인딩한다.  Declarable들은 [Angular compiler](https://angular.io/guide/ngmodule-faq#q-angular-compiler)에서 중요한 클래스이다.

* Instead of defining all member classes in one giant file as in a JavaScript module, you list the module's classes in the @[NgModule.declarations](https://angular.io/api/core/NgModule#declarations) list. JavaScript module 안에 있는 것과 같이 하나의 거대한 모든 멤버 클래스들을 선언하는것 대신에, 우리는 @[NgModule.declarations](https://angular.io/api/core/NgModule#declarations) 목록에 있는 모듈의 클래스들로 리스트화한다.

* An NgModule can only export the [declarable classes](https://angular.io/guide/ngmodule-faq#q-declarable) it owns or imports from other modules. It doesn't declare or export any other kind of class. NgModule 오로지 [declarable classes](https://angular.io/guide/ngmodule-faq#q-declarable) 들 자체만 export 하거나 다른 모듈에 import 한다. 이것은 또다른 종류에 클래스에 export 하거나 선언하지 않는다.

* Unlike JavaScript modules, an NgModule can extend the *entire*application with services by adding providers to the @[NgModule.providers](https://angular.io/api/core/NgModule#providers) list. JavaScript modules 과  다르게 NgModule은 @[NgModule.providers](https://angular.io/api/core/NgModule#providers) 목록에서 추가된 서비스를 가진 전체 어플케이션으로 확장할수 있다.

### More on NgModules

For more information on NgModules, see:

* [Bootstrapping](https://angular.io/guide/bootstrapping).

* [Frequently used modules](https://angular.io/guide/frequent-ngmodules).

* [Providers](https://angular.io/guide/providers).

