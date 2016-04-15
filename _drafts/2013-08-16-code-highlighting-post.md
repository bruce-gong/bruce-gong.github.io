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

## What's the difference between Component and Directive
I hate to admit that directive is a parent class of component. But you can treat component as a super power version of directive. Component is restricted to use as element, while Directive can be used as element, attribute, class and comment.
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

## When to use component?
* If it is NOT template-less;
* If it does contain link function;
* The remainings should use component.

Mostly, I use Component as element, and use Directive as attribute with function inside.
