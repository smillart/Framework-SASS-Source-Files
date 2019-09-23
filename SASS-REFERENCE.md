
Sass Reference
==========

Utilize our [*Framework SASS*](README.md) files to take advantage of the following *functions*, *placeholders*, *mixins*, *variables* and *maps*.

## Helpers

### General

#### Functions

* [`contains-number($values)`](functions/helpers/general/_contains-number.scss) :  
Checks if a list contains a number(s).

* [`strip-units($value)`](functions/helpers/general/_strip-units.scss) :  
Strips the units from a value.

* [`is-direction($value)`](functions/helpers/general/_direction.scss) :  
Test if `$value` is a valid direction.

* [`legacy-direction($value)`](functions/helpers/general/_direction.scss) :  
Convert a direction to legacy syntax.

#### Placeholders

* [`%clearfix-defaults`](placeholders/helpers/general/_clearfix.scss) :  
Float clearing default properties.

* [`%screen-reader-only-defaults`](placeholders/helpers/general/_screen-readers-only.scss) :  
Content to screen readers default properties.

* [`%screen-reader-only-focusable-defaults`](placeholders/helpers/general/_screen-readers-only.scss) :  
Focused content default properties.

#### Mixins

* [`clearfix($extend)`](mixins/helpers/general/_clearfix.scss) :  
Provides an easy way to include a clearfix for containing floats.

* [`visually-hidden($extend)`](mixins/helpers/general/_screen-readers-only.scss) :  
Only display content to screen readers.

* [`focusable($extend)`](mixins/helpers/general/_screen-readers-only.scss) :  
Only display content when it's focused.

### Color

#### Functions

* [`color($key)`](functions/helpers/color/_color-scheme.scss) :  
Retreive a color from the "*All colors*" Sass map.

* [`theme-color($key)`](functions/helpers/color/_color-scheme.scss) :  
Retreive a color from the "*Theme colors*" Sass map.

* [`grayscale($key)`](functions/helpers/color/_color-scheme.scss) :  
Retreive a color from the "*Grayscales*" Sass map.

### Media

#### Mixins

* [`background($color, $image, $image-size, $image-path, $image-extension, $image-repeat, ...)`](mixins/helpers/media/_background.scss) :  
Mixin for background images with retina fallback.

* [`background-gradien($direction, $color-stops...)`](mixins/helpers/media/_background-gradient.scss) :  
Mixin for background gradient.

## Layout

### General

#### Functions

* [`breakpoint-next($name, $breakpoints, $breakpoint-names)`](functions/layout/general/_breakpoint.scss) :  
Retreive the name of the next breakpoint.

* [`breakpoint-min($name, $breakpoints)`](functions/layout/general/_breakpoint.scss) :  
Retreive the minimum breakpoint width.

* [`breakpoint-max($name, $breakpoints)`](functions/layout/general/_breakpoint.scss) :  
Retreive the maximum breakpoint width.

* [`breakpoint-infix($name, $breakpoints)`](functions/layout/general/_breakpoint.scss) :  
Retreive a blank string if smallest (xsmall) breakpoint, otherwise returns the name with a dash infront.

#### Mixins

* [`breakpoint-up($name, $breakpoints)`](mixins/layout/general/_breakpoint.scss) :  
Generate Media Query of at least the minimum breakpoint width.

* [`breakpoint-down($name, $breakpoints)`](mixins/layout/general/_breakpoint.scss) :  
Generate Media Query of at most the maximum breakpoint width.

* [`breakpoint-between($lower, $upper, $breakpoints)`](mixins/layout/general/_breakpoint.scss) :  
Generate Media Query that spans multiple breakpoint widths.

* [`breakpoint($name, $breakpoints)`](mixins/layout/general/_breakpoint.scss) :  
Generate Media Query between the breakpoint's minimum and maximum widths.

* [`flex($aligns, $flow)`](mixins/layout/general/_flex.scss) :  
Quickly manage the layout, alignment of navigation, components, and more with a full suite of flexbox utilities.

### Grid System

#### Placeholders

* [`%container-defaults`](placeholders/layout/grid-system/_grid.scss) :  
Grid container default properties.

* [`%row-defaults`](placeholders/layout/grid-system/_grid.scss) :  
Grid row default properties.

* [`%row-reset-defaults`](placeholders/layout/grid-system/_grid.scss) :  
Reset grid row default properties.

* [`%column-defaults`](placeholders/layout/grid-system/_grid.scss) :  
Grid column default properties.

* [`%column-ready-defaults`](placeholders/layout/grid-system/_grid.scss) :  
Grid column (with paddings) default properties.

#### Mixins

* [`make-container($gutter)`](mixins/layout/grid-system/_grid.scss) :  
Generate container width, and override it in media queries.

* [`make-container-max-widths($max-widths, $breakpoints)`](mixins/layout/grid-system/_grid.scss) :  
For each breakpoint, define the maximum width of the container in a media query.

* [`make-row($gutter)`](mixins/layout/grid-system/_grid.scss) :  
Generate a row (wrapper) for a series of columns.

* [`make-column-ready($gutter)`](mixins/layout/grid-system/_grid.scss) :  
Make the element grid-ready (applying everything but the width).

* [`make-column($size, $columns)`](mixins/layout/grid-system/_grid.scss) :  
Generate specific width that span multiple columns.

* [`make-column-offset($offset, $columns)`](mixins/layout/grid-system/_grid.scss) :  
Move columns to the right by increasing the left margin of a column by * columns.

* [`make-column-order($order, $columns)`](mixins/layout/grid-system/_grid.scss) :  
Easily control the visual order of your columns.

## Library

### General

#### Mixins

* [`abbreviation-variant($style, $abbreviation-initialism-font-size)`](mixins/library/general/_abbreviations.scss) :  
Easily set out variant styles on a specific abbreviation.

* [`button($rounded, $transition, $shadow, $button-vertical-padding, $button-horizontal-padding, ...)`](mixins/library/general/_buttons.scss) :  
Easily set out default styles for all buttons.

* [`button-variant($style, $shadow, $button-variant-color, $button-variant-darken-pourcentage)`](mixins/library/general/_buttons.scss) :  
Easily set out variant styles on a specific button.

* [`form-control($rounded, $transition, $shadow, $form-control-vertical-padding, ...)`](mixins/library/general/_forms.scss) :  
Easily set out default styles for all form controls.

* [`form-check($transition, $shadow, $form-check-label-padding-left, ...)`](mixins/library/general/_forms.scss) :  
Easily set out default styles for all (un)limited check-list type.

* [`headings($$headings-margin-bottom, $headings-font-weight)`](mixins/library/general/_headings.scss) :  
Easily set out default styles for all headings.

* [`item-list-variant($style)`](mixins/library/general/_item-list.scss) :  
Easily set out variant styles on a specific item list.

* [`lists($lists-padding-left, $lists-margin-bottom)`](mixins/library/general/_lists.scss) :  
Easily set out default styles for all lists.

* [`list-variant($style, $unstyled-padding-left, $inline-item-vertical-align, $inline-item-margin-left)`](mixins/library/general/_lists.scss) :  
Easily set out variant styles for all kind of lists.

* [`paragraph-variant($style, $lead-font-size, $lead-font-weight)`](mixins/library/general/_paragraphs.scss) :  
Easily set out variant styles for all paragraphs.

* [`table-variant($style, $striped-background-color, $hover-background-color)`](mixins/library/general/_tables.scss) :  
Easily set out variant styles for all tables.

## Typography

### General

#### Mixins

* [`rem($property, $values, $root)`](mixins/typography/general/_rem.scss) :  
Generate PX/REM value which is relative to the font-size defined for the html element.

### Font Awesome

#### Mixins

* [`fa-icon($icon, $type, $position)`](mixins/typography/fontawesome/_fa-icon.scss) :  
Font Awesome's Free Icons.

## Variables

### Options

* [`$enable-rounded`](variables/_options.scss) :  
Enable or disable the border radius on components.

* [`$enable-shadows`](variables/_options.scss) :  
Enable or disable the box shadow on components.

* [`$enable-transitions`](variables/_options.scss) :  
Enable or disable the transitions when components state changes.

* [`$enable-grid-classes`](variables/_options.scss) :  
Enable or disable the *Grid Sytem* classes.

* [`$enable-extend-directive`](variables/_options.scss) :  
Choose either to use the `@extend` or the `@include` Sass directive.

* [`$enable-retina-fallback`](variables/_options.scss) :  
Enable or disable the retina fallback for images.

* [`$enable-legacy-support-for-ie6`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 6.

* [`$enable-legacy-support-for-ie7`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 7.

* [`$enable-legacy-support-for-ie8`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 8.

* [`$enable-legacy-support-for-ie9`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 9.

* [`$enable-legacy-support-for-ie10`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 10.

* [`$enable-legacy-support-for-ie11`](variables/_options.scss) :  
Enable or disable the browser support to Internet Explorer 11.

### Default palette

* [`$colors`](variables/_colors.scss) :  
Map of color scheme.

* [`$theme-colors`](variables/_colors.scss) :  
Map of theme color scheme.

* [`$grays`](variables/_colors.scss) :  
Map of grayscales.

### Base rule variables

* [`$font-family-sans-serif`](variables/_base.scss) :  
Sans-serif font family.

* [`$font-family-monospace`](variables/_base.scss) :  
Monospace font family.

* [`$body-base-color`](variables/_base.scss) :  
The base text color applied on the document body.

*[ `$body-base-background-color`](variables/_base.scss) :  
The base background color applied on the document body.

* [`$body-base-font-family`](variables/_base.scss) :  
The base font family applied on the document body.

* [`$body-base-font-size`](variables/_base.scss) :  
The base font size applied on the document body.

* [`$body-base-font-weight`](variables/_base.scss) :  
The base font weight applied on the document body.

* [`$body-base-line-height`](variables/_base.scss) :  
The base text line height applied on the document body.

* [`$heading-[1-6]-font-size`](variables/_base.scss) :  
The default font sizes applied on each heading type.

* `$image-folder-path`](variables/_base.scss) :  
The default path to the image folder.

* [`$image-fallback-extension`](variables/_base.scss) :  
The default file extension for images.

* [`$image-retina-media-query`](variables/_base.scss) :  
The retina display media query string.

* [`$image-retina-suffix`](variables/_base.scss) :  
The default suffix for images with retina fallback.

### Layout & Grid system variables

* [`$grid-breakpoints`](variables/_layout.scss) :  
Map of breakpoints for responsive design.

* [`$container-max-widths`](variables/_layout.scss) :  
Map of the `.container` maximum widths for different screen sizes.

* [`$grid-columns`](variables/_layout.scss) :  
The number of columns of the *Grid System*.

* [`$grid-gutter-width`](variables/_layout.scss) :  
The width of the gutters between each *Grid System* columns.

### Components rule variables

* [`$component-vertical-paddings`](variables/_components.scss) :  
Map of common vertical padding sizes used by the components.

* [`$component-horizontal-paddings`](variables/_components.scss) :  
Map of common horizontal padding sizes used by the components.

* [`$component-margins`](variables/_components.scss) :  
Map of common margin sizes used by the components.

* [`$component-border-width`](variables/_components.scss) :  
The common border width used by the components.

* [`$component-border-style`](variables/_components.scss) :  
The common border style used by the components.

* [`$component-border-colors`](variables/_components.scss) :  
Map of common border color brightnesses used by the components.

* [`$component-border-radiuses`](variables/_components.scss) :  
Map of common border radius sizes used by the components.

* [`$component-font-weights`](variables/_components.scss) :  
Map of common font thicknesses used by the components.

* [`$component-state-colors`](variables/_components.scss) :  
Map of common text color states used by the components.

* [`$component-state-background-colors`](variables/_components.scss) :  
Map of common background color states used by the components.

* [`$component-box-shadows`](variables/_components.scss) :  
Map of common box shadow lengths used by the components.

### Selectors rule variables

* [`$[french|dutch|english]_language`, `$pages`, `$page-[front|not-front|maintenance|...]`, `$sidebar-[not-visible|visible|one-visible|...]`, `$regions`, `$forms`, `$navigations`](variables/_selectors.scss) :  
Define all CSS selectors for "System" (module) components.

* [`$layouts`, `$layout-[wrappers|wrapper-content|wrapper-navigation|wrapper-complementary]`](variables/_selectors.scss) :  
Define all CSS selectors for "Layouts" (module) components.

* [`$nodes`, `$view-mode`, `$teaser`, `$page`](variables/_selectors.scss) :  
Define all CSS selectors for "Node" (module) components.

* [`$paragraphs`](variables/_selectors.scss) :  
Define all CSS selectors for "Paragraph" (module) components.

* [`$fields`, `$field-label-[inline|above]`](variables/_selectors.scss) :  
Define all CSS selectors for "Field" (module) components.

* [`$views`, `$views-[row|exposed-form]`](variables/_selectors.scss) :  
Define all CSS selectors for "Views" (module) components.

* [`$blocks`, `$block-inside-region`, `$region-[tools|header|header-collapsible|highlighted|content|navigation|complementary|postscript|footer]`](variables/_selectors.scss) :  
Define all CSS selectors for "Block" (module) components.

* [`$ckeditor`](variables/_selectors.scss) :  
Define all CSS selectors for "CKEditor" (module) components.

### Font Awesome's Free Icons Library

* [`$fa-conversion-map`](variables/_fontawesome.scss) :  
Define the map of "Font Awesome Icons" conversion allowed values.