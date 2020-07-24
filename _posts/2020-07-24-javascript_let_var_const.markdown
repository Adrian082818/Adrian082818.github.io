---
layout: post
title:      "Javascript Let, Var, Const "
date:       2020-07-24 14:25:23 +0000
permalink:  javascript_let_var_const
---


Understanding the difference between the variable declarations of *let*, *var*, and *const* in Javascript and when to use them. In ES6 Javascript 'var' has been ruled out as an assignment method to use over 'let' and 'const', var isn't used as much anymore due to how volatile it can be when assigning values to it. With var, you can assign variable info and it can be updated and redeclared within its scope which would be the global scope. Let and Const are not globally scoped they are block-scoped, where var can be reassigned values or redeclared at any time 'let' can also be updated but it cannot be redeclared. The same won't go for const either, as implied from the name const as in a constant, const variable cannot be redeclared or updated. Using var as an identifier brought up some problems with reassignment and updating, thats where let and const come into play. Sometimes during coding, we tend to forget what we've assigned certain variables and use them again reassigning or updating the variable with our new info. While using var as the identifier for this there is no problem because it will be reassigned or updated but that's also the root problem. Using var is too volatile it can undo the code you've been working on simple by not realizing you've used the variable assignment already and just overwritten it with new info. I tend to favor using let or const over var for that sole reason, I tend to use let more for mathematical algorithms or loops. When I won't be reassigning anything I will use const that way my usage of it is clear as possible in my code. 

***Const*** is used for no reassignment.

***Let*** can be used for reassignment, such as looping for a counter, or swapping the values in an algorithm. It also identifies that the variable will be used only in the block it's defined in, which is not always the containing function. 

***Var*** is too messy and seems weak when compared to let and const when using it to define a variable in JavaScript. The variable may or may not be reassigned, and the variable may or may not be used for an entire function, or just for a block or loop.
