---
layout: post
title:      "Should You Truly Never Use var?"
date:       2017-10-21 00:08:26 -0400
permalink:  should_you_truly_never_use_var
---


While the 'Variables' readme in the new and excellent Learn V3 curriculum says use var never, some controversy in the Javascript community has emerged over this classic variable declaration. So, is the V3 curriculum correct and we should forever delegate var to the dustbin? This blog post gets to the bottom of the debate.

First, the arguments against var. 

1. No error is thrown if you declare the same variable twice using var (conversely, both let and const will throw an error if a variable is declared twice)

2. Variables declared with var are not block scoped (although they are function scoped), while with let and const they are. This is important because what’s the point of block scoping if you’re not going to use it? So using var in this context would require a situation in which a variable declared inside a function would need to be used in the global scope. I’m not able to think of any situations where that would be absolutely necessary, but perhaps they exist. 

3. Another argument that has been made against the use of var is that JS Linters are now pointing out their use as bad practice. I conducted a quick search on the Internet revealed that Jslint.com and Jshint.com did not raise an issues with the use of Var as a variable declaration. However, ESLint explicitly has a no-var rule aimed at discouraging the use of var (https://eslint.org/docs/rules/no-var). 

4. Most Javascript experts agree Var shouldn’t be used. Douglas Crockford, the man who popularized JSON, is against the use of var. He indicates that, “var might possibly still be useful in an extreme case like machine-generated code, but I'm stretching hard there.” Wes Bos also says he won’t use var. 

So, with the above reasons clearly and logically indicating why var should never be used, why would any be temped to use it over const or let again? Kyle Simpson, author of You Don’t Know JS, and all-around Javascript guru, in this article -- https://davidwalsh.name/for-and-against-let – has argued in favor of var. Simpson argues that: 

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

Essentially, Simpson is arguing that while changing var with let in the above example will still work the same, because two blocks inside the function explicitly take advantage of let’s block scoping (remember only let/const are block scoped not var), var is a helpful signal to indicate a function scope.
 
(Simpson also makes the case that when he uses try…catch blocks for debugging, the let block scope causes unwanted errors.)

Ultimately, after looking at the above code example Simpson provides, it’s not difficult to see how var constitutes a cleaner option in that instance. 

Of course, many people disagree with Simpson. Sure, in the above example var is a clearer signal than let, but since it operates the same is it really worth bringing it into play? 
