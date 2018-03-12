---
title: NgModules - Types of Feature Modules
layout: post
author: kimchristian3426
permalink: /ngmodules---types-of-feature-modules/
source-id: 1oIg6_Z88nX_dLjeDpcOfbMnJsi6r0u8uA1_cZj5Sb0M
published: true
---
# **Types of Feature Modules**

#### **Prerequisites**

A basic understanding of the following concepts:

* [Feature Modules](https://github.com/angular/angular/blob/master/aio/content/guide/guide/feature-modules).

* [JavaScript Modules vs. NgModules](https://github.com/angular/angular/blob/master/aio/content/guide/guide/ngmodule-vs-jsmodule).

* [Frequently Used Modules](https://github.com/angular/angular/blob/master/aio/content/guide/guide/frequent-ngmodules).

* * *


There are five general categories of feature modules which tend to fall into the following groups:

* Domain feature modules.

* Routed feature modules.

* Routing modules.

* Service feature modules.

* Widget feature modules.

While the following guidelines describe the use of each type and their typical characteristics, in real world apps, you may see hybrids.

<table>
  <tr>
    <td>Feature Module</td>
    <td>Guidelines</td>
  </tr>
  <tr>
    <td>Domain</td>
    <td>Domain feature modules deliver a user experience dedicated to a particular application domain like editing a customer or placing an order.
They typically have a top component that acts as the feature root and private, supporting sub-components descend from it.
  </tr>
  <tr>
    <td>Routed</td>
    <td>Routed feature modules are domain feature modules whose top components are the targets of router navigation routes.
All lazy-loaded modules are routed feature modules by definition.
  </tr>
  <tr>
    <td>Routing</td>
    <td>A routing module provides routing configuration for another module and separates routing concerns from its companion module.
  </tr>
  <tr>
    <td>Service</td>
    <td>Service modules provide utility services such as data access and messaging. Ideally, they consist entirely of providers and have no declarations. Angular's `HttpClientModule` is a good example of a service module.
  </tr>
  <tr>
    <td>Widget</td>
    <td>A widget module makes components, directives, and pipes available to external modules. Many third-party UI component libraries are widget modules.
  </tr>
</table>


The following table summarizes the key characteristics of each feature module group.

<table>
  <tr>
    <td>Feature Module</td>
    <td>Declarations</td>
    <td>Providers</td>
    <td>Exports</td>
    <td>Imported by</td>
  </tr>
  <tr>
    <td>Domain</td>
    <td>Yes</td>
    <td>Rare</td>
    <td>Top component</td>
    <td>Feature, AppModule</td>
  </tr>
  <tr>
    <td>Routed</td>
    <td>Yes</td>
    <td>Rare</td>
    <td>No</td>
    <td>None</td>
  </tr>
  <tr>
    <td>Routing</td>
    <td>No</td>
    <td>Yes (Guards)</td>
    <td>RouterModule</td>
    <td>Feature (for routing)</td>
  </tr>
  <tr>
    <td>Service</td>
    <td>No</td>
    <td>Yes</td>
    <td>No</td>
    <td>AppModule</td>
  </tr>
  <tr>
    <td>Widget</td>
    <td>Yes</td>
    <td>Rare</td>
    <td>Yes</td>
    <td>Feature</td>
  </tr>
</table>


* * *


## **More on NgModules**

You may also be interested in the following:

* [Lazy Loading Modules with the Angular Router](https://github.com/angular/angular/blob/master/aio/content/guide/guide/lazy-loading-ngmodules).

* [Providers](https://github.com/angular/angular/blob/master/aio/content/guide/guide/providers).
