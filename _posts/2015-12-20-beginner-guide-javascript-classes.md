---
published: true
layout: post
title: Beginner's Guide to JavaScript Classes
---

So what are Classes in JavaScript? And why do we have them? What is their usage?

First, a prerequisite for understanding this blog post is a knowledge of how Objects in JavaScript works. I will spend a paragraph for anyone who doesn’t know.

Objects can be seen as a container. A data container. Much like how you would have a plastic container for you socks, underwear, etc. And they look something like this :

```javascript
var object = { 
  socks : 4, underwear : 6 
};
```

So what are classes then? And what are they used for?

First, I will say upfront that Classes are a modified version of an Object.

What do I mean?

Let’s say that you are running a supermarket in JavaScript. That’s right, in JavaScript. Let your imagination go wild with this one.

And you need 10 cash registers. As we all know, cash registers have multiples of functions some of which are : adding up all the items, processing payment, and opening the cash drawer.

How would I build 10 of these in JavaScript?

I guess I can do something like :

{% highlight javascript %}
var register1 = { 
  opendrawer : function() { … }, 
  closedrawer : function() { … }, 
  money : 50 
}

var register2 = { 
  opendrawer : function() { … }, 
  closedrawer : function() { … }, 
  money : 110 
}

var register3 = { 
  opendrawer : function() { … }, 
  closedrawer : function() { … }, 
  money : 20 
}
{% endhighlight %}

And on down the line. That could certainly work. But it isn’t the most efficient. If computers are not going to be efficient for us, why did we even create them in the first place? ;)

So that’s where Classes come in.

Classes are basically object factories.

Much like a car factory, it creates the same thing over and over again. And similar that scenario, you can get it in a different color for example. 

So how do we create this factory? 

Check this out, and I'll explain after :

```
var registerFactory = function(money) {
  var register = {};
  register.money = money;
  register.opendrawer = function() { },
  register.closedrawer = function() { },
  return register
};
```

So let's call this function and see what it does exactly.

We call the function like this :

```
var register1 = registerFactory(100);
```

The first line that will be executed will be 

```
var register = {};
```

This is pretty simple, we instantiate a new empty object, or a container. 

Then :

```
register.money = money;
```
This line sets the money property on the new object we just created. So now our register object looks like this :

```
register = {
  money: 50
}  
```

The next couple lines will do exactly the same thing so after those lines have finished we have this :

```
register = {
  money : 50,
  opendrawer : function() { ... },
  closedrawer : function() { ... }
}
``` 

Now the last line :

```
return register
```

Will return the 'register' object into 'register1' we defined above.

So now, we have a register1! And by this same logic we can create more registers that have the same properties without copy and pasting so much. 

We can do something like 

```
var register2 = registerFactory(110);
var register3 = registerFactory(20);
var register4 = registerFactory(100);
```

We can build more using for-loops, etc. 

So that's why and how Classes exist. They make repetitive tasks in creating containers quicker. And it makes it nicely organized :)
