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
> git review 047fe48...issue/1
cb182c1 (#1) update CHANGELOG.md
cfbb485 (#1) update README.md with installation instructions and example usage
9f34372 (#1) add initial version of git-review
Review '(#1) add initial version of git-review' [y,n,q,?]? n
Review '(#1) update README.md with installation instructions and example usage' [y,n,q,?]? y
commit cfbb485f8905976db5045dd77d48a8240c517a39
Author: Henry J. Wylde <public@hjwylde.com>
Date:   Thu Jun 9 13:19:02 2016 +1200

    (#1) update README.md with installation instructions and example usage
---
 README.md | 33 +++++++++++++++++++++++++++++++++
 1 file changed, 33 insertions(+)

diff --git a/README.md b/README.md
index fb303d5..b08df3f 100644
--- a/README.md
+++ b/README.md
...
Review '(#1) update CHANGELOG.md' [y,n,q,?]? n
```
