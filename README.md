# v2-typography

Typography styles and mixins for nib. See the [nib-pattern-library](http://nib-pattern-library.azurewebsites.net/pages/typography.html) for usage.

## Build

    npm run build
    
For older projects not using scss. To see an example:

    npm run example.build


## Using mixins

Mixins allow us to have fewer classes on html elements, without needing to rewrite styles.

For the typography mixins we have left behind the `v2-` prefix. 

### @include title($size: (1-4), $color: (grey, green, white), $pad: (false, true));
### @include link($color: (inherit, green, grey, white));
### @include copy;
### @include paragraph;

CSS:

    @import "@nib-styles/v2-typography";
    
    .box {
      // mixin equivalent of .v2-copy
      @include copy;
    }
    
    .custom-title {
      // mixin equivalent of .v2-title .v2-title--1, plus green text color
      @include title($size: 1, $color: green, $pad: false);
      transform: rotate(180deg);
    }
    
    .custom-subheading {
      // mixin equivalent of .v2-title .v2-title--1, plus green text color
      @include title(2, white, true);
      background: $green--elizabeth;
    }
    
    .custom-paragraph {
      // mixin equivalent of .v2-paragraph
      @include paragraph;
      text-align: right;
    }
    
    .custom-link {
      // mixin equivalent of .v2-link--green
      @include link(green);
    }

HTML:

    <div class="box">
      <h1 class="custom-title">A mixed in heading</h1>
      <h3 class="custom-subheading">Lorem ipsum</h3>
      <p class="custom-paragraph">Nunc urna mi, <a href="#" class="custom-link">faucibus sed egestas</a> quis, laoreet sed felibitur vit risus i.</p>
    </div>
    
## Changelog

### v2.3.0

- Mixins!!

### v2.2.0

- Setting `color: inherit` on `.v2-link` by default

## To do

- List mixins
