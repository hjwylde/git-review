# git-review

[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![Release](https://img.shields.io/github/release/hjwylde/git-review.svg)](https://github.com/hjwylde/git-review/releases/latest)

A Git command that enables reviewing a feature commit by commit.

### Installing

Clone down the repository and add the bin folder to your `PATH` environment variable.

```bash
git clone https://github.com/hjwylde/git-review DESTINATION/
export $PATH:DESTINATION/bin/
```

### Usage

Call `git review` and pass in any commit reference that `git log` supports, e.g.,
    `master...issue/1`.
Any commit found in the reference will be piped to `xargs` and give you a prompt asking whether you
    would like to review the commit.

```bash
git review master...issue/1
git show -w 9f34372e3756c19838027cc0a16e8cd5f96a0a93?...y
commit 9f34372e3756c19838027cc0a16e8cd5f96a0a93
Author: Henry J. Wylde <public@hjwylde.com>
Date:   Thu Jun 9 13:17:14 2016 +1200

    (#1) add initial version of git-review

diff --git a/bin/git-review b/bin/git-review
new file mode 100755
index 0000000..e3d2e1f
--- /dev/null
+++ b/bin/git-review
...
```
