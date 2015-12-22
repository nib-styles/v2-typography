# @nib-styles/v2-typography

Typography styles and mixins for nib. See the [nib-pattern-library](https://nib-pattern-library.firebaseapp.com/pages/typography.html) for usage.

## Build

    npm run build
    
For older projects not using scss. To see an example:

    npm run example.build


## Using mixins

Mixins allow us to have fewer classes on html elements, without needing to rewrite styles. For the typography mixins we have left behind the `v2-` prefix. 

There are mixins for titles, copy and links. For lists and utils you will need to use the compiled classes ***(see below)***

### @include title($size: (1-4), $color: (grey/green/white), $pad: (false/true));

Mixin equivalent of `.v2-title`, plus `.v2-title--1/2/3/4`, plus new capability to adjust colour (grey default) and add padding (false by default)

### @include link($color: (inherit/green/grey/white));

Mixin equivalent of `.v2-link`, plus optional `.v2-link--green/grey/white`

### @include copy;

Mixin equivalent of `.v2-copy` class.

### @include paragraph;

Mixin equivalent of `.v2-paragraph` class.

CSS:

    @import "@nib-styles/v2-typography";
    
    .box {
      @include copy;
    }
    .custom-title {
      @include title($size: 1, $color: green, $pad: false);
      transform: rotate(180deg);
    }
    .custom-subheading {
      @include title(2, white, true);
      background: $green--elizabeth;
    }
    .custom-paragraph {
      @include paragraph;
      text-align: right;
    }
    .custom-link {
      @include link(green);
    }

HTML:

    <div class="box">
      <h1 class="custom-title">A mixed in heading</h1>
      <h3 class="custom-subheading">Lorem ipsum</h3>
      <p class="custom-paragraph">Nunc urna mi, <a href="#" class="custom-link">faucibus sed egestas</a> quis, laoreet sed felibitur vit risus i.</p>
    </div>
    
## Using compiled classes

CSS:

    @import "@nib-styles/v2-typography/dist/compiled";


HTML:

    <div class="v2-article v2-copy">
      <h1 class="v2-title v2-title--3">Page title</h1>
      <p class="v2-paragraph">This is a paragraph with a <a class="v2-link" href="#">link</a>.</p>
      <ul class="v2-list v2-list--copy">
        <li class="v2-list--item">One</li>
        <li class="v2-list--item">Two</li>
        <li class="v2-list--item">Three</li>
      </ul>
    </div>
    

## Fluid Type Setting

Fluidly set the type size between a specified min and max font size, over a specified viewport size range.

Current settings:

- `min-font`: 14px
- `max-font`: 20px
- `min-width`: 400px
- `max-width`: 1200px

This means that at screen sizes at or below 400px wide, the font will be 14px. Over 1200px and the font will be fixed at 20px. In between the font will be somewhere in between.

NB: These values are yet to be ratified by the designers.

## Modular Scale

Headings 1-4 and paragraph text obey a [perfect fourth](http://www.modularscale.com/?16&px&1.333&web&text) modular scale. All sizes must be specified relative to the root element using rems in order to follow the scale.


## Changelog

### v2.3.0

- Mixins!!

### v2.2.0

- Setting `color: inherit` on `.v2-link` by default

## To do

- List mixins
