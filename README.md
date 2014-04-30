# SuffixConditionals

Add Ruby-like suffix and Python-like infix conditionals to Visualworks
Smalltalk.

SuffixConditionals is licensed under the MIT license.  See the
copyright tab in the RB, the `notice` property of this package or the
`LICENSE` file on GitHub.

SuffixConditionals' primary home is the [Cincom Public Store Repository](http://www.cincomsmalltalk.com/CincomSmalltalkWiki/Public+Store+Repository).
Check there for the latest version.  It is also on
[GitHub](https://github.com/randycoulman/SuffixConditionals).

SuffixConditionals was developed in VW 7.9.1, but is compatible with
any version of VisualworksSmalltalk. If you find any incompatibilities,
let me know (see below for contact information) or file an issue on
GitHub.

# Introduction

SuffixConditionals adds `if:`, `unless:`, and `if:else:` methods to
`BlockClosure` in Visualworks Smalltalk.

When writing a conditional expression with a single branch (i.e.,
`ifTrue:` or `ifFalse:`), it is sometimes desirable for the main focus
of the expression to be on the action, rather than the condition.  In
those cases, the action should come first.

Likewise, when using the return value of a conditional expression,
an infix notation of the condition is easier to read from time to time.

SuffixConditionals makes that possible.

For example, the following code:

```
(self respondsTo: methodName)
    ifTrue: [^self perform: methodName with: anEvent]
```

can be written as:

```
[^self perform: methodName with: anEvent]
    if: (self respondsTo: methodName)
```

Another example:

```
'Variable n is ' , (n odd ifTrue: ['odd'] ifFalse: ['even'])
```

could be rewritten as:

```
'Variable n is ' , (['odd'] if: n odd else: ['even'])
```

It is up to you to decide which form is more readable in your code,
but SuffixConditionals gives you the choice.

The methods `#if:`, `#unless:`, and `#if:else` are optimized in the
same way as the standard conditional methods (`#ifTrue:`, `#ifFalse:`,
etc), so SuffixConditionals does not impose an additional performance
penalty.  Thanks to Steffen Märcker for implementing this
optimization.

# Contributing

I'm happy to receive bug fixes and improvements to this package.  If
you'd like to contribute, please publish your changes as a "branch"
(non-integer) version in the Public Store Repository and contact me as
outlined below to let me know.  I will consider merging your changes
back into the "trunk" as soon as I can review them.

# Contact Information

If you have any questions about SuffixConditionals and how to use it, feel
free to contact me.

* Web site: http://randycoulman.com
* Blog: Courageous Software (http://randycoulman.com/blog)
* E-mail: randy _at_ randycoulman _dot_ com
* Twitter: @randycoulman
* GitHub: randycoulman
