---
title: New Blog
date: 2019-04-18
tags:
  - google app engine
  - blog
layout: layouts/post.njk
---

<p>I decided to start writing again and so I picked up the latest in static site generation, <a href="https://gohugo.io">Hugo</a>, and deployed it all on my favoritest hosting option, <a href="https://cloud.google.com/appengine/">Google App Engine</a>.</p>

<p>Running the site this way is almost straightforward. The only tricky thing is getting the rules right for serving the static files. I’ve been running a static site on App Engine for a while now, but I figured it would be good to take another look at the config to make sure I’m using it well. I found this blog entry on <a href="https://deciphertools.com/blog/google-app-engine-static-sites/">running a static site on Google App Engine</a> and that helped me confirm rules I needed. It also has some good tips on setting up 301 redirects (though I usually just delete my old stuff on refresh) and SSL (something that I didn’t know was super easy to do on App Engine). When I get some time (and can clean up the process more) I’ll write an entry about it.</p>

<p><strong><em>Update:</em></strong> I had to make an adjustment just before publishing. It turns out I wasn’t able to use the <code>skip_files</code> part of the configuration from the article linked above. It looks like that’s a holdover from the older App Engine instances. The new way is to use a <code>.gcloudignore</code> file which is <a href="https://cloud.google.com/sdk/gcloud/reference/topic/gcloudignore">documented here</a>.</p>

<h2 id="what-i-m-looking-at-now">What I’m Looking At Now</h2>

<p>The newest thing that’s caught my attention is <a href="https://cloud.google.com/run/">Google Cloud Run</a>. From what I’ve read/heard so far it’s basically “run your container in the cloud”. That might not sound spectacular but it’s got one killer feature that first made me love App Engine - it scales down to zero automatically. If you’ve got eight minutes I’d recommend checking out this <a href="https://www.youtube.com/watch?v=3OP-q55hOUI">video by Fireship</a> which not only demos Cloud Run but also hooking it up to a Firebase hosted site.</p>

<p>At this point you might assume (if you don’t know me) that I’m a Google fan boy. That wouldn’t be accurate, but I can see the cause of the confusion. My real affinity is for App Engine. I can explain why but we have to go back a bit.</p>

<p>Back when App Engine was first released I was just starting to get into Python. I really liked it’s expressiveness and I really wanted to use it more often for web development. There was a problem though - hosting. Hosting options weren’t great for small pet projects, especially if you were cash strapped like I was. But then the heavens opened and App Engine was released.</p>

<p>App Engine had a number of great features. One was that it had a free quota (woo!). The second was that it would <em>shut itself down</em> when no requests were coming to it, effectively stretching your free quota even further (woohoo!!). It was great for someone trying to stretch their dollar further. And this is still true today, App Engine (standard at least) still offers the free quota and automatic scaling. (Are you taking notes Amazon?)</p>

<p>There is a downside to running on App Engine (standard) though and one of those downsides is that you are restricted in your choice of language. I’m a polygot developer so the restriction didn’t bother me much but I can appreciate it being a stumbling block for others, especially if you have a rigid organization. <strong>Cloud Run</strong> though opens up that App Engine automatic scaling to everyone and that sounds really cool. Feel like writing that new micro service in Erlang? Go for it. Lua? Sure. Want to put Openoffice in a container so you can convert docs to pdf? There’s a demo for that, <a href="https://www.gcppodcast.com/post/episode-173-cloud-run/">per the Google Cloud podcast</a>. The prospects of how people could use this are exciting. As soon as I get a chance to look into this, I plan to.</p>

<p>Unless something else distracts me first. (It’s very possible.)</p>
