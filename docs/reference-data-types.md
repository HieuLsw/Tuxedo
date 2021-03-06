---
id: data-types
title: Data types
---

A data type - as in regular programming languages - represents a type of data that is evaluated by the interpreter, taking into account its semantics.
Similarly, Tuxedo also deals with data types, however their implementation is not exacly a 1-to-1 map of the Swift types.

<AUTOGENERATED_TABLE_OF_CONTENTS>

---

Let's take a look one by one:

### `String`

A string type is a set of characters, a map of the Swift string type. 
To create one, you need to add a single-quote character to both sides, like this:
```
{{ 'This is a string' }}
```

You can perform all sorts of operations, and call functions and operators using string types. Here are a few examples:

Concatenation:
```
{{ 'This is ' + 'a string' }}
```

Capitalisation:
```
{{ 'This is a string'.capitalise }}
{{ 'This is a string'.lower }}
{{ 'This is a string'.upper }}
{{ 'This is a string'.lowerFirst }} //only the first character
{{ 'This is a string'.upperFirst }} //only the first character
```

Measurement:
```
{{ 'This is a string'.length }}
```

Trimming and encoding:
```
{{ '   This is a string  '.trim }}
{{ 'https://github.com/tevelee/Tuxedo'.urlEncode }}
{{ '%20'.urlDecode }}
{{ '/;?:!'.escape }}
{{ 'a\nb'.nl2br }}
```

Comparison:
```
{{ 'This' == 'This' }}
{{ 'This' != 'That' }}
```

Containment:
```
{{ 'This' contains 'hi' }}
{{ 'This' starts with 'Th' }}
{{ 'This' ends with 'is' }}
{{ 'This' matches '$T[sih]{3}^' }}
```

Transformation:
```
{{ 'a,b,c'.split(',') }}
```

### `Number`

Numeric types represent Swift double types. They parse all the numeric expressions:

Number literal:
```
{{ 123 }}
{{ 2.5 }}
{{ -9 }}
{{ pi }}
```

Commonly used operators are:

Arithmetics:
```
{{ 4 + 2 }} //addition
{{ 4 - 2 }} //subtraction
{{ 4 * 2 }} //multiplication
{{ 4 / 2 }} //division
{{ 4 % 2 }} //modulo
{{ 4 ** 2 }} //pow
```

Comparison:
```
{{ 1 < 2 }}
{{ 1 > 2 }}
{{ 1 <= 2 }}
{{ 1 >= 2 }}
{{ 1 == 2 }}
{{ 1 != 2 }}
```

and others
```
{{ abs(-4) }}
{{ round(2.4) }}
{{ sqrt(16) }}
{{ min(1,2) }}
{{ max(1,2) }}
{{ avg(1,2) }}
{{ sum(1,2) }}
{{ 3++ }}
{{ 3-- }}
{{ 4 is even }}
{{ 4 is not odd }}
```


### `Boolean`

Booleans map to Swift bool types.

Commonly expressed with true and false literals:
```
{{ true }}
{{ false }}
```

Logical operators apply:
```
{{ true and false }}
{{ true or false }}
{{ !true }}
{{ not false }}
{{ true ? 1 : 2 }}
```

### `Date`

Date types are also a map of the Swift date type.

```
{{ Date(2018,12,13) }}
{{ now }}
```

Formatting with format-string:
```
{{ date.format('dd/MM/yy') }}
```

Comparison:
```
{{ date1 == date2 }}
{{ date1 != date2 }}
{{ date1 < date2 }}
{{ date1 > date2 }}
{{ date1 <= date2 }}
{{ date1 >= date2 }}
```

### `Array`

Arrays are created with brackets on each side, comma separated elements between `[` and `]` or with the range operator (`...`).
```
{{ [1,2,3] }}
{{ ['a', 'b', 'c'] }}
{{ 4 ... 8 }}
```

Currently, only numbers and strings are supported in arrays, but other data types might work as well. If there is a need, it's really easy to extend this list.

Common operators
```
{{ 1 in [1,2,3] }}
{{ 'a' in ['a', 'b', 'c'] }}
{{ 5 not in 4 ... 8 }}
{{ [1,2].merge([3,4]) }}
{{ [1,2].min }}
{{ [1,2].max }}
{{ [1,2].sum }}
{{ [1,2].avg }}
{{ [1,2].count }}
{{ [1,2].first }}
{{ [1,2].last }}
{{ ['a', 'z'].join('-') }}
{{ [1,2,3].map(i => i * 2) }}
{{ [1,2,3].filter(i => i % 2 == 1) }}
{{ [1,2,3].1 }} //value at index 1
```

### `Dictionary`

Very similarly to array, dictionary can be created with a comma separated key-value pairs:
```
{{ {'a': 1, 'b': 2, 'c': 3} }}
```

Keys should always be string values, while values accept strings and number as well.

Common operators
```
{{ {'a': 1, 'b': 2}.keys }}
{{ {'a': 1, 'b': 2}.values }}
{{ {'a': 1, 'b': 2}.filter(k,v => k == 'a') }}
{{ {'a': 1, 'b': 2}.b }} //value for key b
```

### `Optional`

When we talk about optional, the framework does map to Swift optional, but to simply put it, it really just handles nil values nicely.

```
{{ null }}
{{ nil }}
```

Common operators
```
{{ nil.default('Empty value') }}
{{ array.first.default('Empty array') }}
```
