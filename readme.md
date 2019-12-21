![Banner](images/banner.png)

# DOS tips

> Some tips & tricks for Dos

* [File copy](#file-copy)
  * [Copy a set of folders and exclude somes](#copy-a-set-of-folders-and-exclude-somes)
* [License](#license)

## File copy

### Copy a set of folders and exclude somes

Copies a set of folders excluding certain sub-folders; f.i. exclude `.git` folder (which can quickly be a very big folder), `node_modules` and `vendor` which are unneeded because they can be reconstructed with an `npm install` and a `composer update`.

```bash
cd c:\repositories
robocopy . c:\backup\. /IS /S /XD .git node_modules vendor
```

These two lines will allow you to copy everything from `c:\repositories` to `c:\backup`, rewrite files even if they're present in the backup folder, copying symlinked folder and exclude a few folders.

## License

[MIT](LICENSE)
