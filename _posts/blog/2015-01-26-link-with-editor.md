---
title: Link with editor
layout: post
date:   2015-01-29 10:30:00
categories: blog
tags: [clojureScript code lightTable plugin]
---

I released a very simple LightTable plugin that
highlight in the `Workspace` view the file currently edited.
The sources are available on my [GitHub repo]{:target="_blank"}.

It has been build upon the [`mdhaney/lt-plugin-template`]{:target="_blank"},
with the lein command:
`lein new lt-plugin link-with-editor`.

This template generates the same structure and files
than those in the `~.config/LightTable/User` directory,
which is the default user plugin namespace.

I suggest to symlink the project's directory
to the Light Table plugin dir `~/.config/LightTable/plugins/`.
Thus, by running the commands `Plugins: Refresh plugin list`
then `App: reload behaviors`,
your plugin is available and ready to test inside Light Table.

Then, running `Editor: Build file or project` recompiles the Javascript file.
One can also connect to `Light Table UI`.
Any change made in the source files is taken into account automatically.

Don't forget to open the LT console because
all output (via `println`) are redirected here.

Finally the [LT's GitHub]{:target="_blank"} is mandatory
for discovering useful namespaces, behaviors and commands for your plugin.

[GitHub repo]: https://github.com/obarbeau/lt-link-with-editor
[`mdhaney/lt-plugin-template`]: https://github.com/mdhaney/lt-plugin-template
[LT's GitHub]: https://github.com/LightTable/LightTable/tree/master/src/lt
