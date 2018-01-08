---
layout: post
title:      "Why Javascript's Spread Operator is a Powerful Tool "
date:       2018-01-08 01:33:41 +0000
permalink:  why_javascripts_spread_operator_is_a_powerful_tool
---


The spread operator is an awesome part of the ES6 arsenal that any Javascript developer should become familiar with. This blog post will cover how you can use the spread operator in variable assignment (a technique critical in Redux). 

Basically, variable assignment in Javascript works like this:

> const dog = { furry: true };

> const hairlessCat = dog;

> hairlessCat.furry;
> => true

OK, so hairlessCat shouldn’t be furry.

> hairlessCat.furry = false

BUT NOW…

> dog.furry

> => false

Thus, the spread operator to the rescue. Instead of assigning hairlessCat to dog like we did above, we instead use the spread operator to copy its properties like so:

> dog.furry

> => false

Thus, the spread operator to the rescue. Instead of assigning hairlessCat to dog like we did above, we instead use the spread operator to copy its properties like so:

> const hairlessCat = {
>    …dog
> }

This way, we’re able to copy the properties of dog over to hairlessCat and change them and not have them impact the original dog object.

> const hairlessCat.furry = false;

> dog.furry;

> => dog

This concept is critical in Redux because mutating the original function is not allowed.





