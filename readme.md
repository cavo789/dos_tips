![Banner](images/banner.png)

# DOS tips

> Some tips & tricks for Dos

* [Default folder when starting the DOS prompt](#default-folder-when-starting-the-dos-prompt)
* [File copy](#file-copy)
  * [Copy a set of folders and exclude somes](#copy-a-set-of-folders-and-exclude-somes)
* [License](#license)

## Default folder when starting the DOS prompt

By running `CMD`, Windows will start the DOS Prompt and you'll be located in your user profile folder (`%USERPROFILE%`)

If you want to change this:

1. Run `regedit`
2. Navigate to `Computer\HKEY_CURRENT_USER\Software\Microsoft\Command Processor` 
3. Create a new key `Autorun`, string one
4. Type a `cd` (change directory) command followed by your preferred one like `cd c:\christophe\repositories`

From now, when you'll start `CMD` you'll be directly in that folder.

![Default folder when starting the DOS prompt](./images/default_folder.png)

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
