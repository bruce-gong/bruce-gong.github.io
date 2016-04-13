---
layout: post
title: AngularJS Learning Note 1 -- Component
description: "Talking about the definition of component and how it differs from directive"
modified: 2016-04-12
tags: [AngularJS, Front End, Web Development]
categories: [AngularJS]
---
## What is Component in AngularJS?
Component is a basic UI block. It was introduced in Angular 2.0, and now Angular 1.5 also brings it to us.

### Here's an example of component-style directive

{% highlight javascript %}
app.directive('list', function() {
  return {
    scope: {
      items: '='
    },
    templateUrl: 'list.html',
    controller: function ListCtrl() {},
    controllerAs: '$ctrl',
    bindToController: true
  }
});
{% endhighlight %}

### Here's how you write it with `.component`
{% highlight javascript %}
app.component('list', {
  bindings: {
    items: '='
  },
  templateUrl: 'list.html',
  controller: function ListCtrl() {}
});

{% endhighlight %}
