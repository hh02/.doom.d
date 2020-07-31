Ox-pandoc test
==============

Test content
------------

1.  latex fragment
2.  code blocks
3.  symbols
4.  headline

ps: other elements all use symbols, so only testing symbols is enough.

Origin org
----------

``` {.org}
* 标题
** math 1
$a*b$
** math 2
\(a*b\)
** math 3
$$\frac{a}{b}$$
** math 4
\[\frac{a}{b}\]
#+BEGIN_SRC c
#include<stdio.h>
using namespace std;
int main() {
  return 0;
}
#+END_SRC
! @ # $ % ^ & *  (  ) - + _ = ~ `

; : ' ' " "

{  } [ ] | \ < > , . / ?

> very goog
![tupian](baidu.com)
** 二级标题
*** 三级标题
**** 四级标题
***** 五级标题
****** 六级标题
Text info.
```

Export to pandoc flavored markdown
----------------------------------

``` {.markdown}
---
---

标题
====

math 1
------

$a*b$

math 2
------

$a*b$

math 3
------

$$\frac{a}{b}$$

math 4
------

$$\frac{a}{b}$$

    #include <bits/stdc++.h>
    using namespace std;
    int main() {
      return 0;
    }

! @ \# \$ % \^ & \* ( ) - + \_ = \~ \`

; : \' \' \" \"

{ } \[ \] \| \\ \< \> , . / ?

\> very goog !\[tupian\](baidu.com)

二级标题
--------

### 三级标题

1.  四级标题

    1.  五级标题

        1.  六级标题

            Text info.
```

Export to mmd markdown
----------------------

```` {.markdown}
标题
====

math 1
------

\\(a*b\\)

math 2
------

\\(a*b\\)

math 3
------

\\[\frac{a}{b}\\]

math 4
------

\\[\frac{a}{b}\\]

``` c
#include<stdio.h>
using namespace std;
int main() {
  return 0;
}
```

! @ \# $ % \^ & \* ( ) - + \_ = \~ \`

; : ' ' " "

{ } \[ \] \| \\ \< \> , . / ?

\> very goog !\[tupian\](baidu.com)

二级标题
--------

### 三级标题

1.  四级标题

    1.  五级标题

        1.  六级标题

            Text info.
````

Pandoc vs mmd
-------------

1.  latex fragment
    -   pandoc use `$...$`, `$$...$$`
    -   mmd use `\(...\)`, `\[...\]`
2.  code blocks
    -   pandoc use

        ```` {.markdown}
        ``` {.c}

        ```
        ````

    -   mmd use

        ```` {.markdown}
        ``` c

        ```
        ````

3.  symbols Pandoc escapes more symbols: \`\$\`, \`\'\`, \`\"\`.
    (that\'s why pandoc latex fragment can use \$).
4.  headlines They are the same.

Addtion
-------

A few days ago I recommended ox-qmd, but I found that it did not escape
symbols which easy to cause ambiguity. In addtion, cnblogs use pandoc as
markdown engine, so I recommended pandoc.
