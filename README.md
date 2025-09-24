# Grub2 Keymaps

Took me 24h to not be on outdated documentation (which will break your setup btw) so made a script to save time for others. 

Thanks to this blog post [FitzBlog](https://fitzcarraldoblog.wordpress.com/2019/04/21/how-to-change-the-keymap-keyboard-layout-used-by-the-grub-shell-in-gentoo-linux/) And W to void users for going in exact detail and how to do something.

---

Basically when running `grub-mklayout` to generate the layout file: get error: `ckbcomp` not found. So you just need to make sure to have it from the AUR (hopefully becomes a core package). This is a large perl script that just maps/converts keys to a grub compatible format `.gkb`

Then follow the steps from the guide (which is the same as the script here). 

Cheers.
