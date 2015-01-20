---
title: Dashboard
layout: post
date:   2015-01-20 15:59:00
categories: blog
tags: [clojure dashboard hiccup ring compojure LightTable]
---

Since three days I work on a dashboard that
will display statistics in the form of tables and graphs.

I am using with great pleasure the following tools:

* [ring] for the server,
* [compojure] for the  routing,
* [hiccup] for dynamic generation of html pages,
* also [simple-time] for handling dates,
  I found it to be more lightweight and concise as [clj-time].

Thanks to the `ring.middleware.reload` middleware and the tip
which is to set in ring the compojure's routes as a var quote (`#'app-routes`),
every modification made in the code is taken into account
without the need to reload the namespace in the REPL.

I have not yet chosen between Dimple.js and Epoch
for the display part.

Finally, [doric] helps me to show my data in chart form in
the REPL, which is appreciable.

Of course the IDE I use is [Light Table], a must :-)

[ring]: https://github.com/ring-clojure/ring
[compojure]: https://github.com/weavejester/compojure
[hiccup]: https://github.com/weavejester/hiccup
[simple-time]: https://github.com/mbossenbroek/simple-time
[clj-time]: https://github.com/clj-time/clj-time
[doric]: https://github.com/joegallo/doric
[Light Table]: http://lighttable.com/
