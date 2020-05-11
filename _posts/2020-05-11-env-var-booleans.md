---
layout: post
title:  Environment Variable Booleans
date:   2020-05-11 11:41:21 -0500
notes: >-
    When working with environment variables, you sometimes want to have boolean flags. The problem is, envvars are inherintly strings. The better way when working with boolean environment variables is by using 1 or 0 instead.
---

Ugly:
```javascript
if (process.env.MYVAR === 'true')
if (process.env.MYVAR === '1')
```

Pretty:
```javascript
if (!!+process.env.MYVAR) // for boolean env vars for =0/=1
```

 This expression uses JavaScript's string to number dynamic casting of `+process.env.VAR` and double negates it (`!!`) to provide the user with `true` or `false` results.
