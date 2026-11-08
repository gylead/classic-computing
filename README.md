# classic-computing

AmigaOS 1.3 look for [classic-computing.de](https://www.classic-computing.de/) and its
[forum](https://forum.classic-computing.de/), as userstyles for the
[Stylus](https://add0n.com/stylus.html) browser extension.

The theme uses only four colours:

| Colour | Hex       | Use                      |
|--------|-----------|--------------------------|
| blue   | `#1f45ac` | backgrounds              |
| white  | `#fcfffb` | text on blue             |
| orange | `#fe870b` | links and highlights     |
| black  | `#000600` | boxes, inputs, menu bars |

## Files

| File        | Applies to                  | Content                                                                 |
|-------------|-----------------------------|-------------------------------------------------------------------------|
| `style.css` | `www.classic-computing.de`  | Menus, dropdowns, scrollbars, calendar, sidebar, search results, sub pages |
| `forum.css` | `forum.classic-computing.de`| WoltLab theme variables, Amiga header image, dialogs, buttons, topic lists |

## Installation

1. Install Stylus for Chrome or Firefox.
2. Create a new style in Stylus and paste the content of `style.css`. The `@match` line limits it
   to `www.classic-computing.de`.
3. Create a second, separate style for `forum.css`.

Keep the two styles separate. If the www style is applied to the whole domain
`classic-computing.de`, its rules also leak into the forum.

## Notes

- The dropdown popups use `appearance: base-select` and `::picker(select)`, which need Chrome 135 or newer.
- The fonts and the images are loaded from <https://gylead.github.io/images/>
  (repository [gylead/images](https://github.com/gylead/images)). The forum header is embedded
  as a data URI, because the forum's content security policy blocks external images.
- Chrome's native autocomplete list under the search field cannot be styled with CSS.

## Licence

The CSS code is under the [MIT](LICENSE) licence, with one exception:

- The header image embedded in `forum.css` (base64 data URI) is a modified version of the header of
  classic-computing.de. It is under [CC BY-NC-SA 3.0 DE](https://creativecommons.org/licenses/by-nc-sa/3.0/de/)
  (attribution, non-commercial, share-alike), like the other graphics on that site.
  Details: [gylead/images LICENSE.md](https://github.com/gylead/images/blob/main/LICENSE.md).

## Fonts

Three Topaz fonts are available in [gylead/images](https://github.com/gylead/images). The default is
the first one. To use another, change the `src` URL (and `size-adjust`) in the `@font-face` rule at the
top of the Stylus style:

| Font | File | `size-adjust` | Look |
|------|------|---------------|------|
| TopazNG Proportional (default) | `topaz-ng-proportional.woff2` | `100%` | smooth, proportional widths, best for reading |
| TopazNG Classic | `topaz-ng-classic.woff2` | `85%` | smooth, fixed width like the original Topaz |
| Amiga Topaz (pixel font) | `amiga-topaz.woff2` | remove the line | low-resolution pixel look of the real Amiga |

Example for the pixel font:

```css
@font-face {
    font-family: 'Amiga Topaz';
    src: url('https://gylead.github.io/images/classic-computing.de/amiga-topaz.woff2') format('woff2');
    font-weight: normal;
    font-style: normal;
}
```

Do this in both Stylus styles (www and forum) so they match.

The fonts are credited and licensed as follows:

- **Topaz NG** (Proportional and Classic) by Campbell Barton, under the
  [SIL Open Font License 1.1](https://codeberg.org/ideasman42/font-topaz-ng/src/branch/main/LICENSE).
- **Amiga Topaz** (pixel font) by [Patrick H. Lauke](https://fontstruct.com/fontstructions/show/675155),
  under [CC BY 3.0](http://creativecommons.org/licenses/by/3.0/).
