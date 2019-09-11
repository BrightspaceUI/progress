# d2l-progress
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/BrightspaceUI/progress)
[![Bower version][bower-image]][bower-url]
[![Build status][ci-image]][ci-url]

A set of [Polymer](https://www.polymer-project.org/) and [Sass](http://sass-lang.com/) mixins for styling native `progress` elements in D2L applications.

For further information on this and other components, refer to [The Brightspace UI Guide](https://github.com/BrightspaceUI/guide/wiki).

## Installation

`d2l-progress` can be installed from [Bower][bower-url]:
```shell
bower install d2l-progress
```

## Progress Styles

![screenshot of progress bar](/screenshots/progress.gif?raw=true)

## Usage

Progress styles can be applied using either [Polymer](https://www.polymer-project.org/1.0/) or [Sass](http://sass-lang.com/) mixins. Which one you use depends on your technology stack and comfort with each, however since Sass compiles to native CSS it's more performant.

### Polymer

Include the [webcomponents.js](http://webcomponents.org/polyfills/) "lite" polyfill (for browsers that don't natively support web components), import `d2l-progress.html`, and consume the required mixins in a custom style block:

<!---
```
<custom-element-demo>
  <template>
    <script src="../webcomponentsjs/webcomponents-lite.js"></script>
    <link rel="import" href="d2l-progress.html">
    <custom-style>
      <style is="custom-style">
        progress.d2l-progress {
          @apply --d2l-progress;
        }
        /* this is necessary to avoid white bleed over rounded corners in chrome and safari */
        progress.d2l-progress::-webkit-progress-bar {
          @apply --d2l-progress-webkit-progress-bar;
        }
        /* strangely, comma separating the selectors for these pseudo-elements causes them to break */
        progress.d2l-progress::-webkit-progress-value {
          @apply --d2l-progress-webkit-progress-value;
        }
        /* note: unable to get firefox to animate the width... seems animation is not implemented for progress in FF */
        progress.d2l-progress::-moz-progress-bar {
          @apply --d2l-progress-moz-progress-bar;
        }
        progress.d2l-progress::-ms-fill {
          @apply --d2l-progress-ms-fill;
        }
        /* these are necessary to avoid showing border when value is 0 */
        progress[value="0"].d2l-progress::-webkit-progress-value {
          @apply --d2l-progress-webkit-progress-value-no-progress;
        }
        progress[value="0"].d2l-progress::-moz-progress-bar {
          @apply --d2l-progress-moz-progress-bar-no-progress;
        }
      </style>
    </custom-style>
    <next-code-block></next-code-block>
  </template>
</custom-element-demo>
```
-->
```html
<progress class="d2l-progress" value="25" max="100"></progress>
```

### Sass

Import the main `d2l-progress.scss` file into your application's Sass. Then call the `d2l-progress()` mixin to define the styles of your `progress` element:

```sass
@import 'bower_components/d2l-progress/d2l-progress.scss';

progress.my-progress {
  @include d2l-progress();
}
```

## Developing, Testing and Contributing

After cloning the repo, run `npm install` to install dependencies.

If you don't have it already, install the [Polymer CLI](https://www.polymer-project.org/2.0/docs/tools/polymer-cli) globally:

```shell
npm install -g polymer-cli
```

To start a [local web server](https://www.polymer-project.org/2.0/docs/tools/polymer-cli-commands#serve) that hosts the demo page and tests:

```shell
polymer serve
```

To lint ([eslint](http://eslint.org/) and [Polymer lint](https://www.polymer-project.org/2.0/docs/tools/polymer-cli-commands#lint)):

```shell
npm run lint
```

To run unit tests locally using [Polymer test](https://www.polymer-project.org/2.0/docs/tools/polymer-cli-commands#tests):

```shell
polymer test --skip-plugin sauce
```

To lint AND run local unit tests:

```shell
npm test
```

[bower-url]: http://bower.io/search/?q=d2l-progress
[bower-image]: https://img.shields.io/bower/v/d2l-progress.svg
[ci-url]: https://travis-ci.com/BrightspaceUI/progress
[ci-image]: https://travis-ci.com/BrightspaceUI/progress.svg?branch=master

## Versioning & Releasing

All version changes should obey [semantic versioning](https://semver.org/) rules.

Include either `[increment major]`, `[increment minor]` or `[increment patch]` in your merge commit message to automatically increment the `package.json` version and create a tag during the next build.
