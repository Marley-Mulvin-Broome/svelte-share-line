# @svelte-share/line

Simple svelte component for a share to line button.

## Usage

```svelte
<script lang="ts">
  import { Line } from '@svelte-share/line';
</script>

<Line
  url="https://www.marley-web.dev"
  arialLabel="シェア"
  class="line-font"
  --share-button-gap="1.5em"
>
  <span style="font-size: 1.3em; font-weight: 600;"> 送る </span>
</Line>
```

## Properties

There are a variety of properties you can set to directly style the element. See `src/line/Line.svelte` to get a full list of settable variables.

Some of the main ones:

- `--share-link-color` Colours text
- `--share-button-gap` Gap between the icon and `Lines`'s child
- `--share-padding` Padding for the button
- `--share-button-background-color` Background colour for the button
- `--share-button-hover-color` Hover colour for the button

## Direct styling

There are two ways to directly style the button

### Class prop

You can pass through classes directly with class. This will be applied to the `<div>` within the `<a>` tag.

### Global styles

You may also globally style the button with Svelte's `:global(.class)` syntax. Here is a list of the classes used below in order of parent

- `.share-line__link`
- `.share-line__button`
- `.share-line__icon`

## Contributing

Leave an issue or implement it yourself! I have no experience managing repos so lets all be nice to each other ❤️
