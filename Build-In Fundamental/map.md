# Map & Set

> In JavaScript, objects are used to store multiple values as a complex data structure.

An object is created with curly braces `{...}` and a list of properties. A property is a key-value pair where the `key` must be a string and the `value` can be of any type.

On the other hand, `arrays` are an ordered collection that can hold data of any type. In JavaScript, arrays are created with square brackets `[...]` and allow duplicate elements.

> Until ES6 (ECMASCRIPT 2015), JavaScript `objects` and `arrays` were the most important data structures to handle collections of data. The developer community didn't have many choices outside of that. Even so, a combination of objects and arrays was able to handle data in many scenarios.

### _map_
Map is a collection of keyed data items. just like an [Object](). But the main difference is that [Map]() allows keys of any type.

Methods and properties are:

- `new Map()`-creates the map.

A `Map` object iterates its elements in insertion order - a `for...of` loop returns an array of `[key, value]` for each iteration.