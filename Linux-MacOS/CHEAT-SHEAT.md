Using `find` and `cpio` to copy files from a given source into a target folder keeping their folder structure: 

```shell
find . -name 'some-file-or-folder' | cpio -pdm /some/target/folder
```
