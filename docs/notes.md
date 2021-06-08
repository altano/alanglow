# Reference
* TST options: about:addons
* [Mozilla theme reference](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/manifest.json/theme#colors)
* [Firefox Color](https://color.firefox.com/)
* Temporarily loading unsigned ext: about:debugging#/runtime/this-firefox

# TODO
[x] Blue of selected text in address bar
[x] Gray of selected text in address bar when window inactive
[ ] tab overlap (TST userChrome.css?)
[x] TST tab highlight color
[-] button active icon color (non-addressable, don't use green)
[-] button active text color (non-addressable, don't use green)
[x] new tab page background color / border?
[-] new tab page form fields/buttons (non-addressable)
[x] address bar URL colors
[-] search bar "this time search with" text (non-addressable)
[x] test vanilla tabs
[x] Blue of download button when download completes (icons attention)
[x] find dialog checkboxes => mint green (non-addressable)
[x] Submit below TST changes as PR to github
[-] tab_background_separator -> tab_line (FF89). Maybe just duplicate?
[-] menu popup separator at top is rainbow colored (non-addressable)
[x] loading tab bouncy ball color
[x] test bookmarks sidebar
[-] sidebar: input field (e.g. bookmarks search) (non-addressable)
[x] sidebar: highlight
[x] toolbar_field = 2D245B (same as Search Bar Color)
[-] toolbar_field_border = transparent?
[-] toolbar_field_border_focus = mint green?
[-] toolbar_field_highlight_text = ?
[ ] add-on icon
[ ] search popup corner visual defect (https://bugzilla.mozilla.org/show_bug.cgi?id=1714898)
[ ] auto-style tree style tabs?
[ ] auto style sidebery?
[ ] get screenshots onto theme page

# Windows
accent color: EA005E

# alpenglow
icons: C68AFF
toolbar: 271D4E
Search bar color: 2D245B
text: D1C9EA

# TST theme
[_Apply tab colors exactly same to Firefox's native_](https://github.com/piroor/treestyletab/wiki/Code-snippets-for-custom-style-rules#apply-tab-colors-exactly-same-to-firefoxs-native-2780)
```css
:root {
  --tab-surface-regular: var(--theme-colors-tab);
  --tab-surface-active: var(--theme-colors-tab_selected, var(--theme-colors-toolbar, var(--browser-bg-for-header-image, var(--tab-like-surface))));
  --tab-surface-active-hover: var(--theme-colors-tab_selected, var(--theme-colors-toolbar, var(--browser-bg-for-header-image, var(--tab-like-surface))));
  --tab-surface-hover: rgba(255,255,255,.1) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#590 */;
  --tab-border: var(--theme-colors-tab_background_separator, var(--theme-colors-tab_background_text-30, hsl(240,9%,32%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#684 : --tab-text-regular * 0.3 opacity */));
  --tab-text-regular: var(--theme-colors-tab_background_text, hsl(240,9%,98%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */);
  --tab-text-active: var(--theme-colors-toolbar_text, -moz-DialogText /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */);
  --tabbar-bg: var(--theme-colors-frame, hsl(235,33%,19%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/windows/browser-aero.css#59 */);
}
```
My modifications (some for FF 89, some just custom)
```css
:root {
  --tab-surface-regular: var(--theme-colors-tab, var(--theme-colors-frame_inactive));
  --tab-surface-active: var(--theme-colors-tab_selected, var(--theme-colors-toolbar, var(--browser-bg-for-header-image, var(--tab-like-surface))));
  --tab-surface-active-hover: var(--theme-colors-tab_selected, var(--theme-colors-toolbar, var(--browser-bg-for-header-image, var(--tab-like-surface))));
  --tab-surface-hover: var(--theme-colors-button_background_hover, rgba(255,255,255,.1) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#590 */);
  --tab-border: var(--theme-colors-tab_background_separator, var(--theme-colors-tab_line, var(--theme-colors-tab_background_text-30, hsl(240,9%,32%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/shared/tabs.inc.css#684 : --tab-text-regular * 0.3 opacity */)));
  --tab-text-regular: var(--theme-colors-tab_background_text, hsl(240,9%,98%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */);
  --tab-text-active: var(--theme-colors-tab_text, var(--theme-colors-toolbar_text, -moz-DialogText /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/toolkit/themes/windows/global/tabbox.css#27 */));
  --tabbar-bg: var(--theme-colors-frame, hsl(235,33%,19%) /* from https://searchfox.org/mozilla-central/rev/8d722de75886d6bffc116772a1db8854e34ee6a7/browser/themes/windows/browser-aero.css#59 */);
}
```