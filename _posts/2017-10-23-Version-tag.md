---
title: How to make a version tag
author: SiCo
layout: post
category: guide
comments: false
---

#### When a version can release , should create a tag on master branch.

#### Tag format like x.y.z
- x is a main version, it cannot increase until product come to different user expirence extremely.
- y increase when feature-set comes ture, include optimized, expand.
- z increase when there is a bug appear, different with expected. And z will not reset to zero until x increase.
- Like 1.0.0 -> 1.0.1 -> 1.0.2 -> 1.1.2 -> 1.1.3 -> 1.2.3 -> 1.3.3 -> 2.0.0 .....

#### command
`git checkout master && git rebase release/1.1.x && git push && git tag 1.1.6 && git push --tag`