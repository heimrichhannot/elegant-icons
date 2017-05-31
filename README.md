# Elegant Icon Font

Composer/Component Package to provide the famous elegant icon font library containin 360 icons with less support. Created by: http://www.elegantthemes.com/blog/resources/elegant-icon-font

## Icon list

See demo/demo.html for full list of icons or visit http://www.elegantthemes.com/blog/resources/elegant-icon-font.

## Sass Usage

1. Import elegant-icons-sass in your code:

```
@import 'elegant-icons-sass';
```

> By default, only the `woff` and `woff2` formats ([Why?](http://caniuse.com/#search=woff)) of the fonts will be pulled from a CDN (using [RawGit](https://rawgit.com/)). If you want to use different formats and/or local fonts, check the [**Customization**](#customization) section below.

## Usage

To use the icons, you will need their names, which you can find [here](https://www.elegantthemes.com/blog/resources/elegant-icon-font) (right after the unicode reference list).

> The unicode references of the above list are meant to be used as `data-icon`, which the support has been removed in this sass version, because it‘s considered a bad practice due to performance issues. If you wish to use this way, you must define it yourself.

> On the list, you will find that almost all icons have an `icon_` prefix in their names, which seems to be redundant and unnecessary. In this Sass version, you can omit it (as done in the exemples below), but for backwards compatibility they are still valid selectors for all usage types (mixin, placeholder or class).

> By default, the icon will be defined as a `::before` pseude-element. If you wish to change this default, check the [**Customization**](#customization) section below.

### As a mixin

Include the mixin in your selector:

```scss
.my-selector {
  @include elegant-icon('arrow_up');  
}
```

You can override the icon's default placement by passing it as a second parameter:

```scss
.my-selector {
  @include elegant-icon('question', 'after');  
}
```

### As a placeholder

Extend the your selector with the placeholder:

```scss
.my-selector {
  @extend %ei-contacts_alt;
}
```

> When using as a placeholder, the prefix `ei-` must be used. Check the [**Customization**](#customization) section below on how to change or remove this prefix.

### As a class

If you just want to use it as a class, you **MUST ACTIVATE** the class generation first (Check the [**Customization**](#customization) section below on how to activate it.)

After activated, you can simply set the icon class name to your html element:

```html
<span class="ei-plus"></span>
```

> When using as a class, the prefix `ei-` must be used. Check the [**Customization**](#customization) section below on how to change or remove this prefix.

## Customization

This sass version of the Elegant Icons defines a few defaults, which are considered best practices or common use cases. If you wish to override them, here is how:

  > The overrides below, must be done **BEFORE** the import explained in the Step 2 of the [Usage](#usage) section.

### Activate class selectors

```scss
$ei-generate-classes: true;

// Default value: false
```

### Using a different selector prefix:

```scss
$ei-icon-prefix: 'my-prefix-';

// Default value: 'ei-'
```

> If you don‘t want to use a prefix, set it to an empty string: `$ei-icon-prefix: '';`

### Set the icons placement as `::after`:

```scss
$ei-default-placement: 'after';

// Default value: 'before'
```

> The `$ei-default-placement` variable can only be set as 'before' or 'after' which will define it as a `::before` or an `::after` pseudo-element, respectively.

### Using different font formats:

```scss
// All formats:
$ei-font-formats: eot woff2 woff ttf svg;

// Default value: woff woff2
```

> You can define any formats combination that you need from the available formats on example list above.

### Using local fonts

1. Activate the local font usage:
  ```scss
  $ei-use-local-fonts: true;
  ```
2. Override the font path variable:
  ```scss
  // Example:
  $ei-font-path: '../assets/fonts/elegant-icons/';

  // Default value: '/fonts'
  ```
  > Please note that the path above must be relative to the generated `CSS` file, since it is used as a normal `src: url()` in an `@font-face` definition.

3. (Optionally) change the font file name:

  ```scss
  $ei-font-filename: 'my-custom-icons-filename';

  // Default value: 'ElegantIcons'
  ```

  > If you‘re just copying the font files and not renaming them, don‘t override this.

4. (Optionally) change the font family name:

  ```scss
  $ei-font-family: 'My-Custom-Icons-Family-Name';

  // Default value: 'ElegantIcons'
  ```

  > Override only if you somehow wish to have a different font-family name defined to the icons font.

> You might need to copy the font files yourself from the `node_modules/elegant-icons-sass/fonts` folder. You can use your build system of choice for that.

## Original image files

The original image files (in SVG and PNG) can be found in the repo's [image folder](https://github.com/mdentinho/elegant-icons-sass/tree/master/images).
