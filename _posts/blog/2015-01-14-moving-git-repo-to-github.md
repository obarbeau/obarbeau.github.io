---
title: Moving Git repo to GitHub
layout: post
date:   2015-01-14 10:26:00
categories: blog
---

Today I pushed my [`repl-tasks`]{:target="_blank"} project to GitHub,
whose repository was previously on a personal [Synology]{:target="_blank"}
server.

{% highlight bash linenos %}
# add the new repo on GitHub
git remote add new-origin git@github.com:obarbeau/repl-tasks.git
# push everything
git push --all new-origin
git push --tags new-origin
# rename old syno repo
git remote rename origin previous-on-syno
# rename new repo to master
git remote rename new-origin origin
# change destination of local master branch to new repo
git branch master --set-upstream-to=origin/master
{% endhighlight %}

The history is preserved.
If some branches had existed,
it would have been necessary to pull them first to the local repo and then push
them to the new one.
See this [post]{:target="_blank"} for more information.

This project needs some refactoring and documentation, I'll do it ASAP...

[Synology]: https://www.synology.com/
[`repl-tasks`]: https://github.com/obarbeau/repl-tasks
[post]: http://www.smashingmagazine.com/2014/05/19/moving-git-repository-new-server/

