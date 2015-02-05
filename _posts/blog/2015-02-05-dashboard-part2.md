---
title: Dashboard, part2
layout: post
date:   2015-02-05 09:23:00
categories: blog
tags: [clojure dashboard core.async websocket]
---

After a break for more important projects,
I'm back on the dashboard project.
Since the first version was working fine,
I decided to redo everything,
according to a well-known principle in application development...

I replaced vanilla JavaScript by ClojureScript,
and Ajax calls on `Compojure` routes (to retrieve data)
by `core.async` on a `websocket`.

I had previously used on another project
websockets with `httpkit` and `webbitserver`.
It was working on two different ports,
and management (and building) of websocket
brought a lot of boilerplate.

It was also necessary to convert data to json
with `cheshire` on the server side
and Javascript functions on the front side.

For websockets I started using [sente]{:target="_blank"},
which seemed to meet my needs perfectly.
This library is from the same author
than the excellent logging library `timbre`.
Alas, a version conflicts and a recalcitrant macro
prevented me from using it.

So I focused my attention on [chord]{:target="_blank"}.
Same core functionality than `sente`.
The merge with the Compojure routes is done with the
`wrap-websocket-handler` wrapper; the ` transit` format is default,
so everything is perfect.

There's no need anymore to worry about the
`onOpen`, `onClose` and `onMessage` methods of the websocket,
everything is automatic.
It lets the user focus on data to transit the ws-channel,
with `core.async` `get` and `put`.
And of course all is done without having
to explicitly convert the data to json.

On the front side, I use [domina]{:target="_blank"},
which allows me to easily manipulate
the elements of the page as well as events.

[sente]: https://github.com/ptaoussanis/sente
[chord]: https://github.com/james-henderson/chord
[domina]: https://github.com/levand/domina
