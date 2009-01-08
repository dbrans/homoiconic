And I for one welcome our new insect overlords
===

Rails v2.3/3.0 includes [Chris Wanstrath's `#try`](http://ozmm.org/posts/try.html) baked into ActiveSupport. What this means is that for people writing Ruby on Rails applications, the debate over nil handling is **over**.

That's right, the debate is over. No [andand](http://github.com/raganwald/andand/tree/master "raganwald's andand at master &mdash; GitHub"), no [turtles](http://chalain.livejournal.com/66798.html "chalain: Turtles!"), no [ergo](http://facets.rubyforge.org/doc/api/core/classes/Kernel.html#M000368), no `rescue nil`.

> Ladies and gentlemen, uh, we've just lost the picture, but what we've seen speaks for itself. The Corvair spacecraft has apparently been taken over -- 'conquered' if you will -- by a master race of giant space ants. It's difficult to tell from this vantage point whether they will consume the captive earth men or merely enslave them. One thing is for certain: there is no stopping them; the ants will soon be here. And I for one welcome our new insect overlords. I'd like to remind them that as a trusted TV personality, I can be helpful in rounding up others to toil in their underground sugar caves. --[Kent Brockman](http://www.snpp.com/episodes/1F13.html "[1F13] Deep Space Homer")

You'll notice there was no blogghorea, no endless whining about the name or whether symbols should be used or what colour the Core Rails team should [paint the bike shed](http://en.wikipedia.org/wiki/Color_of_the_bikeshed "Parkinson's Law of Triviality - Wikipedia, the free encyclopedia"). The decision was made on your behalf. Rails applications should use `#try`.

We can wring our hands and philosophize about the whole thing, but this is the consequence of two forces interacting. First, Ruby's Smalltalk-like class architecture where changing a class has global effect. Therefore, any feature added to a core class like `Kernel` or `Object` for the convenience of a framework or gem is forced upon anyone using that framework or gem. If David likes having methods like `#second`, `#third`, and `#fourth` for his own purposes, [you get them too](http://github.com/rails/rails/commit/22af62cf486721ee2e45bb720c42ac2f4121faf4 "Commit 22af62cf486721ee2e45bb720c42ac2f4121faf4 to rails's rails &mdash; GitHub"). If he wants to have `#try`, then you get to have `#try`.

Second, The Rails philosophy of being a [monolithic](http://yehudakatz.com/2008/11/15/mythbusting-rails-is-not-a-monolith/ "Katz Got Your Tongue? &raquo; MythBusting &#8212; Rails is not a monolith") framework, or as David prefers to put it, [A collection of defaults](http://www.loudthinking.com/posts/33-myth-4-rails-is-a-monolith "Myth #4: Rails is a monolith"). That has benefits. A few years from now, there won't be anyone looking at a Rails code base and asking "What does `#try` do?" It will be standard, so everyone will know it. The down side, of course, is that there's a lot more documentation to read.

The larger a framework gets, the harder it is for someone to read the entire documentation and understand how all the parts fit together. After you've used it, you understand whether `#try` is important or [not](http://avdi.org/devblog/2008/10/30/self-confident-code/ "Writing Self-Confident Code"). But until then, you have to learn it all and you have no idea of whether `#try` is something that should be a pervasive idiom or simply a little trinket tossed in because it's handy.

Put the two factors together and you have what amounts to Rails becoming a large dialect of Ruby, with its own specific way of expressing certain programming ideas, and a central force that is dictating its evolution as a language.

But before protesting too loudly, remember that it could be worse. I recently discovered that despite [a great deal of interest](http://www.google.ca/search?q=java+7+closures&amp;ie=utf-8&amp;oe=utf-8 "java 7 closures - Google Search"), closures will not be in the next official release of the Java language. It seems nobody could agree on how they should work, so the committee decided not to decide. If David Heinemeier-Hansson wasn't the type of person to decide what to do, Rails would be running on .NET today.

So, if you want to program "The Rails Way," start using `#try`. If "The Rails Way" doesn't suit you, you might want to have a look at [Merb](http://merbivore.com/ "Merb | Looking for a hacker's framework?"). It is based on a different philosophy, the assumption that it shouldn't dictate these things to you.

You have a choice.

----
	
Subscribe to [new posts and daily links](http://feeds.feedburner.com/raganwald "raganwald's rss feed"): <a href="http://feeds.feedburner.com/raganwald"><img src="http://feeds.feedburner.com/~fc/raganwald?bg=&amp;fg=&amp;anim=" height="26" width="88" style="border:0" alt="" align="top"/></a>

[Hire Reg Braithwaite!](http://reginald.braythwayt.com/RegBraithwaiteGH0109_en_US.pdf "")