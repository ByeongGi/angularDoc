---
title: Bootstrapping
layout: post
author: kimchristian3426
permalink: /bootstrapping/
source-id: 16kJ06tvEsmjDHr3TIFhY-Zz1yWrTOb2fgDE_qItIlLk
published: true
---
## bootstrapping

### Prerequisites

A basic understanding of the following(다음과 같은 기본적인 이해): 

* [JavaScript Modules vs. NgModules](https://angular.io/guide/ngmodule-vs-jsmodule).

* * *


An NgModule describes how the application parts fit together. Every application has at least one Angular module, the *root *module that you bootstrap to launch the application. By convention, it is usually called AppModule.

If you use the CLI to generate an app, the default AppModule is as follows:

NgModule 어떻게 어플리케이션의 부분들이 어울릴지를 설명하는 것입니다. 모든 어플케이션은 최소한 Angular module인 어플리케이션 실행하기 위해서 로딩하는 root module 을  가지고 있습니다. 언급한것처럼, 보통 AppModule 이라고 합니다.

If you use the CLI to generate an app, the default AppModule is as follows:

만약 당신이 앱을 생성하기 위해서 CLI 를 사용하다면, 기본 AppModule 을 다음과 같습니다:

<pre>
/* JavaScript imports */import {[ BrowserModule](https://angular.io/api/platform-browser/BrowserModule) } from '@angular/platform-browser';import {[ NgModule](https://angular.io/api/core/NgModule) } from '@angular/core';import {[ FormsModule](https://angular.io/api/forms/FormsModule) } from '@angular/forms';import {[ HttpModule](https://angular.io/api/http/HttpModule) } from '@angular/http';import { AppComponent } from './app.component';/* the AppModule class with the @[NgModule](https://angular.io/api/core/NgModule) decorator */@[NgModule](https://angular.io/api/core/NgModule)({  declarations: [    AppComponent  ],  imports: [   [ BrowserModule](https://angular.io/api/platform-browser/BrowserModule),   [ FormsModule](https://angular.io/api/forms/FormsModule),   [ HttpModule](https://angular.io/api/http/HttpModule)  ],  providers: [],  bootstrap: [AppComponent]})export class AppModule { }
</pre>

After the import statements is a class with the @[NgModule](https://angular.io/api/core/NgModule) [decorator](https://angular.io/guide/glossary#decorator).

The @[NgModule](https://angular.io/api/core/NgModule) decorator identifies AppModule as an [NgModule](https://angular.io/api/core/NgModule) class. @[NgModule](https://angular.io/api/core/NgModule) takes a metadata object that tells Angular how to compile and launch the application.

import 선언 후에는 @[NgModule](https://angular.io/api/core/NgModule) [decorator](https://angular.io/guide/glossary#decorator) 을 가진 클래스 일것입니다.

@[NgModule](https://angular.io/api/core/NgModule) decorator 는 [NgModule](https://angular.io/api/core/NgModule)  class로써 AppModule을 인식합니다.  @[NgModule](https://angular.io/api/core/NgModule) 은 앵귤러가 어플리케이션을 어떻게 컴파일하고 실행될지를 나타내는 메타데이터 객체를 가집니다.

* *declarations*—this application's lone component.(이 어플리케이션만의 단독 컴포넌트)

* *imports*—import [BrowserModule](https://angular.io/api/platform-browser/BrowserModule) to have browser specific services such as DOM rendering, sanitization, and location.(DOM 렌더링, 검사 그리고 위치 등 과 같은 특정 브라우저 서비스를 가진 [BrowserModule](https://angular.io/api/platform-browser/BrowserModule) 을 불러온다.)

* *providers*—the service providers(서비스 제공자).

* *bootstrap*—the *root* component that Angular creates and inserts into the index.html host web page.(앵귤러는 생성하고index.html 삽인된느 root 컴포넌트는 웹 페이지를 관리한다.)

The default CLI application only has one component, AppComponent, so it is in both the declarations and the bootstrap arrays. 기본적인 CLI 어플리케이션 컴포넌트는 AppComponent 를 가지고 , declarations 그리고 bootstrap  의 배열도 있다.

### The declarations array

The module's declarations array tells Angular which components belong to that module. As you create more components, add them to declarations.

모듈의 declarations 배열은 이 모듈에 포함된 컴포넌트들을 앵귤러에게 전달하는 것이다. 만약 더 많은 모듈을 만들 다면 , declarations 에 추가하라.

You must declare every component in exactly one [NgModule](https://angular.io/api/core/NgModule) class. If you use a component without declaring it, Angular returns an error message.

만약 당신이 모든 컴포넌트들을 정확하게 하나의 [NgModule](https://angular.io/api/core/NgModule) 클래스를 추가해야한다. 만약 당신이 이것을 선언없이 사용한다면 앵귤러에서 에러 메세지가 리턴한다.

The declarations array only takes declarables. Declarables are components, [directives](https://angular.io/guide/attribute-directives) and [pipes](https://angular.io/guide/pipes). All of a module's declarables must be in the declarations array. Declarables must belong to exactly one module. The compiler emits an error if you try to declare the same class in more than one module. declarations 배열은 오로지 선언들을 가진다. 선언들은 components, [directives](https://angular.io/guide/attribute-directives)  그리고  [pipes](https://angular.io/guide/pipes) 이다. 모든 모듈들의 선언은 declarations 배열 안에 있어야 한다. 선언들은 정확하게 하나의 모듈에 포함되어야 한다.

These declared classes are visible within the module but invisible to components in a different module unless they are exported from this module and the other module imports this one.

그러한 선언된 클래스들은 모듈안에서 보일수 있지만 이 모듈에서 export 시키거나 또다른 모듈에서 import 하는것 없이는 이 모듈에서 다른 모듈로 보여질수 없다.

An example of what goes into a declarations array follows:

declarations 배열이 어떻게 되어야 하는 예는 다음과 같다:

<pre>
declarations: [  YourComponent,  YourPipe,  YourDirective],
</pre>

A declarable can only belong to one module, so only declare it in one @[NgModule](https://angular.io/api/core/NgModule). When you need it elsewhere, import the module that has the declarable you need in it.

선언할수있는 것은 하나의 모듈에 포함되고 , 그래서 오로지 @[NgModule](https://angular.io/api/core/NgModule) 이것에서만 선언된다. 만약 당신이 어디에서나 필요하다면, 당신이 필요한 선언들을 가진 모듈을 import 해라

Only @[NgModule](https://angular.io/api/core/NgModule) references go in the imports array.

오직 @[NgModule](https://angular.io/api/core/NgModule)  참조들은 imports 배열로 전달된다.

### [Using directives with ](https://angular.io/guide/bootstrapping#using-directives-with-ngmodule)[@](https://angular.io/guide/bootstrapping#using-directives-with-ngmodule)[NgModule(@NgModule 과 디렉티브 사용하기)](https://angular.io/api/core/NgModule)

Use the declarations array for directives. To use a directive, component, or pipe in a module, you must do a few things: 

directives를 declarations 배열로 사용하라. 모듈 안의  directive, component, 또는 pipe 를 사용하기 위해서 당신은 몇가지를 해야만 한다.

1. Export it from the file where you wrote it. 당신이 작성한 파일에서 Export 해라.

2. Import it into the appropriate module. 적절한 모듈에 이것을 Import 해라.

3. Declare it in the @[NgModule](https://angular.io/api/core/NgModule) declarations array. @[NgModule](https://angular.io/api/core/NgModule) declarations array 안에 선언하라.

Those three steps look like the following. In the file where you create your directive, export it. The following example, named ItemDirective is the default directive structure that the CLI generates in its own file, item.directive.ts:

3가지 단계는 다음과 같다. 당신의 디렉티브를 만든 곳에 파일안에서 , 디렉티브를 export 한다. 다음 예에는, item.directive.ts 파일에서 안에서 CLI 가 생성하는  ItemDirective로 이름이 붙여지는 것은  기본적인 디렉티브의 구조이다.

<pre>
import {[ Directive](https://angular.io/api/core/Directive) } from '@angular/core';@[Directive](https://angular.io/api/core/Directive)({  selector: '[appItem]'})export class ItemDirective {// code goes here  constructor() { }}
</pre>

The key point here is that you have to export it so you can import it elsewhere. Next, import it into the NgModule, in this example app.module.ts, with a JavaScript import statement:

여기서 핵심은 이 디렉티브를 어는 곳이나 import 가 가능하도록 export 하는것이다. 다음으로는, 이것을 이 예시에서는 app.module.ts에서 JavaScript import 선언을 하여  NgModule 에 import 한다.

<pre>
import { ItemDirective } from './item.directive';
</pre>

And in the same file, add it to the @[NgModule](https://angular.io/api/core/NgModule) declarations array:

그리고 같은 파일안에서  @NgModule declarations array  에 디렉티브를 선언한다.

<pre>
declarations: [  AppComponent,  ItemDirective],
</pre>

Now you could use your ItemDirective in a component. This example uses AppModule, but you'd do it the same way for a feature module. For more about directives, see [Attribute Directives](https://angular.io/guide/attribute-directives) and [Structural Directives](https://angular.io/guide/structural-directives). You'd also use the same technique for [pipes](https://angular.io/guide/pipes) and components.

Remember, components, directives, and pipes belong to one module only. You only need to declare them once in your app because you share them by importing the necessary modules. This saves you time and helps keep your app lean.

지금 당신이 컴포넌트 안에서 당신의 ItemDirective 를 사용할수 있다. 이 예시는 AppModule 을 사용하지만, 몇몇 다른 모듈에서도 같은 방법으로 해야만 한다. 더 많은 디렉티브들을 보고 싶다면, 속성 디렉티브들와 구조적 디렉티브를을 보라. 당신은 또한  [pipes](https://angular.io/guide/pipes) 그리고 components 대해서 같은 기술로 사용해야만 한다.

기억하나,  components, directives, 그리고 pipes 오로지 한개의 모듈에 포함된다. 당신은 필수적인 모듈들을 포함함으로써 그것들을 공유하기 떄문에 앱에서 그것들을 선언해야만 한다. 이것은 당신의 시간을 줄여주고 앱이 유지되는데 도움을 준다.

### [The ](https://angular.io/guide/bootstrapping#the-imports-array)[imports](https://angular.io/guide/bootstrapping#the-imports-array)[ array](https://angular.io/guide/bootstrapping#the-imports-array)

The module's imports array appears exclusively in the @[NgModule](https://angular.io/api/core/NgModule) metadata object. It tells Angular about other NgModules that this particular module needs to function properly.

This list of modules are those that export components, directives, or pipes that the component templates in this module reference. In this case, the component is AppComponent, which references components, directives, or pipes in [BrowserModule](https://angular.io/api/platform-browser/BrowserModule), [FormsModule](https://angular.io/api/forms/FormsModule), or [HttpModule](https://angular.io/api/http/HttpModule). A component template can reference another component, directive, or pipe when the referenced class is declared in this module or the class was imported from another module.

You don't have any services to provide yet. But you will create some before long and you may chose to provide many of them here.

### The providers array

The providers array is where you list the services the app needs. When you list services here, they are available app-wide. You can scope them when using feature modules and lazy loading. For more information, see [Providers](https://angular.io/guide/providers).

### [The ](https://angular.io/guide/bootstrapping#the-bootstrap-array)[bootstrap](https://angular.io/guide/bootstrapping#the-bootstrap-array)[ array](https://angular.io/guide/bootstrapping#the-bootstrap-array)

The application launches by bootstrapping the root AppModule, which is also referred to as an entryComponent. Among other things, the bootstrapping process creates the component(s) listed in the bootstrap array and inserts each one into the browser DOM.

Each bootstrapped component is the base of its own tree of components. Inserting a bootstrapped component usually triggers a cascade of component creations that fill out that tree.

While you can put more than one component tree on a host web page, most applications have only one component tree and bootstrap a single root component.

This one root component is usually called AppComponent and is in the root module's bootstrap array.

### [More about Angular Modules](https://angular.io/guide/bootstrapping#more-about-angular-modules)

For more on NgModules you're likely to see frequently in apps, see [Frequently Used Modules](https://angular.io/guide/bootstrapping#).

