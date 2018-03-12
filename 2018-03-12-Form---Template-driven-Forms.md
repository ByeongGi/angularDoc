---
title: Form  -Template-driven Forms
layout: post
author: kimchristian3426
permalink: /form---template-driven-forms/
source-id: 1UAh0k7UISaj7mciSkb9GtM1cD7pxvjrmrS56X2_r-7E
published: true
---
1. ## Forms

Forms are the mainstay of business applications. You use forms to log in, submit a help request, place an order, book a flight, schedule a meeting, and perform countless other data-entry tasks.

Forms은 비지니스 어플리케이션들의 중심이다. 당신은 forms을 로그인, 도움 요청을 보내거나, 주문을 하거나 , 비행기를 예약하거나, 미팅을 예약하고, 셀수없이 많은 데이터 입력 작업들을 수행한다.

In developing a form, it's important to create a data-entry experience that guides the user efficiently and effectively through the workflow.

form을 개발하는데 있어서  , 가장 중요한것은 유저가 워크 플로우를 통해서 효과적으로, 효율적으로  되게 안내하는 데이터 입력 경험을 만들어내는 것이다.

Developing forms requires design skills (which are out of scope for this page), as well as framework support for *two-way data binding, change tracking, validation, and error handling*, which you'll learn about on this page.

forms을 개발하는것은 디자인 스킬이 필요로 한다 (이 페이지 영역 외의 문제인), 또한 *two-way data binding, 변화 추척, 검증 , 그리고 에러 핸들링에 대한 프레임워크의 지원도 ,  이것에 대해서 이 페이지에서 배울 것들이다.*

This page shows you how to build a simple form from scratch. Along the way you'll learn how to:

이 페이지는 어떻게 당신이 스케치로부터 폼을 형성하지를 보여준다.아래 와 같은 것을 포함아여 어떻게 해야할지 배울것이다:

* Build an Angular form with a component and template.( 컴포넌트와 템플릿을 가진 폼을 생성하라)

* Use [ngModel](https://angular.io/api/forms/NgModel) to create two-way data bindings for reading and writing input-control values.( 입력- 제어 값을 읽고 쓰는 양방향 방인딩을 만드는 [ngModel](https://angular.io/api/forms/NgModel) 사용하라.

* Track state changes and the validity of form controls.(상태 변화와 폼 제어의 검증을 추적하라)

* Provide visual feedback using special CSS classes that track the state of the controls.( 상태 변화를 추적하는 특별한 Css 클래스들을 사용하여 시각적인 피드백을 주라)

* Display validation errors to users and enable/disable form controls.( 유저에게 검증 에러를 보여주고 폼 컨트를 사용/불능하도록 하라)

* Share information across HTML elements using template reference variables.(템플릿 레퍼런스 변수들을 사용한 HTML 엘림멘트들로부터 정보를 공유하라)

You can run the [live example](https://angular.io/generated/live-examples/forms/stackblitz.html) / [download example](https://angular.io/generated/zips/forms/forms.zip) in Stackblitz and download the code from there.

2. ### Template-driven forms

3. ### [Setup](https://angular.io/guide/forms#setup)

4. ### [Create the Hero model class](https://angular.io/guide/forms#create-the-hero-model-class)

5. ### [Create a form component](https://angular.io/guide/forms#create-a-form-component)

6. ### [Revise ](https://angular.io/guide/forms#revise-appmodulets)*[app.module.t*s](https://angular.io/guide/forms#revise-appmodulets)

7. ### [Revise ](https://angular.io/guide/forms#revise-appcomponenthtml)*[app.component.htm*l](https://angular.io/guide/forms#revise-appcomponenthtml)

8. ### [Create an initial HTML form template](https://angular.io/guide/forms#create-an-initial-html-form-template)

9. ### [Add powers with ](https://angular.io/guide/forms#add-powers-with-ngfor)*[*ngFo*r](https://angular.io/guide/forms#add-powers-with-ngfor)

10. ### [Two-way data binding with ](https://angular.io/guide/forms#two-way-data-binding-with-ngmodel)*[ngMode*l](https://angular.io/guide/forms#two-way-data-binding-with-ngmodel)

11. #### [The ](https://angular.io/guide/forms#the-ngform-directive)*[NgFor*m](https://angular.io/guide/forms#the-ngform-directive)[ directive](https://angular.io/guide/forms#the-ngform-directive)

12. ### [Track control state and validity with ](https://angular.io/guide/forms#track-control-state-and-validity-with-ngmodel)*[ngMode*l](https://angular.io/guide/forms#track-control-state-and-validity-with-ngmodel)

13. ### [Add custom CSS for visual feedback](https://angular.io/guide/forms#add-custom-css-for-visual-feedback)

14. ### [Show and hide validation error messages](https://angular.io/guide/forms#show-and-hide-validation-error-messages)

15. ### [Submit the form with ](https://angular.io/guide/forms#submit-the-form-with-ngsubmit)*[ngSubmi*t](https://angular.io/guide/forms#submit-the-form-with-ngsubmit)

16. ### [Toggle two form regions (extra credit)](https://angular.io/guide/forms#toggle-two-form-regions-extra-credit)

17. ### [Summary](https://angular.io/guide/forms#summary)

