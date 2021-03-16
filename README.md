
Framework SASS Source Files
==========

*Framework SASS Source Files* is a Sass-powered framework accomplished by **Sass variables, Sass maps, and utility CSS**. Ready to use, drop it right into your Sass powered applications.

The  *Sass Framework*  is  **components-oriented**. It means that those should be abstract and decoupled enough that you can build new components quickly from existing parts without having to recode patterns. As new components and features are needed, it should be easy to add, modify and extend CSS without breaking (or refactoring) styles from the existing framework.

Utilize our  _Sass Framework_  files to  [**take advantage of variables, maps, mixins and more**](SASS-REFERENCE.md).

## Installation *(within your Drupal sub-theme folder)*

Download and extract the source files into the root of your new sub-theme: `./themes/custom/THEMENAME`. After it has been extracted, the directory should be renamed (if needed) so it reads `./themes/custom/THEMENAME/_sass-framework`.

If for whatever reason you have an additional `Framework-SASS-Source-Files-1.0.1` directory wrapping the first `Framework-SASS-Source-Files-1.0.1` directory (e.g. `./themes/THEMENAME/Framework-SASS-Source-Files-1.0.1/Framework-SASS-Source-Files-1.0.1`), remove the wrapping `Framework-SASS-Source-Files-1.0.1` directory.

### Sass files structure

Whenever possible, avoid modifying the *Framework SASS* source files (*functions, mixins, placeholders and variables* within the `_sass-framework` folder) source files. For Sass, that means creating your own stylesheets that import the *Framework SASS* source files so you can modify and/or extend it. The Sass files structure, within your sub-theme folder, should look like this, keeping *Framework SASS* source files separate from your own:

```plaintext
./themes/custom/THEMENAME/
├── _sass-framework
│   ├── functions/
│   ├── mixins/
│   ├── placeholders/
│   ├── variables/
│   ├── ...
│   └── _include-all.scss
└── scss/
    ├── base
    ├── components
    ├── config
    │   ├── _imports.scss
    │   └── _variable-overrides.scss
    ├── layout
    └── theme
```

## Importing

In your `_imports.scss`, you will import *Framework SASS* source files. You have two options: Include the full import stack (*A*), or pick the parts you need (*B*). We encourage option *A*, because your have to be aware there are some requirements and dependencies across our components.

```scss
// _imports.scss
// Option A: Include all of the 'Framwork SASS' source files

@import '../../_sass-framework/include-all';
```

```scss
// _imports.scss
// Option B: Include parts of the 'Sass Framwork' you need

@import '../../_sass-framework/functions/helpers/general';
@import '../../_sass-framework/variables/options';
@import '../../_sass-framework/variables/colors';
@import '../../_sass-framework/variables/base';
@import '../../_sass-framework/mixins/typography/general';
```

With that setup in place, you can begin to override any of the Sass variables and maps in your `_variable-overrides.scss`.

## Variable and map defaults

Every Sass variable and map in the *Framework SASS* includes the `!default` flag allowing you to override the default value in your `_variable-overrides.scss` file without modifying the *Framework SASS* source code. Copy and paste variables or maps as needed, modify their values, and remove the `!default` flag. If a variable has already been assigned, then it won’t be re-assigned by the default values in the *Framework SASS*.

You will find the complete list of the *Framework SASS* variables and maps in the `_sass-framework/variables/` folder and in the [**Sass reference**](SASS-REFERENCE.md) including the entire *variables, maps, mixins, functions and placeholders SassDoc*.

Variable or map overrides (within `_variable-overrides.scss`) must come before you import the *Framework SASS* source Sass files (within `_imports.scss`).

Here’s an example that changes the `background-color` and `color` for the `<body>`:

```scss
// _variable-overrides.scss
// Both variable overrides for the 'background-color' and 'color' CSS properties:
$body-base-color: $gray-900; // #212529
$body-base-background-color: $gray-100; // #f8f9fa
```

```scss
// _imports.scss
// Your own variable overrides defined here above:
@import 'variable-overrides';
// The 'Sass Framework' and its default variables:
@import '../../_sass-framework/include-all';
```

To modify existing colors and/or add new ones in the `$theme-colors` map, add the following to your `_variable-overrides.scss` file:

```scss
// _variable-overrides.scss
// Override default 'Framework SASS' colors:
$red: #d13416;
$green: #48782b;
$cyan: #0372d1;
$orange: #c34c09;
// Add your own colors:
$midnight: #0f5153;
$sap: #48782b;
$violet: #c0057a;

// Your overrides and new colors for the "Theme color scheme" map:
$theme-colors: (
  'primary': $midnight,
  'energy': $sap,
  'intellectual-property': $violet,
);
```

To remove colors from `$theme-colors`, or any other map, use the `map-remove` *Sass Script function* (within separate file `_map-removals.scss` for example) . Be aware you must insert it after you import *Sass Framework* source Sass files: 

```scss
// _map-removals.scss
// Remove "info", "light" and "dark" (key/value) from the "Theme color scheme" map:
$theme-colors: map-remove($theme-colors, 'info', 'light', 'dark');
```

```scss
// _imports.scss
// The 'Framework SASS' and its default variables
@import '../../_sass-framework/include-all';
// Your map removals defined here above:
@import 'map-removals';
```

### Required keys

The *Framework SASS* assumes the presence of some specific keys within Sass maps as we used and extend these ourselves. As you customize the included maps, you may encounter errors where a specific Sass map’s key is being used.

For example, The *Framework SASS* uses the `primary`, `success`, and `danger` keys from `$theme-colors` for links, buttons, and form states. Replacing the values of these keys should present no issues, but removing them may cause Sass compilation issues.

## Recompile

When making any overrides to the *Framework SASS* variables, you will need to save your changes and recompile the entire Sass files. Doing so will output a brand new set of predefined look and feel. Make sure to output to the proper CSS file path:

```
sass compile scss/base/*.scss > css/base/*.css
sass compile scss/layout/*.scss > css/layout/*.css
sass compile scss/components/*.scss > css/components/*.css
sass compile scss/theme/*.scss > css/theme/*.css
```
**Here after is an example of the `.scss` file containing the default root styles:**

```scss
// @file scss/base/elements/root.scss
// Remember you changed previously the `background-color` and `color` for the `<body>`.

// Import Sass variables, functions, mixins and placeholders.
@import  '../../config/imports';

// Page body
//
body {
  @include background($color: $body-base-background-color);
  color: $body-base-color;
  font: {
    @include rem('size', $body-base-font-size);
    family: $body-base-font-family;
    weight: $body-base-font-weight;
  }
  line-height: $body-base-line-height;
}
```

After recompiling, you will automatically see your changes reflected in the CSS file... If everything went well ;-)