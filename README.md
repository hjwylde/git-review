# git-review

[![Project Status: Active - The project has reached a stable, usable state and is being actively developed.](http://www.repostatus.org/badges/latest/active.svg)](http://www.repostatus.org/#active)
[![Release](https://img.shields.io/github/release/hjwylde/git-review.svg)](https://github.com/hjwylde/git-review/releases/latest)

A Git command that enables reviewing a feature commit by commit.

### Installing

Clone down the repository and add the `bin/` folder to your `PATH` environment variable.

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
> git review master...issue/1
cb182c1 (#1) update CHANGELOG.md
cfbb485 (#1) update README.md with installation instructions and example usage
9f34372 (#1) add initial version of git-review
git show -w -C -p --stat 9f34372?...y
commit 9f34372e3756c19838027cc0a16e8cd5f96a0a93
Author: Henry J. Wylde <public@hjwylde.com>
Date:   Thu Jun 9 13:17:14 2016 +1200

    (#1) add initial version of git-review
---
 bin/git-review | 7 +++++++
 1 file changed, 7 insertions(+)

diff --git a/bin/git-review b/bin/git-review
new file mode 100755
index 0000000..e3d2e1f
--- /dev/null
+++ b/bin/git-review
...
git show -w -C -p --stat cfbb485?...n
git show -w -C -p --stat cb182c1?...n
```
