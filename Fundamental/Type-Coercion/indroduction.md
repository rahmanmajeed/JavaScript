# JavaScript Type-Coercion

<p>
In JavaScript, you can convert a value from one type to another. This is called type coercion. Type coercion is one of the fundamental topics that can be hard to understand for it's weird behavior. But it's not weird, I will explain it here step by step how it works.
</p>
<h2 align="center">Introduction</h2>

  JavaScript is an interesting language. It allows you to convert value of one type into another. This process of type conversion is called `type coercion`. when it is done implicitly called implicit coercion. when it is done explicitly called explicit coercion.

The Type coercion applies to primitive types:

        * Number
        * String
        * Boolean
        * Null and
        * Undefined.

It is also applies on _`Symbol`_ such as: `+,-,*,/,|,&` etc.

>Sometimes, it also applies to objects.

When type coercion or type casting happens, the result is always some `_primitive_` type, like `string`, `number`, or `boolean`. It will never happen that the result of type coercion, or casting, will be either object or a function.


  Source & Reference: [ALEX DEVERO BLOG](https://blog.alexdevero.com/)
