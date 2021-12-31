# CSS Playground

[Demos based on Jonas Schmedtmann's Udemy course](https://www.udemy.com/course/advanced-css-and-sass/)

- CSS parsing (client side)
  1. cascade: combines and resolves multiple/conflicting CSS rules applied to each element
  1. processes final CSS values (relative units to actual pixels)
- rule precedence: importance => specificity => declaration order
  - importance:
    1. user defined `!important`
    1. author defined `!important` (avoid to improve maintainability)
    1. author defined rules
    1. user defined rules
    1. browser defaults
  - [specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity): (based on selector type and the number of occurrences of a particular selector type)
    1. inline styles
    1. ids
    1. classes, pseudo-classes, attributes
    1. element, pseudo-element
  - declaration order: last declaration wins, import user defined styles after 3rd party style sheets
- box-sizing border-box: width/height includes padding and border (content-box shrinks)
- display inline: no high/width properties, only horizontal padding/margins
- display inline-block: inline but with box-model
- default browser font-size (typically 16px) may be redefined by user-agent

| unit                  | relative element reference |
| --------------------- | -------------------------- |
| % (width)             | parents width              |
| % (font-size)         | parents font-size          |
| em (width)            | current font-size          |
| em (font-size)        | parent font-size           |
| rem (width/font-size) | root font-size             |
| vh/vw                 | viewport height/width      |

```html
<!-- html responsive images -->
<picture>
  <!-- art direction: sets different picture source based on media query -->
  <source
    srcset="img/logo-mobile-1x.png 1x, img/logo-mobile-2x.png 2x"
    media="(max-width: 600px)"
  />
  <!-- default with density switching (srcset) based on DPR -->
  <img
    srcset="img/logo-default-1x.png 1x, img/logo-default-2x 2x"
    src="img/logo-default-2x"
  />
</picture>
```

```scss
// graceful degradation
@supports (display: grid) {
  display: grid;
}
```
