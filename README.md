
# Grid lib

_Library of web grids built on Susy._

Grid lib was made as a collection of complete and responsive grids to be used directly on your own project. It is not a grid framework in the same sense as Bootstrap or 960. Grid lib simply aims to supply you with a large number of Sass placeholders containing flexible and responsive grid styles for you to apply to your project's selectors.

## Usage

### Short version
_To use the grid placeholders you need to:_

- Install the grid-lib node package
- Make sure your project includes the high level dependencies
- Import the grid-lib local dependencies
- Extend your grid selectors with the grid-lib placeholders

### More indepth
_To use the grid placeholders you need to:_

*Install the grid-lib node package:*
`npm install grid-lib --save-dev`

*Include high level deps:*
Grid lib makes use of `compass`, `susy` and `breakpoint`. They will need to be required in your project. This is usually achieved by `require('breakpoint')` in your `config.rb` file that handles the configuration of your compass project.

More information about this can be found here:
- [Compass](http://compass-style.org/)
- [Susy](http://susy.oddbird.net/)
- [Breakpoint](http://breakpoint-sass.com/)

*Local dependencies:*
In your project you'll need to import the file `dist/grid-lib.sass`. This file will in turn import the different dependencies all grid placeholders has.

`@import node_modules/grid-lib/dist/grid-lib`

*Extend your selectors:*
This is the end usage of grid-lib, time for you to import the grids you're interested in using and to extend your selectors like so:

```
// Import interesting grids
@import sb-main
@import sb-main-sb

// Extend your own selectors
.my-custom-main-grid-container
  @extend %sb-main

.another-secondary-container
  @extend %sb-main-sb
```

## About grid lib

Unlike Bootstrap and most grid frameworks, this approach doesn't require you to add any new classes to your markup. The main assuption made in Grid lib is that the grid's columns should be direct children of the container to which the grid placeholder was applied. See the structure below.

_Incorrect_

```
.my-grid-container
  .some-random-wrapper <!-- Problem! -->
    .grid-col-1
      - content
    .grid-col-2
      - content
```

_Correct_

```
.my-grid-container
  .grid-col-1 <!-- Direct child to .my-grid-container -->
    - content
  .grid-col-2 <!-- Direct child to .my-grid-container -->
    - content
```

## Contributions

_TODO: complete docs._