---
layout: post
title:      "Should You Truly Never Use Var?"
date:       2017-10-21 04:08:25 +0000
permalink:  should_you_truly_never_use_var
---


While the Variables Readme of the new and very excellent Learn V3 curriculum says use Var never, some controversy in the Javascript community has emerged over this once mighty variable declaration. So, is the V3 curriculum correct and we should forever delegate Var to the dustbin? This blog post will get to the bottom of the debate.

First, the arguments against Var. 

1. No error is thrown if you declare the same variable twice using Var (conversely, both let and const will throw an error if a variable is declared twice)

2. Variables declared with var are not block scoped (although they are function scoped), while with let and const they are. This is important because what’s the point of block scoping if you’re not going to use it.
 
So using Var in this context would require a situation in which a variable declared inside a function would need to be used in the global scope. I’m not able to think of any situations where that would be absolutely necessary, but perhaps they exist. 

4. Another argument that has been made against the use of Var is that JS Linters are now pointing out their use as bad practice. I conducted a quick search on the Internet revealed that Jslint.com and Jshint.com, and did not raise an issues with the use of Var as a variable declaration. However, ESLint explicitly has a no-var rule aimed at discouraging the use of Var (https://eslint.org/docs/rules/no-var). 

5. Most Javascript experts agree Var shouldn’t be used. Douglas Crockford, the man who popularized JSON, is against the use of var. He indicates that, “var might possibly still be useful in an extreme case like machine-generated code, but I'm stretching hard there.” Wes Bos also says he won’t use Var. 

So, with the above reasons clearly and logically indicating why Var should never be used, why would any be temped to use it over const or let again? Kyle Simpson, author of You Don’t Know JS, and all-around Javascript guru, in this article -- https://davidwalsh.name/for-and-against-let – has argued for a possible case for Var. Simpson argues that: 

“There are going to be places in real world code where some variables are going to be properly scoped to the entire function, and for those variables, var is a better signal” 

He provides this code block to illustrate his point:

```
function foo() {
    var a = 10;

    if (a > 2) {
        let b = a * 3;
        console.log(b);
    }

    if (a > 5) {
        let c = a / 2;
        console.log(c);
    }

    console.log(a);
}
```

Essentially, Simpson is arguing that while changing Var with let in the above example will still work the same, because two blocks explicitly take advantage of Let’s block scoping (remember only Let/Const are block scoped not var), Var is a helpful signal to indicate a function scope.
 
(Simpson also makes the case that when he uses try…catch blocks for debugging, the Let block scope causes unwanted errors.)

Ultimately, after looking at the above code example Simpson provides, it’s not difficult to see how Var constitutes a cleaner option in that instance. 

Of course, many people disagree with Simpson. Sure, in the above example Var is a clearer signal than Let, but since it operates the same, is it really worth bringing it into play? 
