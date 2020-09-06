# Hardware

## Mechanical keyboards

### Durgod Taurus K320

Inspiration:

* https://www.chriscollins.me/blog/durgod-taurus-k320-mechanical-keyboard-for-mac-os/

Extra keycaps:

* https://www.aliexpress.com/item/4000138763106.html

Tooling:

* https://karabiner-elements.pqrs.org/

This is my setup that I've got working after 3-4 hours of hacking around to understand how to configure [Karabiner-Elements complex_modifications rules
](https://ke-complex-modifications.pqrs.org/) do get the results I wanted. These were:

* The most basic:
  - Swap `command` (Win/Super) with `option` (Alt) and 
  - Swap `option` to `command`
  - Swap `application` to become my `right_option`. Comparing to Chris Collins setup I've did a small change regarding `fn`
* Map `\`, `@`, `€`, `#` and `~` and `|` (in `grave_accent_and_tilde`) - pretty much using the keyboard without moving keycaps around and I can swap to Windows without having to change anything
* I write Portugues as well and made the AltGr (Option) behaviour for chars like `áãâ`

Usage:

* Copy the JSON file [durgod-iso-uk.json](./durgod-iso-uk.json) into _~/.config/karabiner/assets/complex_modifications_ 1st time or on every change
* Open Karabiner-Elements, go to _Complex modifications_ tab, _Rules_ and press _Add rule_ (enable all or desired ones):
* Enjoy a fully functional keyboard
