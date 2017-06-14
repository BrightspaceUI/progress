# d2l-progress

[![Bower version][bower-image]][bower-url]
[![Build status][ci-image]][ci-url]

A set of [Polymer](https://www.polymer-project.org/1.0/) and [Sass](http://sass-lang.com/) mixins for styling native `progress` elements in D2L applications.

For further information on this and other Brightspace UI components, see the docs at [ui.developers.brightspace.com](http://ui.developers.brightspace.com).

## Installation

`d2l-progress` can be installed from [Bower][bower-url]:
```shell
bower install d2l-progress
```

## Progress Styles

![screenshot of progress bar](/screenshots/progress.gif?raw=true)

## Usage

Progress styles can be applied using either [Polymer](https://www.polymer-project.org/1.0/) or [Sass](http://sass-lang.com/) mixins. Which one you use depends on your technology stack and comfort with each, however since Sass compiles to native CSS it's more performant.

### Sass

Import the main `d2l-progress.scss` file into your application's Sass. Then call the `d2l-progress()` mixin to define the styles of your `progress` element:

```sass
@import 'bower_components/d2l-progress/d2l-progress.scss';

progress.my-progress {
	@include d2l-progress();
}
```

### Polymer

Include the [webcomponents.js](http://webcomponents.org/polyfills/) "lite" polyfill (for browsers that don't natively support web components), import `d2l-progress.html`, and consume the required mixins in a custom style block:

```html
<head>
	<script src="https://s.brightspace.com/lib/webcomponentsjs/0.7.21/webcomponents-lite.min.js"></script>
	<link rel="import" href="../d2l-progress/d2l-progress.html">
	<custom-style>
		<style is="custom-style">
			progress.d2l-progress {
				@apply --d2l-progress;
			}
			/* etc. */
		</style>
	</custom-style>
</head>
```

## Coding styles

See the [Best Practices & Style Guide](https://github.com/Brightspace/valence-ui-docs/wiki/Best-Practices-&-Style-Guide) for information on naming conventions, plus information about the [EditorConfig](http://editorconfig.org) rules used in this repo.

[bower-url]: http://bower.io/search/?q=d2l-progress
[bower-image]: https://img.shields.io/bower/v/d2l-progress.svg
[ci-url]: https://travis-ci.org/BrightspaceUI/progress
[ci-image]: https://travis-ci.org/BrightspaceUI/progress.svg?branch=master
