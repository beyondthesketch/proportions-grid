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

### REM Only Lengths

When using the Proportions Grid, all CSS lengths for your project should be specified in `rem` units, including `margin`, `padding` & `font-size`.

As the system works using relative proportions, and absolute lengths will make for fixed layouts that do not respond well to varying device screens. This will lead to broken or unexpected layouts.

Using `rem` values is simple when working with the Proportions Grid. To get the right value, simply use the pixel value you want and divide by 10.

```
1px     = 0.1rem
10px    = 1rem
100px   = 10rem
1000px  = 100rem

12px    = 1.2rem
16px    = 1.6rem
24px    = 2.4rem
```

### Content Containers (class: pgrid_cr)

These are content-containing elements that are always structural and may be semantic - such as `<div>`, `<section>`, `<article>` etc. The purpose of these elements are simply to contain actual content of your page.


### Content Widths (class: pgrid_w_*)

Any **Content Container**, or content holding item within a container can be given a **Content Width** - these however are not widths in the sense you might be used to - they are *proportions*. You give your content any of the following proportions (CSS class name in brackets):

- full width: `pgrid_w_1`
- Three Quarters: `pgrid_w_3_4`
- Two-thirds: `pgrid_w_2_3`
- Half: `pgrid_w_1_2`
- Third: `pgrid_w_1_3`
- Quarter: `pgrid_w_1_4`

These widths are relative to the width of their parent element and are *nest-able*.

By default, all **Content Width** classes specify the *minimum* proportion, but will expand to fit the width of the container. This feature allows the layout to be driven by the content it contains as well as the adjacent widths. To stop this behaviour, you can add the *no grow* modifier class, detailed below.

**Content Widths** will **not work** if they are not a child or decendant of a **Content Container**.

### Spacing With `padding`

On it's own, a **Content Width** only specifies the proportion of space to occupy, taking into account the content it contains and space available horizontally within it's **Content Container**.

But one key objective of the Proportions Grid is to provide a way of designing for content by using *spacing* to create meaningful visual relationships between content. To achieve this, padding is used to give a Content Width content's the horizontal and vertical spacing from the adjacent elements. The amount padding applied is derived from the spacing-ratio and the base font size.

Padding can be applied either with a single class which gives the *padded width* or by using *padding modifier classes*. Each **Content Width** class is also available as a padded alternative, which are:


### Padded Content Widths

- full width: `pgrid_p_w_1`
- Three Quarters: `pgrid_p_w_3_4`
- Two-thirds: `pgrid_p_w_2_3`
- Half: `pgrid_p_w_1_2`
- Third: `pgrid_p_w_1_3`
- Quarter: `pgrid_p_w_1_4`

These alternate padded Content Width classes are great if you are trying to keep your markup's class lists small.

### Padding Modifiers

If you need to control the padding in a more granular way, the padding classes can be used alongside a width instead:

- Pad all sides: `pgrid_p`
- Pad sides: `pgrid_p-s`
- Pad horizontals; i.e. the top and bottom edges: `pgrid_p-h`
- Pad top: `pgrid_p-t`
- Pad right: `pgrid_p-r`
- Pad bottom: `pgrid_p-b`
- Pad left: `pgrid_p-l`

### CSS Modifier Classes

The following CSS classes are modifiers to the default behaviours.

#### Content Container (pgrid_cr) modifiers

- `pgrid_n-w` - No Wrap - prevent wrapping of the contents of this container

#### Width (pgrid_w_*, pgrid_p_w_*) modifiers

- No Grow/No Flex: `pgrid_n-g` or `pgrid_n-f` - Do not grow and fill the available space (i.e. force the width proportion specified even if it creates empty space)

### Fully Responsive

The layout system is completely responsive and flexible - based on CSS Flexible Box Layout - without any configuration from you, handles the content in a way that mitigates your layout breaking down between breakpoints.

In addition, the Proportions Grid uses fluid layout for smaller and larger screen sizes, meaning you can benefit from knowing your design will be predictable and consistent across a wide array of devices, from the smallest smartphones to the biggest 8K monitors, and everything in between.

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

- Base font size: 16px
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