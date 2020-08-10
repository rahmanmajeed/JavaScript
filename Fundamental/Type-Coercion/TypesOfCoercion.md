# Types of Coercion in Javascript

<h2 align="center">Abstract Value Operations</h2>

Before we can explore _`explicit`_ vs _`implicit`_ coercion, we need to learn the basic rules that govern how values become either a string,number, or boolean. Here, we will specifically pay attention to _`ToString`_, _`ToNumber`_ and _`ToBoolean`_, and to a lesser extent, _`ToPrimitive`_.


<h2 align="center">ToString</h2>

When any non-string value is coerced to a _`string`_ representation, the conversion is handled by the _`ToString`_ abstract operation.

Bulit-in primitive values have natural stringification: `null` becomes `'null'`, `undefined` becomes `'undefined'` and `true` becomes `'true'`.

For regular objects, unless you specify your own, the default _`toString()`_ `l(located in Object.prototype.toString())` will return the internal [[Class]].

But as shown earlier, if an object has it's own _`toString()`_ method on it, and you use that object in a string-like way, it's _`toString()`_ will automatically be called.