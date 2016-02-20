---
layout: post
title:  "Welcome to Mantra!"
date:   2016-02-20 10:12:37 +0100
categories: mantra update
---
Mantra API:

{% highlight javascript %}
import MyComp from './myComp';
import {createApp} from 'mantra-core';

// Here's a simple Mantra Module
const module = {
  routes(injectDeps) {
    const InjectedComp = injectDeps(MyComp);
    // load routes and put `InjectedComp` to the screen.
  },
  load(context, actions) {
    // do any module initialization
  },
  actions: {
    myNamespace: {
      doSomething: (context, arg1) => {}
    }
  }
};

const context = {
  client: new DataClient()
};

const app = createApp(context);
app.loadModule(module);
// app.loadModule(someOtherModule);
app.init();
{% endhighlight %}
