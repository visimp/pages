# `visimp` pages

Static [Hugo](https://gohugo.io) website for
[`visimp`](https://github.com/visimp/visimp).

Before invoking `hugo`, use

```bash
find content -type -l | xargs sed -i ''
```

This way, symbolic links in `visimp` will become copies of the respective
original files. The CI pipeline also takes care of this. Please do not commit
these changes. Our Hugo theme does not work well with symbolic links, but there
are sometimes important to maintain the codebase non-repetitive.
