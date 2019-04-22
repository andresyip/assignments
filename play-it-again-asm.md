**CMSI 284** Computer System Organization/Systems Programming, Spring 2019

# Make-Up Work 0510
These exercises are meant for students who ran into a rough patch at some point in the semester, or for those who needed a little extra time to get things to click. It is _make-up_ work, not extra work. As such, submissions will only be evaluated for students who have a final grade of C– or lower, and only for a maximum grade of C.

You will not be penalized if you do this work but turn out not to need it. It will still be time well spent: just a little more assembly language practice to solidify your knowledge of it for the rest of your lives (for most of you).

## Background Reading
As before, pretty much all of the information you need can be found in Dr. Toal’s assembly language pages (all linked from the [course website](https://dondi.lmu.build/spring2019/cmsi284)). Assembly language beginner and tutorial pages are harder to find on the web, but there are bound to be some out there.

## For Submission: Play It Again, _.asm_
Yes, this is a reference to an [oft-misquoted movie line](https://www.infoplease.com/askeds/editing-film-history). However, it is most applicable to these make-up exercises in this misquoted form.

Write the following programs in assembly language for 64-bit Linux machines on Intel x86_64 processors.

### Make Change (in U.S.A. denominations)
Write an x86_64 assembly language program for Linux, _make-usa-change.asm_, that takes a command line argument for a total number of cents and computes the number of quarters, dimes, nickels, and pennies that can be changed for that amount.

Sample program invocation and output:

    $ ./make-usa-change 142
    Quarters: 5
    Dimes: 1
    Nickels: 1
    Pennies: 2

Don’t worry about a negative amount, because assembly language.

If the wrong number of command line arguments is supplied, the program should respond as follows:

    $ ./make-usa-change
    This program requires exactly one integer command line argument.

Or:

    $ ./make-usa-change 78 12 33
    This program requires exactly one integer command line argument.

Because `atoi` just returns `0` on bad input values, don’t worry about detecting those:

    $ ./make-usa-change bazinga
    Quarters: 0
    Dimes: 0
    Nickels: 0
    Pennies: 0

As always, the grading of this program will be semi-automated, so it is very important that you adhere strictly to the specified output messages and format.

### Is Leap Year? (per the Gregorian Calendar)
Write an x86_64 assembly language program for Linux, _is-gregorian-leap-year.asm_, that takes a command line argument for an integer year and computes whether that year would be a leap year according to current [Gregorian calendar rules](https://en.wikipedia.org/wiki/Leap_year#Algorithm) (and not whether it actually _was_ a leap year as recorded by history).

Sample program invocation and output:

    $ ./is-gregorian-leap-year 1942
    1942 is not a leap year.

    $ ./is-gregorian-leap-year 1900
    1900 is not a leap year.

    $ ./is-gregorian-leap-year 2020
    2020 is a leap year.

    $ ./is-gregorian-leap-year 1500
    1500 is not a leap year.

(the Gregorian calendar was introduced in 1582, so under its rules, 1500 is not a leap year but historically it was recorded as one)

Don’t worry about negative years. Say it with me: _assembly language_.

If the wrong number of command line arguments is supplied, the program should respond as follows:

    $ ./is-gregorian-leap-year
    This program requires exactly one command line argument specifying a year.

Or:

    $ ./is-gregorian-leap-year 1985 2001 2019
    This program requires exactly one command line argument specifying a year.

Because `atoi` just returns `0` on bad input values, don’t worry about detecting those:

    $ ./is-gregorian-leap-year bazinga
    0 is a leap year.

As always, the grading of this program will be semi-automated, so it is very important that you adhere strictly to the specified output messages and format.

## How to Turn it In
Commit your source code (and _just_ the source code)—_make-usa-change.asm_ and _is-gregorian-leap-year.asm_—to this repository.

## Specific Point Allocations
These exercises will be evaluated according to outcomes _2c_, _2d_, _3a_, _3b_, and _4a_ to _4f_ in the [syllabus](https://dondi.lmu.build/spring2019/cmsi284/cmsi284-spring2019-syllabus.pdf). Graded categories are as follows:

| Category | Points | Outcomes |
| -------- | -----: | -------- |
| _make-usa-change.asm_ | 50 points total | |
| • Assembles, links, and runs without unexpected errors | 10 points | _3a_, _4a_, _4d_ |
| • Correct program output | 25 points | _2c_, _2d_, _3b_, _4a_, _4d_ |
| • Correct handling of invalid user input | 15 points | _2c_, _2d_, _3b_, _4a_, _4d_ |
| _is-gregorian-leap-year.asm_ | 50 points total | |
| • Assembles, links, and runs without unexpected errors | 10 points | _3a_, _4a_, _4d_ |
| • Correct program output | 25 points | _2c_, _2d_, _3b_, _4a_, _4d_ |
| • Correct handling of invalid user input | 15 points | _2c_, _2d_, _3b_, _4a_, _4d_ |
| Hard-to-maintain or error-prone code | deduction only | _4b_ |
| Hard-to-read code | deduction only | _4c_ |
| Version control | deduction only | _4e_ |
| Punctuality | deduction only | _4f_ |
| **Total** | **100** |

Note that inability to assemble, link, and run to begin with will negatively affect the correctness of program output and proper handling of invalid user input.

Because this is make-up work and not extra work, your final grade will be based on a percentage that adds 100 points to the total for the semester, and the percentage will be capped at a C. The work will have the most positive grade impact on students who do attain the learning outcomes for this course but may have hit a temporary snag during the semester.
