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
- The font (Topaz) and the images are loaded from <https://gylead.github.io/images/>
  (repository [gylead/images](https://github.com/gylead/images)). The forum header is embedded
  as a data URI, because the forum's content security policy blocks external images.
- Chrome's native autocomplete list under the search field cannot be styled with CSS.

## Licence

The CSS files are under the [MIT](LICENSE) licence.

The font **Amiga Topaz** (loaded from the images repository) is by
[Patrick H. Lauke](https://fontstruct.com/fontstructions/show/675155) and licensed under
[CC BY 3.0](http://creativecommons.org/licenses/by/3.0/).
