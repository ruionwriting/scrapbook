# Cheat Sheat

## Finding things

Using `find` and `cpio` to copy files from a given source into a target folder keeping their folder structure:

> From https://unix.stackexchange.com/questions/83593/copy-specific-file-type-keeping-the-folder-structure.

```shell
find . -name 'some-file-or-folder' | cpio -pdm /some/target/folder
```

## Flush DNS

From: https://documentation.cpanel.net/display/CKB/How+To+Clear+Your+DNS+Cache

**MacOS:**

```bash
sudo killall -HUP mDNSResponder
```
