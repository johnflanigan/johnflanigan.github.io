---
layout: page
title: Chapter 2, Section 2 - Type Consistency
categories: chapter-2 section-2
---

## Exercise 2.2.1

Write expressions to make each of the following conversions.

### a

Convert `123.45` to the next lower integer.

> ```sml
> floor(123.45);
> ```

### b

Convert `-123.45` to the next lower integer.

> ```sml
> floor(~123.45);
> ```

### c

Convert `123.45` to the next higher integer.

> ```sml
> ceil(123.45);
> ```

### d

Convert `-123.45` to the next higher integer.

> ```sml
> ceil(~123.45);
> ```

### e

Convert `#"Y"` to an integer.

> ```sml
> ord(#"Y");
> ```

### f

Convert `120` to a character.

> ```sml
> chr(120);
> ```

### g

Convert `#"N"` to a real.

> ```sml
> real(ord(#"N"));
> ```

### h

Convert `97.0` to a character.

> ```sml
> chr(trunc(97.0));
> ```

### i

Convert `#"Z"` to a string.

> ```sml
> str(#"Z");
> ```


## 2.2.2

The following expressions contain type errors. What are the errors and how might we fix them?

### a

```sml
ceil(4)
```

`ceil` only to reals, not integers. We can fix it by changing `4` to `4.0`.

```sml
ceil(4.0)
```

### b

```sml
if true then 5+6 else 7.0
```

`5+6` returns an integer whereas 7.0 is a real. The types returned by the expression must match so the expression could be rewritten as

```sml
if true then 5.0+6.0 else 7.0
```

or

```sml
if true then 5+6 else 7
```

### c

```sml
chr(256)
```

chr only accepts integer arguments in the range 0 to 255. The argument could be changed to

```sml
chr(255)
```

### d

```sml
chr(~1)
```

chr only accepts integer arguments in the range 0 to 255. The argument could be changed to

```sml
chr(0)
```

### e

```sml
ord(3)
```

`ord` only accepts character arguments. `3` could be changed to `#"3"`.

```sml
ord(#"3")
```

### f

```sml
chr(#"a")
```

`chr` only accepts character arguments. Perhaps `ord` was meant.

```sml
ord(#"a")
```

### g

```sml
if 0 then 1 else 2
```
0 is not a boolean. Perhaps `false` was intended.

```sml
if false then 1 else 2
```

### h

```sml
ord("a")
```

`ord` only accepts character arguments, not strings.

```sml
ord(#"a")
```
