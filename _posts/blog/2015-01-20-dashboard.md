---
title: Dashboard
layout: post
date:   2015-01-20 15:59:00
categories: blog
tags: [clojure compojure dashboard hiccup lightTable ring]
---

Since three days I work on a dashboard that
will display statistics in the form of tables and graphs.

I am using with great pleasure the following tools:

* [ring]{:target="_blank"} for the server,
* [compojure]{:target="_blank"} for the  routing,
* [hiccup]{:target="_blank"} for dynamic generation of html pages,
* also [simple-time]{:target="_blank"} for handling dates,
  I found it to be more lightweight and concise as
  [clj-time]{:target="_blank"}.

Thanks to the `ring.middleware.reload` middleware and the tip
which is to set in ring the compojure's routes as a var quote (`#'app-routes`),
every modification made in the code is taken into account
without the need to reload the namespace in the REPL.

I have not yet chosen between Dimple.js and Epoch
for the display part.

Finally, [doric]{:target="_blank"} helps me to show my data in chart form in
the REPL, which is appreciable.

Of course the IDE I use is [Light Table]{:target="_blank"}, a must :-)

[ring]: https://github.com/ring-clojure/ring
[compojure]: https://github.com/weavejester/compojure
[hiccup]: https://github.com/weavejester/hiccup
[simple-time]: https://github.com/mbossenbroek/simple-time
[clj-time]: https://github.com/clj-time/clj-time
[doric]: https://github.com/joegallo/doric
[Light Table]: http://lighttable.com/
