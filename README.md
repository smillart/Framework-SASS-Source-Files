
# Framework SASS Source Files

![GitHub updated](https://img.shields.io/badge/Last%20updated-January%208,%202024-b83e3e.svg)
![Compatibility](https://img.shields.io/badge/Compatibility-Dart%20Sass%20%28since%201.23.0%29-3e59b8.svg)
[![GitHub release](https://img.shields.io/badge/Pre%20release-2.0.0%20%28beta1%29-35743b.svg)](https://github.com/smillart/Framework-SASS-Source-Files/releases/tag/2.0.0-beta1)

*Framework SASS Source Files* is a *Sass*-powered framework accomplished by **Sass variables, Sass maps, and utility CSS**. Ready to use, drop it right into your Sass powered applications.

The  *Framework SASS* source files are  **components-oriented**. It means that those should be abstract and decoupled enough that you can build new components quickly from existing parts without having to recode patterns. As new components and features are needed, it should be easy to add, modify and extend *CSS* without breaking (or refactoring) styles from the existing framework.

Utilize our *Framework SASS* source files to  [**take advantage of variables, maps, functions, mixins and more**](SASS-REFERENCE.md).

## Getting Started

### Installation

Download and extract the source files into the root of your project (theme): `./THEMENAME`. After it has been extracted, the directory should be renamed (if needed) so it reads `./THEMENAME/_sass-framework`.

If for whatever reason you have an additional `Framework-SASS-Source-Files-2.0.0-beta1` directory wrapping the first `Framework-SASS-Source-Files-2.0.0-beta1` directory (e.g. `./THEMENAME/Framework-SASS-Source-Files-2.0.0-beta1/Framework-SASS-Source-Files-2.0.0-beta1`), remove the wrapping `Framework-SASS-Source-Files-2.0.0-beta1` directory.

#### Sass Files Structure

Whenever possible, avoid modifying the *Framework SASS* source files (*functions, mixins, placeholders and variables* within the `_sass-framework` folder). For *Sass*, that means creating your own stylesheets that include the *Framework SASS* source files so you can modify and/or extend it. The *Sass* files structure, within your project (theme) folder, should look like this, keeping *Framework SASS* source files separate from your own:

```plaintext
./THEMENAME/
├── _sass-framework
│   ├── elements/
│   ├── helpers/
│   ├── layout/
│   ├── options/
│   ├── utilities/
│   └── ...
└── scss/
    ├── base
    ├── components
    ├── config
    │   └── _variable-overrides.scss
    ├── layout
    └── theme
```

## Customization

### CSS Variables (Experimental)

> [!TIP]
> The  *Framework SASS* source files include now many [**CSS custom properties (variables)**](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties) in their compiled *CSS* for real-time customization without the need to recompile *Sass*.
>
> These *CSS* variables are added across the `:root` level and all core elements/components. These provide easy access to commonly used values like the colors (scheme, theme, grayscale & state), spacings, breakpoints, and primary font stacks when working in your browser’s inspector, a code sandbox, or general prototyping.
>
> All the power of *Sass* is still there behind the scenes, but *CSS* variables adds a ton of power for the future. Use and compose new values, updates styles globally without recompiling, set fallback values, setup new color modes, and more.

### Loading Modules

> [!WARNING]
> The *Sass* team discourages the continued use of the `@import` rule. Sass will [gradually phase it out](https://github.com/sass/sass/blob/main/accepted/module-system.md#timeline) over the next few years, and eventually remove it from the language entirely. The *Framework SASS* source files are now using both the `@use` and the `@forward` rules instead. (Note that only [Dart Sass](https://sass-lang.com/dart-sass/) currently supports these rules. Users of other implementations must continue using the `@import` rule instead.)

In your own stylesheets, you will load mixins, functions, and variables using the `@use` rule from the *Framework SASS* source files, and combine *CSS* from multiple stylesheets together. Stylesheets loaded by `@use` are called "modules". *Sass* also provides [built-in modules](https://sass-lang.com/documentation/modules) full of useful functions.

The simplest `@use` rule is written `@use '<url>';` which loads the module at the given URL. Any styles loaded this way will be included exactly once in the compiled *CSS* output, no matter how many times those styles are loaded.

```scss
// ./THEMENAME/scss/base/_root.scss
// Load parts of the 'Sass Framwork' modules you need only.

@use '../../_sass-framework/helpers/units';
@use '../../_sass-framework/utilities/color';
@use '../../_sass-framework/utilities/font';

body {
  background-color: color.grayscale('100');
  color: color.grayscale('900');
  font: {
    size: units.rem(18px);
    weight: font.weight('medium');
  }
  ...
}
```

With that setup in place, you can begin to override any of the *Sass* variables and maps in your `_variable-overrides.scss`.

### Variable and Map defaults

Every *Sass* variable and map in the *Framework SASS* includes the `!default` flag allowing you to override the default value in your `_variable-overrides.scss` file without modifying the *Framework SASS* source code. Copy and paste variables or maps as needed, modify their values, and remove the `!default` flag. If a variable has already been assigned, then it won’t be re-assigned by the default values in the *Framework SASS*.

You will find the complete list of the *Framework SASS* variables and maps in the [***Framework SASS* source files reference**](SASS-REFERENCE.md) including the entire *variables, maps, mixins, functions and placeholders SassDoc*.

Variable or map overrides (within `_variable-overrides.scss`) must come before you load the *Framework SASS* modules.

Here’s an example that changes all `background-color`, `color`, `font-size` and `font-weight` values for the `<body>` element:

```scss
// ./THEMENAME/scss/config/_variable-overrides.scss
// Variable overrides for the "Body" styles:
@forward '../../_sass-framework/elements/body/base' with (
  $base-color: #212529,
  $base-background-color: #f8f9fa,
  $base-font-size: 18px,
  $base-font-weight: 500,
);
```

```scss
// ./THEMENAME/scss/base/_root.scss
// Load your own variable overrides first and then the 'Sass Framwork' module(s) you need.

@use '../config/variable-overrides';
@use '../../_sass-framework/elements/body';

body {
  @include body.styles;
  ...
}
```

To modify existing variables and/or add new ones in a *Sass* map (**e.g.** colors within the `$themes` *Sass* map), add the following to your `_variable-overrides.scss` file:

```scss
// ./THEMENAME/scss/config/_variable-overrides.scss
// Add your own (new) color variables:
$midnight: #0f5153;
$sap: #48782b;
$violet: #c0057a;

// Overrides and new variables for the "Theme color scheme" Sass map:
@forward '../../_sass-framework/utilities/color/themes' with (
  $themes: (
    'primary': $midnight,
    'energy': $sap,
    'intellectual-property': $violet,
  ),
);
```

To remove colors from `$themes`, or any other *Sass* map, use the [`map.remove()`](https://sass-lang.com/documentation/modules/map/#remove) *Sass Script function* from the [`sass:map`](https://sass-lang.com/documentation/modules/map/) *Sass Built-in module*:

```scss
// ./THEMENAME/scss/config/_variable-overrides.scss

@use 'sass:map';

// Remove "info", "light" and "dark" (key/value) from the "Theme color scheme" Sass map:
@forward '../../_sass-framework/utilities/color/themes' with (
  $themes: map.remove($themes, 'info', 'light', 'dark'),
);
```

### Required Keys

The *Framework SASS* assumes the presence of some specific keys within *Sass* maps as we used and extend these ourselves. As you customize the included maps, you may encounter errors where a specific *Sass* map’s key is being used.

For example, The *Framework SASS* uses the `primary`, `success`, and `danger` keys from the `$themes` *Sass* map for links, buttons, and form states. Replacing the values of these keys should present no issues, but removing them may cause *Sass* compilation issues.

## Recompile

When making any overrides to the *Framework SASS* variables, you will need to save your changes and recompile the entire *Sass* files. Doing so will output a brand new set of predefined look and feel. Make sure to output to the proper *CSS* file path:

```
sass compile scss/base/*.scss > css/base/*.css
sass compile scss/layout/*.scss > css/layout/*.css
sass compile scss/components/*.scss > css/components/*.css
sass compile scss/theme/*.scss > css/theme/*.css
```

After recompiling, you will automatically see your changes reflected in the *CSS* file... If everything went well ;-)
