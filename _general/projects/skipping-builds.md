---
title: Skipping builds
menus:
  general/projects:
    title: Skipping Builds
    weight: 4
tags:
  - docker
  - basic
  - pro
  - jet
  - git
  - builds
  - testing
  - skipping

redirect_from:
  - /docker/skipping-builds/
  - /pro/getting-started/skipping-builds/
  - /basic/getting-started/skipping-builds/
  - /continuous-integration/skipping-builds/
---

* include a table of contents
{:toc}

## Skipping Builds

You can skip builds on both [Codeship Basic](https://codeship.com/features/basic) and [Codeship Pro](https://codeship.com/features/pro) by using a special commit directive.

### Skipping Via Commit Message

You can add either of the following skip directives to the commit message of the last commit before you push and that push will be ignored:

* `--skip-ci`
* `--ci-skip`
* `[skip ci]`
* `[ci skip]`

Skipped builds do not have a build record and will not show up in the Codeship UI. They will also not count towards the concurrent builds or monthly build limits for users.

### Ignore pull request merges

When you merge a pull request you can add one of the skip directives to the commit message as well.

### Skipping Via A Step Tag on Pro

On [Codeship Pro](https://codeship.com/features/pro), in addition to using a commit message, you can also de-facto skip builds by making sure that every step in your `codeship-steps.yml` file has a `tag`, which limits that step to a certain branch. You can learn more about limiting your steps to a certain branch [codeship-steps.yml documentation]({{ site.baseurl }}{% link _pro/builds-and-configuration/steps.md %}).
