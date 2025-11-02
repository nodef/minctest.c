# Minctest


Minctest is a very minimal unit-testing "framework" written in ANSI C and
implemented in a single header file, by [Lewis Van Winkle](https://github.com/codeplea). It's handy when you want some real simple
unit tests for a small project.

Basically, it implements assertion and equal functions. It'll track and time
how many tests pass and fail. Failed tests will also display which line the
failing test code was on.

There is a [Node.js port here](https://github.com/codeplea/minctest-node) and a [Lua port here.](https://github.com/codeplea/minctest-lua)

## Installation

Run:
```bash
$ npm i minctest.c
```

And then include `minctest.h` as follows:
```c
#include "node_modules/minctest.c/minctest.h"
```

## Features

- **C99 with no dependencies**.
- Single header file.
- Reports file and line number for failed assertions.
- Reports run time for each test.
- Tests continue even after an assertion fails.
- Has assertion for checking float equality.
- Released under the zlib license - free for nearly any use.

## Example

    #include "minctest.h"

    void test1() {
        lok('a' == 'a');
    }

    void test2() {
        lequal(5, 5);
        lfequal(5.5, 5.5);
        lsequal("abc", "abc");
    }

    int main(int argc, char *argv[])
    {
        lrun("test1", test1);
        lrun("test2", test2);
        lresults();
        return lfails != 0;
    }


That produces the following output:

            test1:
             -- pass: 1                    fail: 0                    time: 12ms
            test2:
             -- pass: 3                    fail: 0                    time: 0ms
    ALL TESTS PASSED (4/4)



## Hints
     All functions/variables start with the letter 'l'.

## Users

Minctest is used in almost all of my C projects, including:

* [Tulip Indicators - Financial Technical Analysis Indicators](https://tulipindicators.org)
* [TinyExpr - Math Expression Evaluation Library](https://codeplea.com/tinyexpr)
* [Genann - Neural Network Library](https://codeplea.com/genann)

You can check those out to see how Minctest is used in practice.

If you're using Minctest in your project, let me know. I could add a link back.

<br>
<br>


[![ORG](https://img.shields.io/badge/org-nodef-green?logo=Org)](https://nodef.github.io)
![](https://ga-beacon.deno.dev/G-RC63DPBH3P:SH3Eq-NoQ9mwgYeHWxu7cw/github.com/nodef/minctest.c)
