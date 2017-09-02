# meteor create --bare (vs) --full
(Meteor 1.5) 

### _Just the diffs, plz_
Because I wanted to easily grok the differences between creating a _bare_ bones, empty-as-can-be meteor project, and _full_ boilerplate-scaffolded meteor project (i.e. the spread between the `--bare` and `--full` optional switches to `meteor create`.

### Basic steps / commands
> `mkdir bare-v-full && cd bare-v-full`

> `meteor create --bare --release 1.5 .`

> `git commit -am "with '--bare'"`

At this point I also snapshotted a [branch](https://github.com/emjayess/meteor-bare-v-full/branches), for posterity, w: 

> `git checkout -b meteor/bare`

Then I removed everything from the folder (except ./.git with the git repo meta-information) and ran the `--full` switch:

> `meteor create --full --release 1.5 .`

> `git commit -am "with '--full'"`

And snapshotted the token, correlating [branch](https://github.com/emjayess/meteor-bare-v-full/branches), for posterity:

> `git checkout -b meteor/full`

### Okie, so _diffs_?
Nod, commit 49255d5e1352c0605c0799130078319ef42f417a (commit of the scaffolded source) reveals the diffs between scaffolded and the parent commit ref (commit of the bare source). The bare source is really _really_ bare, and the scaffolded source indeed has a nice introductory meteor 1.5+ application structure, from which to begin working and modeling a new application.

### And?
For starters, peruse the deltas in the [`.meteor/packages`](https://github.com/emjayess/meteor-bare-v-full/commit/49255d5e1352c0605c0799130078319ef42f417a#diff-a3eac861006726578afdba8a9e3196de) file, to better understand how the scaffolded variation is making some basic enhancements over vanilla meteor...

* drops `static-html` in favor of `blaze-html-templates` (yay!)
* also adds `kadira:flow-router` and `kadira:blaze-layout` (double yay!)
* introduces a `less` css pre-compiler (`meteor add fourseven:scss` for sass/scss support!)
* and `practicalmeteor:mocha` geared for writing and running tests for your app (tests!)

### Sweet Meteor o' Life
Indeed, Happy hacking =)
