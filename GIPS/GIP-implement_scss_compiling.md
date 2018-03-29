## Preamble
```
GIP: <to be assigned>
Title: Implement Sass or LESS Compiling
Author: Mark Beacom, Olaf Ghanizadeh, Mitch Kosowski, Ian Liddle, Josh Mobley, Kevin Owocki, Elan Trybuch
Type: Standard track
Category: Front-end
Status: Draft
Created: 2018-03-28
```
## Simple Summary

As I Gitcoin developer  
I would like to have have consolidated styling (view layer abstracted away from logic)  
So that I can quickly make global styling changes across the app and have re-useable components, variables, etc.

## Motivation

Current styling in the site is “[is messy and a hassle to edit](https://github.com/gitcoinco/web/issues/135)”

0. Templates that aren’t reusable across [Dashboard](https://github.com/gitcoinco/web/tree/master/app/dashboard), [Marketing](https://github.com/gitcoinco/web/tree/master/app/marketing), [Retail](https://github.com/gitcoinco/web/tree/master/app/retail), etc.
1. Non-reusable variables and components so that it’s difficult to maintain consistency across the site

## Specification and Rationale

Specification describes the syntax and semantics of any new feature and rationale fleshes out that specification. These are not applicable to this GIP.

## Backwards Compatibility

N/A

## Test Cases

0. Build process that leverages SCSS to consolidate styling across the app
1. Preserve all current functionality (do no harm)

## Implementation

This initiative will be chunked into smaller segments with a staggered bounty schedule starting with the homepage.

B lock E lement M odifier aka BEM will be used to write both class names and css. 

For example consider this simple `<img>` element:
```
<img src="https://gitcoin.co/static/v2/images/tldr/bounties.574eee54d651.jpg">
```
using BEM it will be re-written in the following manner where p could stand for pattern. In this case `p-image` is the pattern block `__image` is the pattern element and `--jpg` is the modifier.
```
<div class="p-image">
  <img class="p-image__image p-image__image--jpg" src="https://gitcoin.co/static/v2/images/tldr/bounties.574eee54d651.jpg">`
</div>
```
This lets us re-write .css from:
```
.tldr_container img {
    max-width: 250px;
    max-height: 250px;
}
```
to:
```
.p-image {
  &__image{
    &--jpg{
      max-width: 250px;
      max-height: 250px;
    }
  }
}
```
This keeps the .css contained. This can also let us create a pattern for reusability and increase performance by using [reference](https://css-tricks.com/reference-imports-in-less-are-kinda-cool/):
```
@import (reference) '/path/to/patterns/image/image.less
```

Files will be broken out so any new developer coming in can quickly identify and implement bug-fixes, enhancements, new features etc.
```
/styles/base/colors.less
/styles/base/spacing.less
/styles/base/type.less
/styles/base/breakpoints.less
/styles/base/etc..
```

## TBD
Deciding between LESS vs. Sass. [Trends](https://insights.stackoverflow.com/trends?tags=sass%2Cless/)show that Sass is on the upswing and as fostering as much community contribution as possible is one of the goals of Gitcoin Sass will be used **TODO: CONFIRM THIS APPROACH**
## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).