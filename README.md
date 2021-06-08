# alanglow

A Firefox theme. Alpenglow-inspired. [Tree Style Tabs]() compatible.

## Screenshots

`@TODO`

## Tree Style Tabs Styling

`@TODO` Add screenshot

[Tree Style Tabs](https://github.com/piroor/treestyletab) is an extension for having a vertical tree of tabs in your sidebar. This theme is comptible with it but you must revert Tree Style Tabs' CSS to Firefox native for this theme's styling to work. [Instructions are here](https://github.com/piroor/treestyletab/wiki/Code-snippets-for-custom-style-rules#apply-tab-colors-exactly-same-to-firefoxs-native-2780) but in short:

1. Right click TST button in toolbar
1. Click "Manage Extension"
1. Click "Options"
1. Go to the "Extra style rules for contents provided by Tree Style Tab and in the text area put:

```css
:root {
  --tab-surface-regular: var(--theme-colors-tab,
                             var(--theme-colors-frame_inactive));
  --tab-surface-active: var(--theme-colors-tab_selected,
                            var(--theme-colors-toolbar,
                                var(--browser-bg-for-header-image,
                                    var(--tab-like-surface))));
  --tab-surface-active-hover: var(--theme-colors-tab_selected,
                                  var(--theme-colors-toolbar,
                                      var(--browser-bg-for-header-image,
                                          var(--tab-like-surface))));
  --tab-surface-hover: rgba(255,255,255,.1) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#590 */;
  --tab-border: var(--theme-colors-tab_background_separator,
                    var(--theme-colors-tab_line,
                        var(--theme-colors-tab_background_text-30,
                            hsl(240,9%,32%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#684 : --tab-text-regular * 0.3 opacity */)));
  --tab-text-regular: var(--theme-colors-tab_background_text,
                          hsl(240,9%,98%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */);
  --tab-text-active: var(--theme-colors-tab_text,
                         var(--theme-colors-toolbar_text,
                             -moz-DialogText /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */));
  --tabbar-bg: var(--theme-colors-frame,
                   hsl(235,33%,19%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/windows/browser-aero.css#59 */);
}
```

## Sidebery Styling

`@TODO` Add screenshot

[Sidebery](https://github.com/mbnuqw/sidebery) is an extension for having a vertical tree of tabs in your sidebar.

A work-in-progress set of styles to match this theme can be found [here](integrations\sidebery\sidebery-data-2021.06.08-00.44.04.json). You can import this .json file from the Sidebery settings.