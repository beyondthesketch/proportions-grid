# The Proportions Grid

__An unconventional layout system for a content-first, fully responsive design approach__

## About

TBC

## Concepts

### Content First & Semantics

The Proportions Grid is all about content, and therefore you *must write HTML semantically*. This is less about the structural and sectioning elements, but the content elements the flow elements - i.e. Use the appropriate heading elements where you need a heading - not a styled `<p>` tags or similar.

### The Spacing Ratio

The main concept of this layout system, is to lay out page *content* in a way that is less about pixel perfect positioning of elements, but creating separations between the content in a way that visually infer relationships between the different parts of that content.

This is achieved by using a spacing ratio and a base font size to determine what amount of spacing (by approximation) is relevant between not only titles, headings, text etc, but also the structural or semantic elements you use to separate that content.

The default spacing ratio used by the Proportions Grid is the golden ratio: __1.618__. We believe this is the best ratio to use as it is everywhere in nature, and therefore engages human visual perception in a way that is familiar and inherently recognised as beautiful - but you can use any ratio you like - experiment with a few to find the right one for your layout. 

### Content Containers (class: pgrid_cr)

These are content-containing elements that are always structural and may be semantic - such as `<div>`, `<section>`, `<article>` etc. The purpose of these elements are simply to contain actual content of your page.


### Widths (class: pgrid_w_*)

Any Content Container, or content holding item within a container can be given a width - these however are not widths in the sense you might be used to - they are *proportions*. You give your content any of the following proportions (CSS class name in brackets):

- full width (pgrid_w_1)
- Three Quarters (pgrid_w_3_4)
- Two-thirds (pgrid_w_2_3)
- Half (pgrid_w_1_2)
- Third (pgrid_w_1_3)
- Quarter (pgrid_w_1_4)

These widths are relative to the width of their parent element and are *nest-able*.

### CSS Modifier Classes

The following CSS classes are modifiers to the default behaviours.

#### Content Container (pgrid_cr) modifiers

- `pgrid_n-w` - No Wrap - prevent wrapping of the contents of this container

#### Width (pgrid_w_*) modifiers

- `pgrid_p` - Pad - *NOTE: Applies only to the `pgrid_w_1` width*
- `pgrid_n-p` - No Pad - do not apply the normal padding to this width
- `pgrid_n-p-s` - No Pad Sides - do not apply the normal padding to the sides of this width - top and bottom are padded as normal.
- `pgrid_n-p-t` - No Pad Sides - do not apply the normal padding to the top of this width - sides and bottom are padded as normal.
- `pgrid_n-p-b` - No Pad Sides - do not apply the normal padding to the bottom of this width - top and sides are padded as normal.
- `pgrid_n-g` or `pgrid_n-f` - No Grow/No Flex - Do not allow this width to grow to fill the available space (i.e. force the width proportion specified even if it creates empty space)

### Fully Responsive

The layout system is completely responsive and flexible - being based on CSS Flexible Box Layout - without any configuration from you, handles the content in a way that mitigates your layout breaking down between breakpoints.

In addition, the Proportions Grid uses fluid layout for smaller screensizes, meaning you can benefit from knowing you design will be predictable and consistent across a wide array of different mobile devices.

### Gain Control by Relinquishing Control

By default, the Proportions Grid follows rules to determine at what screen sizes, the widths you choose for your content would be logical and feasible to do be shown at that proportion of the screen.

For example, rules determine that at a certain size point, an element you have designated as a quarter would be better to be displayed as a half. This allows you to lay out your website optimally for the majority of your users, and not have worry so much about the layout breaking down on bigger or smaller screens, or as is usually the case - between breakpoints.

## Usage

First clone this repository. Use the command line and navigate to the folder that was cloned (i.e. the root of the repo).

Generate the proportions grid by running:

```shell
    npm run build
```

The production ready css file is created in the `dist` directory as `proportions-grid.css`. Copy this file to the project in which you want to use the layout system, and link it in your html file/s, ideally before any of your other css.

### Default Grid

By default, the Portportions Grid works with the following settings:

- Base font size: 12px
- Spacing Ratio: 1.618
- CSS class prefix: 'pgrid'

3 other configurations that we like are provided for convenience:

`proportions-grid-12x1_5.css` which has the following settings:

- Base font size: 12px
- Spacing Ratio: 1.5
- CSS class prefix: 'pgrid'

`proportions-grid-12x2.css` which has the following settings:

- Base font size: 12px
- Spacing Ratio: 2
- CSS class prefix: 'pgrid'

`proportions-grid-13x1_618.css` which has the following settings:

- Base font size: 13px
- Spacing Ratio: 1.618
- CSS class prefix: 'pgrid'

### Customisation

You can generate grids with different settings if you want to customise the layouts further.

To customize these settings, use the `_user-settings.conf.scss` file to uncomment the appropriate setting and specify your own values. When you run the npm `build` script, your settings will be used in place of the above defaults.