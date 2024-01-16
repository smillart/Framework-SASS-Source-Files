
Sass Reference
==========

Utilize our [*Framework SASS*](README.md) files to take advantage of the following *functions*, *placeholders*, *mixins*, *variables* and *maps*.

## Modules

|#      | Options    | Utilities                | Helpers   | Layout         | Elements    |
|:------|:-----------|:-------------------------|:----------|:---------------|:------------|
| **1** | [Enable](#enable) | [Color]()                | [Units]() | [Breakpoint]() | [Root]()    |
| **2** |            | [Background]()           | [Float]() | [Grid]()       | [Body]()    |
| **3** |            | [Background Direction]() | [A11y]()  |                | [Heading]() |
| **4** |            | [Border]()               | [CSS]()   |                | [Link]()    |
| **5** |            | [Display]()              |           |                | [Table]()   |
| **6** |            | [Effect]()               |           |                | [List]()    |
| **7** |            | [Font]()                 |           |                | [Form]()    |
| **8** |            | [Font Awesome]()         |           |                | [Button]()  |
| **9** |            | [Spacing]()              |           |                |             |

## Options

### Enable

#### Variable(s) `!default`

* [`$css-variables`]()  
Enable or disable the CSS variables.

* [`$rounded`]()  
Enable or disable the border radius on components.

* [`$shadows`]()  
Enable or disable the box shadow on components.

* [`$transitions`]()  
Enable or disable the transitions when components state changes.

* [`$grid-classes`]()  
Enable or disable the Grid Sytem classes.

* [`$legacy-support-for-ie6`]()  
Enable or disable the browser support to the legacy IE6.

* [`$legacy-support-for-ie7`]()  
Enable or disable the browser support to the legacy IE7.

* [`$legacy-support-for-ie8`]()  
Enable or disable the browser support to the legacy IE8.

* [`$legacy-support-for-ie9`]()  
Enable or disable the browser support to the legacy IE9.

* [`$legacy-support-for-ie10`]()  
Enable or disable the browser support to the legacy IE10.

* [`$legacy-support-for-ie11`]()  
Enable or disable the browser support to the legacy IE11.

## Utilities

### Color

#### Variable(s) `!default`

* [`$blue`](), [`$indigo`](), [`$purple`](), [`$pink`](), [`$red`](), [`$orange`](), [`$green`](), [`$teal`](), [`$cyan`]()  
Define all colors as consistent color scheme for use across the theme.

* [`$gray-100`](), [`$gray-200`](), [`$gray-300`](), [`$gray-400`](), [`$gray-500`](), [`$gray-600`](), [`$gray-700`](), [`$gray-800`](), [`$gray-900`]()  
Define all grayscales as consistent shades of gray for use across the theme.

* [`$schemes`]()  
Map of default color scheme.

* [`$grayscales`]()  
Map of shades of gray.

* [`$themes`]()  
Map of theme color scheme.

* [`$color-states`]()  
Map of common text color states used by the components.

#### Function(s)

* [`@function scheme($key) { ... }`]()  
Retreive a color from the "Default color scheme" Sass map.

* [`@function grayscale($key) { ... }`]()  
Retreive a color from the "Shades of gray" Sass map.

* [`@function theme($key) { ... }`]()  
Retreive a color from the "Theme color scheme" Sass map.

* [`@function state($state) { ... }`]()  
Retrieve a text color state from the "Colors states" Sass map.

### Background

#### Variable(s) `!default`

* [`$image-retina-fallback`]()  
Enable or disable the retina fallback for images.

* [`$image-folder-path`]()  
The default path to the image folder.

* [`$image-fallback-extension`]()  
The default file extension for images.

* [`$image-retina-media-query`]()  
The retina display media query string.

* [`$image-retina-suffix`]()  
The default suffix for images with retina fallback.

* [`$background-states`]()  
Map of common background color states used by the components.

#### Function(s)

* [`@function state($state) { ... }`]()  
Retrieve a background color state from the "Background colors states" Sass map.

#### Mixin(s)

* [`@mixin image($color, $name, $size, [...]) { ... }`]()  
Mixin for background images with retina fallback.

* [`@mixin gradient($direction, $color-stops...) { ... }`]()  
Mixin for background gradient.

### Background Direction

#### Variable(s) `!default`

* [`$direction`]()  
Background direction value.

#### Function(s)

* [`@function legacy($value) { ... }`]()  
Convert a direction to legacy syntax.

* [`@function is-valid($value) { ... }`]()  
Test if `$value` is a valid direction.

### Border

#### Variable(s) `!default`

* [`$colors`]()  
Map of common border color brightnesses used by the components.

* [`$radiuses`]()  
Map of common border radius sizes used by the components.

* [`$border-states`]()  
Map of common border color states used by the components.

#### Function(s)

* [`@function color($brightness) { ... }`]()  
Retrieve a border color brightness from the "Border colors" Sass map.

* [`@function radius($size) { ... }`]()  
Retrieve a border radius size from the "Border radiuses" Sass map.

* [`@function state($state) { ... }`]()  
Retrieve a border color state from the "Colors states" Sass map.

### Display

#### Mixin(s)

* [`@mixin flex($aligns, $flow) { ... }`]()  
Flexbox Layout

### Effect

#### Variable(s) `!default`

* [`$shadows`]()  
Map of common shadow properties used by the components.

* [`$transitions`]()  
Map of common transition properties used by the components.

#### Function(s)

* [`@function shadow($key, $type) { ... }`]()  
Retrieve a shadow property from the "Shadows" Sass map.

* [`@function transition($key) { ... }`]()  
Retrieve a transition property from the "Transitions" Sass map.

### Font

#### Variable(s) `!default`

* [`$families`]()  
Map of default font families.

* [`$weights`]()  
Map of common font thicknesses used by the components.

#### Function(s)

* [`@function family($font) { ... }`]()  
Retrieve a font family from the "Font families" Sass map.

* [`@function weight($thickness) { ... }`]()  
Retrieve a font thickness from the "Font weights" Sass map.

### Font Awesome

#### Variable(s) `!default`

* [`$icons`]()  
Font Awesome Free 6.2.0 Icons Library

#### Placeholder(s)

* [`@extend %icon-defaults`]()  
Font Awesome Icons default properties.

* [`@extend %icon-regular-defaults`]()  
Font Awesome "Regular" Icons properties.

* [`@extend %icon-solid-defaults`]()  
Font Awesome "Solid" Icons properties.

* [`@extend %icon-brands-defaults`]()  
Font Awesome "Brands" Icons properties.

#### Mixin(s)

* [`@mixin icon($name, $type, $position) { ... }`]()  
Font Awesome Free 6.2.0

### Spacing

#### Variable(s) `!default`

* [`$spacer`]()  
Default spacing value.  
Assumes the browser default, typically `16px`.

* [`$spacers`]()  
Map of common spacing values.

* [`$margins`]()  
Map of common margin sizes used by the components.

* [`$paddings`]()  
Map of common vertical & horizontal padding sizes used by the components.

#### Function(s)

* [`@function spacer($key, $multiplier) { ... }`]()  
Retrieve a variation from the "Spacing" Sass map.

* [`@function margin($size) { ... }`]()  
Retrieve a component rhythm from the "Margins" Sass map.

* [`@function padding($size, $orientation) { ... }`]()  
Retrieve a component rhythm from the "Paddings" Sass map.

## Helpers

### Units

#### Function(s)

* [`@function strip($number) { ... }`]()  
Strips the units from a value.

* [`@function rem($values, $root, $fallback) { ... }`]()  
Function to convert "px" to "rem" value.

#### Mixin(s)

* [`@mixin rem($property, $values, $root) { ... }`]()  
Generate CSS property with the "px/rem" value which is relative to the font-size defined for the html element.

### Float

#### Placeholder(s)

* [`@extend %clearfix-defaults`]()  
Float clearing default properties.

#### Mixin(s)

* [`@mixin clearfix($extend) { ... }`]()  
Provides an easy way to include a clearfix for containing floats.

### A11y

#### Placeholder(s)

* [`@extend %visually-hidden-defaults`]()  
Content to screen readers default properties.

* [`@extend %focusable-defaults`]()  
Focused content default properties.

#### Mixin(s)

* [`@mixin visually-hidden($extend) { ... }`]()  
Only display content to screen readers.

* [`@mixin focusable($extend) { ... }`]()  
Only display content when it’s focused.

### CSS

#### Variable(s) `!default`

* [`$selectors`]()  
Map of default component CSS selectors.

#### Function(s)

* [`@function selector($selector) { ... }`]()  
Retreive a CSS selector from the "CSS selectors" Sass map.

## Layout

### Breakpoint

#### Variable(s) `!default`

* [`$breakpoints`]()  
Grid breakpoints.

#### Function(s)

* [`@function infix($name, $breakpoints) { ... }`]()  
Retreive a blank string if smallest (xsmall) breakpoint, otherwise returns the name with a dash infront.

* [`@function max($name, $breakpoints) { ... }`]()  
Retreive the maximum breakpoint width.

* [`@function min($name, $breakpoints) { ... }`]()  
Retreive the minimum breakpoint width.

* [`@function next($name, $breakpoints) { ... }`]()  
Retreive the name of the next breakpoint.

#### Mixin(s)

* [`@mixin up($name, $breakpoints) { ... }`]()  
Generate Media Query of at least the minimum breakpoint width.

* [`@mixin down($name, $breakpoints) { ... }`]()  
Generate Media Query of at most the maximum breakpoint width.

* [`@mixin between($lower, $upper, $breakpoints) { ... }`]()  
Generate Media Query that spans multiple breakpoint widths.

### Grid

#### Variable(s) `!default`

* [`$columns`]()  
Grid columns

* [`$gutter-width`]()  
Grid gutter width

* [`$containers`]()  
Define the maximum width of `.container` for different screen sizes.

#### Placeholder(s)

* [`extend %container-defaults`]()  
Grid container default properties.

* [`extend %row-defaults`]()  
Grid row default properties.

* [`extend %column-ready-defaults`]()  
Grid column (Next, apply the paddings) default properties.

#### Mixin(s)

* [`@mixin container($gutter, $css-variables) { ... }`]()  
Generate container width, and override it in media queries.

* [`@mixin container-max-widths($containers, $breakpoints, $css-variables) { ... }`]()  
For each breakpoint, define the maximum width of the container in a media query.

* [`@mixin row($gutter, $css-variables) { ... }`]()  
Generate a row (wrapper) for a series of columns.

* [`@mixin row-reset($css-variables) { ... }`]()  
Reset grid row.

* [`@mixin column-ready($gutter, $css-variables) { ... }`]()  
Make the element grid-ready (applying everything but the width).

* [`@mixin column($size, $css-variables) { ... }`]()  
Generate specific width that span multiple columns.

* [`@mixin column-offset($size, $columns, $css-variables) { ... }`]()  
Move columns to the right by increasing the left margin of a column by * columns.

* [`@mixin column-order($position, $columns, $css-variables) { ... }`]()  
Easily control the visual order of your columns.

## Elements

### Root

#### Mixin(s)

* [`@mixin colors { ... }`]()  
Generate default CSS variables for full colors, grays, and theme colors.

* [`@mixin fonts { ... }`]()  
Generate default CSS font variables for families and weights.

* [`@mixin spacings { ... }`]()  
Generate default CSS spacing variables for margins and paddings.

* [`@mixin grid-system { ... }`]()  
Generate default CSS layout variables for the grid system.

### Body

#### Variable(s) `!default`

* [`$base-color`]()  
The base text color applied on the document body.

* [`$base-background-color`]()  
The base background color applied on the document body.

* [`$base-font-family`]()  
The base font family applied on the document body.

* [`$base-font-size`]()  
The base font size applied on the document body.  
Assumes the browser default, typically `16px`.

* [`$base-font-weight`]()  
The base font weight applied on the document body.

* [`$base-line-height`]()  
The base text line height applied on the document body.

#### Mixin(s)

* [`@mixin styles($background-color, $color, $font-size, [...]) { ... }`]()  
Easily inject default styles for the document body.

### Heading

#### Variable(s) `!default`

* [`$heading-margin-bottom`]()  
The default bottom margin size applied on all headings.

* [`$heading-font-weight`]()  
The default font thickness applied on all headings.

* [`$heading-font-weight`]()  
The default font thickness applied on all headings.

* [`$font-sizes`]()  
Map of common font sizes applied on each heading type.

#### Function(s)

* [`@function font-size($heading) { ... }`]()  
Retrieve a font size from the "Heading common font sizes" Sass map.

#### Mixin(s)

* [`@mixin styles($margin-bottom, $font-weight, $line-height, [...]) { ... }`]()  
Easily inject default styles for all headings.

### Link

#### Variable(s) `!default`

* [`$link-color`]()  
The default state for the link color.

* [`$link-hover-color`]()  
The hovered state for the link color.

* [`$link-visited-color`]()  
The visited state for the link color.

* [`$link-text-decoration`]()  
The default decoration for the link.

* [`$link-hover-text-decoration`]()  
The hovered decoration for the link.

#### Mixin(s)

* [`@mixin styles($color, $hover-color, $visited-color, [...]) { ... }`]()  
Easily inject default styles for the text links.

### Table

#### Variable(s) `!default`

* [`$table-margin-bottom`]()  
The default bottom margin size applied on data tables.

* [`$table-background-color`]()  
The default background color applied on data tables.

* [`$table-border-width`]()  
The default border width applied on (bordered) data tables.

* [`$table-border-color`]()  
The default border color applied on (bordered) data tables.

* [`$table-nested-margin-bottom`]()  
The default bottom margin size applied on nested data tables.

* [`$table-nested-background-color`]()  
The default background color applied on nested data tables.

* [`$table-cell-padding`]()  
The default padding size applied on data table cells.

* [`$table-cell-background-color`]()  
The default background color applied on data table rows (cells) when striped/hovered.

* [`$table-caption-color`]()  
The default text color applied on data table captions.

* [`$table-caption-padding-top`]()  
The default top padding size applied on data table captions.

* [`$table-caption-padding-bottom`]()  
The default bottom padding size applied on data table captions.

* [`$table-caption-side`]()  
The default side position applied on data table captions.

* [`$flow-rules`]()  
Map of the CSS rules applied on bordered data tables.

#### Mixin(s)

* [`@mixin styles($margin-bottom, $background-color, $nested-margin-bottom, [...]) { ... }`]()  
Easily inject default styles for data tables.

* [`@mixin striped($flow, $order, $cell-background-color, [...]) { ... }`]()  
Add zebra-striping to any table row (or column).

* [`@mixin hoverable($cell-hover-background-color, $css-variables) { ... }`]()  
Enable a hover state on table rows within a `<tbody>`.

* [`@mixin bordered($flow, $border-width, $border-color, [...]) { ... }`]()  
Add borders all around the table and/or between all the rows/columns.

### List

#### Variable(s) `!default`

* [`$list-padding-left`]()  
The default left padding size applied on all lists.

* [`$list-margin-bottom`]()  
The default bottom margin size applied on all lists.

* [`$list-unstyled-padding-left`]()  
The default left padding applied on unstyled lists.

* [`$list-inline-padding-left`]()  
The default left padding applied on both inline/inline block lists.

* [`$list-inline-block-item-vertical-align`]()  
The default vertical alignment applied on inline list items.

* [`$list-inline-item-margin-left`]()  
The default left margin applied on both inline/inline-block list items (Except the first child).

#### Mixin(s)

* [`@mixin styles($padding-left, $margin-bottom, $css-variables) { ... }`]()  
Easily set out default styles for all lists.

* [`@mixin unstyled($padding-left, $css-variables) { ... }`]()  
Easily unstyle a specific list.

* [`@mixin inline($item-margin-left, $css-variables) { ... }`]()  
Easily set out a specific list inline.

* [`@mixin inline-block($item-vertical-align, $item-margin-left, $css-variables) { ... }`]()  
-

### Form

#### Variable(s) `!default`

* [`$form-element-enable-rounded`]()  
Enable/disable by default the border radius on form elements.

* [`$form-element-enable-shadows`]()  
Enable/disable by default the box shadow on form elements.

* [`$form-element-enable-transitions`]()  
Enable/disable by default the transitions when form elements state changes.

* [`$form-element-enable-native-appearance`]()  
Enable/disable by default the native appearance of form elements.

* [`$form-element-color`]()  
The default text color to be applied on form elements.

* [`$form-element-background-color`]()  
The default background color to be applied on form elements.

* [`$form-element-border-width`]()  
The default border width to be applied on form elements.

* [`$form-element-border-color`]()  
The default border color to be applied on form elements.

* [`$form-element-border-radius`]()  
The default border radius size to be applied on form elements.

* [`$form-element-disabled-color`]()  
The default text color to be applied on form elements when disabled.

* [`$form-element-disabled-background-color`]()  
The default background color to be applied on form elements when read-only and/or disabled.

* [`$form-element-disabled-border-color`]()  
The default border color to be applied on form elements when read-only and/or disabled.

* [`$form-control-vertical-padding`]()  
The default top/bottom (vertical) padding size to be applied on form controls.

* [`$form-control-horizontal-padding`]()  
The default right/left (horizontal) padding size to be applied on form controls.

* [`$form-control-font-size`]()  
The default font size to be applied on form elements.

* [`$form-control-font-weight`]()  
The default font weight to be applied on form controls.

* [`$form-control-line-height`]()  
The default text line height to be applied on form elements.

* [`$form-control-placeholder-color`]()  
The default text color to be applied for placeholders on form controls.

* [`$form-element-theme-background-color`]()  
The default background color to be applied on themed form elements.

* [`$form-file-selector-button-color`]()  
The default text color to be applied on file input buttons.

* [`$form-file-selector-button-background-color`]()  
The default background color to be applied on file input buttons.

* [`$form-select-background-position`]()  
The default position (offsets from bottom and/or right edges) of the background image to be used as form select indicator.

* [`$form-select-background-size`]()  
The default size of the background image to be used as form select indicator.

* [`$form-check-margin-right`]()  
The default right margin size to be applied on form check-list types.

* [`$form-check-checked-background-size`]()  
The default background image size to be applied on form check-list types (when checked).

* [`$form-element-theme-border-color`]()  
The default border color to be applied on themed form elements.

* [`$form-element-theme-transition`]()  
The default transition properties to be applied on themed form elements.

#### Placeholder(s)

* [`%form-defaults { ... }`]()  
Form control default properties.

#### Mixin(s)

* [`@mixin styles($rounded, $native-appearance, $color, [...]) { ... }`]()  
Easily inject default styles for all form elements.

* [`@mixin control($vertical-padding, $horizontal-padding, $font-size, [...]) { ... }`]()  
Easily inject specific styles for all form controls.

* [`@mixin select($background-image-name, $background-image-extension, $background-image-path, [...]) { ... }`]()  
Easily inject specific styles for all form selects.

* [`@mixin textarea($min-height, $css-variables) { ... }`]()  
Easily inject specific styles for all form textareas.

* [`@mixin file($selector-button-vertical-padding, $selector-button-horizontal-padding, $selector-button-border-inline-end-width, [...]) { ... }`]()  
Easily inject specific styles for all form file uploads.

* [`@mixin check($checkbox-checked-background-image-name, $checkbox-checked-background-image-extension, $checkbox-checked-background-image-path, [...]) { ... }`]()  
Easily inject specific styles for all (un)limited check-list type.

* [`@mixin theme($theme, $background-color, $border-color, [...]) { ... }`]()  
Easily set out theme color styles on a specific form element.  
Note: This mixin can have effect on `<input>`s, `<textarea>`s and `<select>`s.

### Button

#### Variable(s) `!default`

* [`Aaa`]()  
-

#### Placeholder(s)

* [`Aaa`]()  
-

#### Mixin(s)

* [`Aaa`]()  
-
