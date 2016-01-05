# vfu
Tool for vendoring repositories.

Currently supports git and mercurial.

```
Usage: vfu [-d DIR] -s [-a PATH=REPO]* CONFIG  # save
       vfu [-d DIR] -r CONFIG  # restore
```

Default for `DIR` is the current working directory.

`vfu -s` searches through `DIR` looking for repositories, making a record of all that it finds, and writes it to `CONFIG`.

Zero or more additional repositories that exist outside of subdirectories of `DIR` may be vendored using the `-a PATH=REPO` flag. `PATH` is the location within `DIR` that it will be put on a restore, and REPO is the absolute path of the repository root.

`vfu -r` looks at `CONFIG`, and clones all the recorded repositories into `DIR`.

`vfu` prints the local directories of the repositories it processes. This printing makes it easy to update a .gitignore or .hgignore file.
```
$ vfu -s >> .gitignore
```
