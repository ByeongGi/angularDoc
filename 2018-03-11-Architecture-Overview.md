---
title: Architecture Overview
layout: post
author: kimchristian3426
permalink: /architecture-overview/
source-id: 15s39Wxz2nnyuR9JfqTorAb06UFYbaWWvUsyfJypUGTA
published: true
---
앵귤러 개괄

1. [Architecture Overview](https://angular.io/guide/architecture#architecture-overview)

	

2. [Modules](https://angular.io/guide/architecture#modules)

	@NgModule

declarations - 이 모듈에 view 클래스(컴포넌트 , 디렉티브 그리고 파이프 라인)들을 포함시킨다.	imports -  오로지 선언만 컴포넌트 , 디렉티브 그리고 파이프 라인들을 쓸수 있습니다.

exports - 외부 모듈에서 모듈에서 선언된 요소들을 사용할수 있습니다.	providers - 서비스 객체를 생성하여 글로벌 범위에서 사용할수 있게 합니다. 	bootstrap - 메인 어플리케이션 실행시 사용할 컴포넌트를 지정한다.

3. [NgModules vs. JavaScript modules](https://angular.io/guide/architecture#ngmodules-vs-javascript-modules)

4. [Angular libraries](https://angular.io/guide/architecture#angular-libraries)

5. [Components](https://angular.io/guide/architecture#components)

	컴포넌트는 view 호출된 부분을 제어합니다.

6. [Templates](https://angular.io/guide/architecture#templates)

	컴포넌트에서 사용할 HTML 형식의 View를 정의하는것이다.

7. [Metadata](https://angular.io/guide/architecture#metadata)

	메 타데이터는 해당 클래스를 어떻게 처리할지 지정합니다.

8. [Data binding](https://angular.io/guide/architecture#data-binding)

	데이터 삽입

{{hero.name}} *[interpolatio*n](https://angular.io/guide/displaying-data#interpolation) 은 hero.name 의 속성의 값을 나타냅니다.

	속성 바인딩

[hero] 속성 바인딩은 값을 전달합니다.

              이벤트 바인딩

               (cilck) 컴포넌트의 메서드와 이벤트를 바인딩 시킨다.

9. [Directives](https://angular.io/guide/architecture#directives)

	아래의 예제는 구조적인 디렉티브

	<li *[ngFor](https://angular.io/api/common/NgForOf)="let hero of heroes"></li>	<app-hero-detail *[ngIf](https://angular.io/api/common/NgIf)="selectedHero"></app-hero-detail>

10. [Services](https://angular.io/guide/architecture#services)

	서비스는 어플리케이션에서 필요한 넓은 범주로 어떤 값, 함수 또는 요소들이다.

11. Dependency injection

	가장 많이 쓰는 DI 는 컴포넌트에게 서비스 객체를 주입하는 것이다.

12. [Wrap up](https://angular.io/guide/architecture#wrap-up)

