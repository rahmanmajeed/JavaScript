# JavaScript Type-Coercion


In JavaScript, you can convert a value from one type to another. When it's done  _`explicitly`_ called _`type casting`_ and when it's done _`implicitly`_ this is called 
_`type coercion`_ . Type coercion is magical, evil, confusing. But it's not weird, I will explain it here step by step how it works.

Our goal is to fully explore the pros and cons (yes, there are pros!) of coercion, so that you can make an informed decision on it appropriateness in your program.

<h2 align="center">Introduction</h2>

  JavaScript is an interesting language. It allows you to convert value of one type into another. This process of type conversion is called _`type coercion`_. When it's done _`explicitly`_ called _`type casting`_ (or explicit coercion) and when it's done _`implicitly`_ this is called _`type coercion`_ (or implicit coercion). `type casting` (or `type conversion`) occurs statically typed at compile time, while `type coercion` is a runtime conversion for dynamically typed languages.

The Type coercion applies to primitive types:

        - Number
        - String
        - Boolean
        - Null and
        - Undefined.

It is also applies on _`Symbol`_ such as: `+,-,*,/,|,&` etc.

>Sometimes, it also applies to objects.

When type coercion or type casting happens, the result is always some _`primitive`_ type, like `string`, `number`, or `boolean`. It will never happen that the result of type coercion, or casting, will be either **object** or a **function**.

However, we discuss and distinguish the _`implicit`_ coercion and _`explicit`_ coercion

<h2 align="center">Implicit and explicit type coercion</h2>

As you know, type coercion refers to implicit type conversion while type casting to explicit. When JavaScript developers talk about type coercion, they usually refer to both types, implicit and explicit. 

The difference should be obvious. `explicit coercion` is when it is obvious from looking at the code that a type conversion is intentionally occurring, whereas `implicit coercion` is when the type conversion will occur as less obvious side effect of some other intentional operation.

For example, consider these two approaches to coercion:

```js
var a = 42;
var b = a + "";
var c = String(a);

```
Here For b, the coercion that occurs happens `implicitly` and it will a string operation, because the `+` operator will insist on the operation being a _`string`_ concatenation if any of the operand is type of a `string`.

Source & Reference: [ALEX DEVERO BLOG](https://blog.alexdevero.com/) [YDKJS](https://github.com/getify/You-Dont-Know-JS)
