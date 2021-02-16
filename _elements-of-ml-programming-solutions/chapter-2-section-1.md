---
layout: page
title: Chapter 2, Section 1 - Expressions
categories: chapter-2 section-1
---

## Exercise 2.1.1

What is the response of ML to the following expressions?

### a

```sml
1+2*3
```

> ```sml
> val it = 7 : int
> ```

### b

```sml
5.0-4.2/1.4
```

> ```sml
> val it = 2.0 : real
> ```

### c

```sml
11 div 2 mod 3
```

> ```sml
> val it = 2 : int
> ```

### d

```sml
"foo"^"bar"^""
```

> ```sml
> val it = "foobar" : string
> ```

### e

```sml
3>4 orelse 5<6 andalso not (7<>8)
```

> ```sml
> val it = false : bool
> ```

### f

```sml
if 6<10 then 6.0 else 10.0
```

> ```sml
> val it = 6.0 : real
> ```

### g

```sml
0xAB+123
```

> ```sml
> val it = 294 : int
> ```

### h

```sml
0xab<123
```

> ```sml
> val it = false : bool
> ```

## 2.1.2

The following ML "expressions" have errors in them. Explain what is wrong with each.

### a

```sml
8/4
```

The / operator applies only to reals, not integers. Use div instead.

```sml
8 div 4
```

### b

```sml
if 2<3 then 4
```

if ... then ... is not a valid statement. There must be an else.

```sml
if 2<3 then 4 else 5
```

### c

```sml
1<2 and 5>3
```

`and` cannot be applied to boolean values; `andalso` must be used instead.

```sml
1<2 andalso 5>3
```

### d

```sml
6+7 DIV 2
```

Operators are case sensitive; `DIV` must be replaced with `div`.

```sml
6+7 div 2
```

### e

```sml
4.+3.5
```

A real number needs to have digits both before and after the decimal point. Instead of `4.`, use `4.0`.

```sml
4.0+3.5
```

### f

```sml
1.0<2.0 or 3>4
```

`or` cannot be applied to boolean values; `orelse` must be used instead.

```sml
1.0<2.0 orelse 3>4
```

### g

```sml
#"a"^#"b"
```

The concatentation operation `^` applies to strings, not characters.

```sml
"a"^"b"
```

### h

```sml
123.
```

A real number needs to have digits both before and after the decimal point. Instead of `123.`, use `123.0`.

```sml
123.0
```

### i

```sml
1.0 = 2.0
```

Real numbers may not be compared using = or <>.

```sml
1.0 <= 2.0 andalso 2.0 <= 1.0
```

## 2.1.3

Write a string that when printed creates the displayed text on lines (3)-(5) of Example 2.6. You may assume that the indentation of the lines is made by a single tab character. Your string should be written over several lines so there are no more than 80 characters appearing on any one line.

```sml
"\t\"\\\\\\\" stands for the double-quote character, \\\n \
\\t\\which otherwise would be interpreted \\\n \
\\t\\as the string ender.\"\n"
```

## 2.1.4

Express:

a) `E orelse F`

b) `E andalso F`

as if-then-else expressions. Incidentally, in ML, expressions formed with the symbols orelse and andalso are actually shorthands for these if-then-else expressions.

### a

`E orelse F`

```sml
if E then true else F
```

### b

`E andalso F`

```sml
if E then F else false
```
