# SYMAN

## Grub2 Keymaps

Took me 24h to not be on outdated documentation (which will break your setup btw) so made a script to save time for others. 

Thanks to this blog post [FitzBlog](https://fitzcarraldoblog.wordpress.com/2019/04/21/how-to-change-the-keymap-keyboard-layout-used-by-the-grub-shell-in-gentoo-linux/) And W to gentoo users for going in exact detail and how to do something.

---

Basically when running `grub-mklayout` to generate the layout file: get error: `ckbcomp` not found on arch. So you just need to make sure to have it from the AUR (hopefully becomes a core package). This is a large perl script that just maps/converts keys to a grub compatible format `.gkb` I've included it directly in the repo here as it's unlikely to change that much. 

Then follow the steps from the guide on Fitz's blog (which is the same as the script [here](https://github.com/h8d13/SYMAN-GRUB2/blob/master/grub_keymaps)). 

```
KB_LAYOUT="fr"
KB_VARIANT="azerty"
```

Make sure to set these and variant can be left empty as `""`. 

Careful that grub (and system critical pieces in general) are often restricted to 1-127 range. So don't use special chars in users/passwords, etc. And are case sensitive! 

> At this point you can verify it works by pressing `c` in the grub menu and checking keys are properly registered.

## Grub2 Passwords

Included a second script that can generate the hash append it to the same file we just modified and also decide  you want to restrict boot (laptops). Using `ALLOW_BOOT_NOPW=1` so set it to `0` if boot should require password.

But this already covers a large vector that nobody can edit your launch lines (common exploit of adding rw and spawing a shell) or use the rescue shell without your user/pw. Hence why I've set it to `1` by default. 

