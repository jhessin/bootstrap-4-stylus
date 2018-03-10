# bootstrap-4-stylus

stylus port of bootstrap.css v4.0.0-beta.
🚧 UNDER CONSTRUCTION 🚧
This a fork of the original created by [Angeal185](https://github.com/angeal185). This is a (to-be) pure mixin library.

## Installation

When published (not-yet):
NPM/Yarn: (not sure how bower works)

```sh
yarn add stylus-pure-mixins
```

## info

A complete, fully functional convert of bootstrap.css to stylus. Using nothing but pure mixins for those of us who actually like writing stylus instead of just importing it and forgetting it.

## Progress

Currently I have just started converting everything over to mixins. It may take some time I'm starting at the top and working my way down.

## Instructions

bootstrap.css has been converted, broken down into smaller .styl includes and the include files are named accordingly. Each class should be replaced with a mixin. This allows you to build custom classes in your .styl files and keep your html class lists to a flat minimum. This is useful for a flat map of styles.

```stylus
.my-app-tabs
  nav-tabs()

.my-app-button
  btn()
```

### Conventions

To minimize and standardize the number of classes used inside mixins for functionality I am adopting the following conventions:

Classes like `.close` and `.active` will remain as is (unless overwritten as parameters of the mixin) as these are clear and concise. Clases like `.tab-pane`, `.alert-link`, and `.card-link` will be shortened to simply `.pane` or `.link` for conciseness these too can be overwritten as parameters (more explaination to follow).

For hyphenated abreviations such as `.badge-primary` etc. I took a different track. I added a list parameter to the `badge()` mixin so you can write `badge(pill primary)` to get a primary colored pill badge.
So far this is the case for:

* badge(--types: list) -- accepts (btn, pill, primary, secondary...)
* align-self(--type), align-content(), and all sized variants align-self-sm(...) -- accepts every standard align-self/align-content parameter.
* align(--type) -- accepts (baseline, top, middle, bottom, text-bottom, text-top) all this realy does is same a bit of typing (vertical and !important).
* alert(--types: list, --close: class, --link: class)
* bg(--type: either a defined color or valid rgba, --hover: (optional) rgba for hover and active links)
* ** pretty much everything I will let you know more when I'm done **

** note I removed alert-dismissable as all it did was allow you to add a class to an alert and hide it (something you should be able to do anyway).
### Variables

Build variables can be overwritten before importing into your .styl file.

i.e.

```stylus
--primary = green
--secondary = grey

@require('~stylus-pure-mixins')
```

### A complete list of customizable variables

```stylus

// colors
--primary := #007bff
--primaryHov := #0062cc
--primaryBtnHov := #0069d9
--secondary := #868e96
--secondaryHov := #6c757d
--secondaryBtnHov := #727b84
--success := #28a745
--successHov := #1e7e34
--successBtnHov := #218838
--info := #17a2b8
--infoHov := #117a8b
--infoBtnHov := #138496
--warning := #ffc107
--warningHov := #d39e00
--warningBtnHov := #e0a800
--danger := #dc3545
--dangerHov := #bd2130
--dangerBtnHov := #c82333
--light := #f8f9fa
--lightHov := #dae0e5
--lightBtnHov := #e2e6ea
--dark := #343a40
--darkHov := #1d2124
--darkBtnHov := #23272b

--white := #fff
--black := #000

--bodyColor := #212529
--bodyBackground := --white

//grid breakpoints
--grid-sm := 576px
--grid-md := 768px
--grid-lg := 992px
--grid-xl := 1200px

//container-max-size
--container-sm := 540px
--container-md := 720px
--container-lg := 960px
--container-xl := 1140px

//fonts
--font-weight-light := 300
--font-weight-normal := normal
--font-weight-bold := bold

--font-family-base := -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif
--font-family-monospace :=  "SFMono-Regular", Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace

--h1-font-size := 2.5rem
--h2-font-size := 2rem
--h3-font-size := 1.75rem
--h4-font-size := 1.5rem
--h5-font-size := 1.25rem
--h6-font-size := 1rem

//display
--display1-size := 6rem
--display2-size := 5.5rem
--display3-size := 4.5rem
--display4-size := 3.5rem

--display1-weight := --font-weight-light
--display2-weight := --font-weight-light
--display3-weight := --font-weight-light
--display4-weight := --font-weight-light
```
