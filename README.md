# @nib-styles/v2-typography

nib styled typography

## Installation

    npm install --save @nib-styles/v2-typography

**Note**: Requires `Opens Sans` and `Roboto` fonts from Google Fonts:

```html
<link rel='stylesheet' href='//fonts.googleapis.com/css?family=Open+Sans:400,700|Roboto:300,700' />
```

## Usage

### Using mixins

```scss
@import "@nib-styles/v2-typography";

.product {

  &__title {
    @include title(2, $color: 'grey', $pad: true)
  }

  &__description {
    @include copy($color: 'grey', $pad: true)
  }

  &__link {
    @include link($color: 'green')
  }

}
```

```html
<div class="product">
    <h2 class="product__title">Top</h2>
    <p class="product__description">
      The best hospital cover you can get.
      <a class="product__link">Join now!</a>
    </p>
</div>
```

### Using compiled classes

```scss
@import "@nib-styles/v2-typography/compiled";
```

```html
<div class="v2-article">
    <h2 class="v2-title v2-title--2 v2-title--color-doc">Top</h2>
    <p class="v2-copy">
      The best hospital cover you can get.
      <a class="v2-link v2-link--green">Join now!</a>
    </p>
</div>
```

## Mixins

```scss
@include title($size, $color : null, $padding : false)
```

- `$size` Required. An integer from `1-4`.

- `$color` Optional. May be `grey`, `green` or `white`. If no color is provided the title will inherit the color from its parent element.

- `$padding` Optional. If `true` an amount of top and bottom margin is applied.

```scss
@include copy($size : null, $color : null, $padding : false)
```

- `$size` Optional. May be `small` or `large`.

- `$color` Optional. May be `grey`, `green` or `white`. If no color is provided the title will inherit the color from its parent element.

 `$padding` Optional. If `true` an amount of top and bottom margin is applied.


```scss
@include link($color : null)
```

- `$color` Optional. May be `green`, `grey` or `white`. If no color is provided the title will inherit the color from its parent element.

## Functions

```scss
text-color-disabled($color)
```

- `$color` Required. The normal text color.

## Changelog

### 5.0.0

- break: bump version of `v2-icons`

### v4.3.0

- fix: colour should default to `currentColour` when no color is specified


### v4.2.0

- add: a reusable function for generating the disabled text color

### v4.0.2

- fix: both color names and color name strings work for `title()`, `copy()` and `link()` mixins e.g. `copy($color: green)`, `copy($color: 'green')`

### v4.0.1

- fix: bumped the package version to display the latest readme on npmjs.com

### v4.0.0

- break: `copy()` color defaults to inherit
- break: `title()`, `copy()` and `link()` mixins error if they receive an invalid param
- add: `copy()` size configurable via mixin
- add: `$font-copy` and `$font-title` variables
- fix/break: `link()`/`.v2-link` now has font specified so it doesn't have to be inside a `v2-copy` block
- fix: `title()` padding should be dependent on the title size
- fix: issues with mixins comparing strings and color names
- fix: documentation

### v2.3.0

- Mixins!!

### v2.2.0

- Setting `color: inherit` on `.v2-link` by default
