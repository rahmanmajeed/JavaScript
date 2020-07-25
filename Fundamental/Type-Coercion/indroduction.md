# JavaScript Type-Coercion

<p>
In JavaScript, you can convert a value from one type to another. When it's done  _`explicitly`_ called _`type casting`_ and when it's done _`implicitly`_ this is called 
_`type coercion`_ . Type coercion is magical, evil, confusing. But it's not weird, I will explain it here step by step how it works.

Our goal is to fully explore the pros and cons (yes, there are pros!) of coercion, so that you can make an informed decision on it appropriateness in your program.
</p>
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


  Source & Reference: [ALEX DEVERO BLOG](https://blog.alexdevero.com/) [YDKJS]
