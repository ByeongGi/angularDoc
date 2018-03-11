---
title: Template & Data Binding
layout: post
author: ByeongGiKim
permalink: /template-&-data-binding/
source-id: 1wY7qJIreVwtJlAFo5YBmmnwGKV7dRGOw-0eBJannNfQ
published: true
---
1. [Displaying Data](https://angular.io/guide/displaying-data)

	*ngFor

	*ngIf

	

2. [Template Syntax](https://angular.io/guide/template-syntax)

    1. [HTML in templates](https://angular.io/guide/template-syntax#html-in-templates)

    2. [Interpolation ( ](https://angular.io/guide/template-syntax#interpolation----)[{﻿{...}}](https://angular.io/guide/template-syntax#interpolation----)[ )](https://angular.io/guide/template-syntax#interpolation----)

    3. [Template expressions](https://angular.io/guide/template-syntax#template-expressions)

        1. [Expression context](https://angular.io/guide/template-syntax#expression-context)

        2. [Expression guidelines](https://angular.io/guide/template-syntax#expression-guidelines)

    4. [Template statements(템플릿 선언)](https://angular.io/guide/template-syntax#template-statements)

        3. [Statement context[선언 영역]](https://angular.io/guide/template-syntax#statement-context)

선언 영역은 일반적으로 컴포넌트 인스턴스이다.

<button (click)="deleteHero()">Delete hero</button>

컴포넌트의 deleteHero 라는 메소드를 참조하고 있다.선언 영역은 템플릿 자신의 영역에 있는 속성을 참고 할수도 있다.

<button (click)="onSave($event)">Save</button>

<button *ngFor="let hero of heroes" (click)="deleteHero(hero)">{{hero.name}}</button>

<form #heroForm (ngSubmit)="onSubmit(heroForm)"> ... </form>

* $event  현재 엘리멘트의 이벤트를 넘겨줌

* 템플릿 태그의 참조값(#heroForm)을 onSubmit 메서드의 인자로 넘길수 있다.



        4. [Statement guidelines](https://angular.io/guide/template-syntax#statement-guidelines)

* 템플릿 표현식은 복잡한 템플릿 선언을 쓰는것을 피하라. 한 메서드 또는 간단한 메소드 할당은 일반적이다.

* 템플릿 표현식에 side-effect를 일으키는 복잡한 수식은 쓰지마라.

    5. [Binding syntax: An overview](https://angular.io/guide/template-syntax#binding-syntax-an-overview)

* One-way : Interpolation, Property, Attribute, Class, Style

			{{expression}}

[target]="expression"

bind-target="expression"

* One-way : Event

			(target)="statement"

on-target="statement"

* Two-way : 

			[(target)]="expression"

bindon-target="expression"

        5. [A new mental model](https://angular.io/guide/template-syntax#a-new-mental-model)

        6. [HTML attribute vs. DOM property](https://angular.io/guide/template-syntax#html-attribute-vs-dom-property)

        7. [Binding targets](https://angular.io/guide/template-syntax#binding-targets)

    6. [Property binding ( ](https://angular.io/guide/template-syntax#property-binding--property-)[[property]](https://angular.io/guide/template-syntax#property-binding--property-)[)](https://angular.io/guide/template-syntax#property-binding--property-)

        8. [One-way ](https://angular.io/guide/template-syntax#one-way-in)*[i*n](https://angular.io/guide/template-syntax#one-way-in)

        9. [Binding target](https://angular.io/guide/template-syntax#binding-target)

        10. [Avoid side effects](https://angular.io/guide/template-syntax#avoid-side-effects)

        11. [Return the proper type](https://angular.io/guide/template-syntax#return-the-proper-type)

        12. [Remember the brackets](https://angular.io/guide/template-syntax#remember-the-brackets)

        13. [One-time string initialization](https://angular.io/guide/template-syntax#one-time-string-initialization)

        14. [Property binding or interpolation?](https://angular.io/guide/template-syntax#property-binding-or-interpolation)

    7. [Attribute, class, and style bindings](https://angular.io/guide/template-syntax#attribute-class-and-style-bindings)

        15. [Attribute binding](https://angular.io/guide/template-syntax#attribute-binding)

        16. [Class binding](https://angular.io/guide/template-syntax#class-binding)

        17. [Style binding](https://angular.io/guide/template-syntax#style-binding)

    8. [Event binding ( ](https://angular.io/guide/template-syntax#event-binding---event-)[(event)](https://angular.io/guide/template-syntax#event-binding---event-)[ )](https://angular.io/guide/template-syntax#event-binding---event-)

        18. [Target event](https://angular.io/guide/template-syntax#target-event)

        19. *[$even*t](https://angular.io/guide/template-syntax#event-and-event-handling-statements)[ and event handling statements](https://angular.io/guide/template-syntax#event-and-event-handling-statements)

        20. [Custom events with ](https://angular.io/guide/template-syntax#custom-events-with-eventemitter)[EventEmitter](https://angular.io/guide/template-syntax#custom-events-with-eventemitter)

        21. [Template statements have side effects](https://angular.io/guide/template-syntax#template-statements-have-side-effects)

    9. [Two-way binding ( ](https://angular.io/guide/template-syntax#two-way-binding---)[[(...)]](https://angular.io/guide/template-syntax#two-way-binding---)[ )](https://angular.io/guide/template-syntax#two-way-binding---)

    10. [Built-in directives](https://angular.io/guide/template-syntax#built-in-directives)

    11. [Built-in ](https://angular.io/guide/template-syntax#built-in-attribute-directives)*[attribut*e](https://angular.io/guide/template-syntax#built-in-attribute-directives)[ directives](https://angular.io/guide/template-syntax#built-in-attribute-directives)

        22. [NgClass](https://angular.io/guide/template-syntax#ngclass)

        23. [NgStyle](https://angular.io/guide/template-syntax#ngstyle)

        24. [NgModel - Two-way binding to form elements with ](https://angular.io/guide/template-syntax#ngmodel---two-way-binding-to-form-elements-with-ngmodel)[[(ngModel)]](https://angular.io/guide/template-syntax#ngmodel---two-way-binding-to-form-elements-with-ngmodel)

    12. [Built-in ](https://angular.io/guide/template-syntax#built-in-structural-directives)*[structura*l](https://angular.io/guide/template-syntax#built-in-structural-directives)[ directives](https://angular.io/guide/template-syntax#built-in-structural-directives)

        25. [NgIf](https://angular.io/guide/template-syntax#ngif)

        26. [NgForOf](https://angular.io/guide/template-syntax#ngforof)

        27. [Template input variables](https://angular.io/guide/template-syntax#template-input-variables)

        28. [The ](https://angular.io/guide/template-syntax#the-ngswitch-directives)*[NgSwitc*h](https://angular.io/guide/template-syntax#the-ngswitch-directives)[ directives](https://angular.io/guide/template-syntax#the-ngswitch-directives)

    13. [Template reference variables ( ](https://angular.io/guide/template-syntax#template-reference-variables--var-)[#var](https://angular.io/guide/template-syntax#template-reference-variables--var-)[ )](https://angular.io/guide/template-syntax#template-reference-variables--var-)

    14. [Input and Output properties](https://angular.io/guide/template-syntax#input-and-output-properties)

        29. [Binding to a different component](https://angular.io/guide/template-syntax#binding-to-a-different-component)

        30. [Declaring Input and Output properties](https://angular.io/guide/template-syntax#declaring-input-and-output-properties)

        31. [Input or output?](https://angular.io/guide/template-syntax#input-or-output)

        32. [Aliasing input/output properties](https://angular.io/guide/template-syntax#aliasing-io)

    15. [Template expression operators](https://angular.io/guide/template-syntax#template-expression-operators)

        33. [The pipe operator ( ](https://angular.io/guide/template-syntax#the-pipe-operator---)[| )](https://angular.io/guide/template-syntax#the-pipe-operator---)

        34. [The safe navigation operator ( ](https://angular.io/guide/template-syntax#the-safe-navigation-operator----and-null-property-paths)[?.](https://angular.io/guide/template-syntax#the-safe-navigation-operator----and-null-property-paths)[ ) and null property paths](https://angular.io/guide/template-syntax#the-safe-navigation-operator----and-null-property-paths)

        35. [The non-null assertion operator ( ](https://angular.io/guide/template-syntax#the-non-null-assertion-operator---)[! )](https://angular.io/guide/template-syntax#the-non-null-assertion-operator---)

    16. [The ](https://angular.io/guide/template-syntax#the-any-type-cast-function-any-expression-)[$any](https://angular.io/guide/template-syntax#the-any-type-cast-function-any-expression-)[ type cast function (](https://angular.io/guide/template-syntax#the-any-type-cast-function-any-expression-)[$any( <expression> )](https://angular.io/guide/template-syntax#the-any-type-cast-function-any-expression-)[)](https://angular.io/guide/template-syntax#the-any-type-cast-function-any-expression-)

    17. [Summary](https://angular.io/guide/template-syntax#summary)

	inerpolation 표현식 안에서 연산과 함수 호출이 가능하다.

	<p>The sum of 1 + 1 is {{1 + 1 + getVal() }}</p> 

	{{}} 안에서 많은 연산을 하지 않도록 주의한다. (|, $ 미지원 )

3. [Lifecycle Hooks](https://angular.io/guide/lifecycle-hooks)

4. [Component Interaction](https://angular.io/guide/component-interaction)

5. [Component Styles](https://angular.io/guide/component-styles)

6. [Dynamic Components](https://angular.io/guide/dynamic-component-loader)

7. [Attribute Directives](https://angular.io/guide/attribute-directives)

8. [Structural Directives](https://angular.io/guide/structural-directives)

9. [Pipes](https://angular.io/guide/pipes)

10. [Animations](https://angular.io/guide/animations)

