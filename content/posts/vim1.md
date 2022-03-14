---
title: "Seeking That Sweet Sweet Vim Joy"
date: 2022-03-13T13:29:36-03:00
draft: false 
---

Text editors are a funny piece of software. They are undeniably important. You can't write any code without them[^1]. 
Text editors are like the software engineer equivalent of a hammer for a woodworker: not the only tool we use, but one we'll certainly use a lot during our entire careers.  

It would make sense, then, to invest  as much time as possible trying to be as good as possible with text editors, right? It is not that simple. Just like you can't be a great woodworker by just being extremely good with a hammer, you can't be a great software engineer by just being very good with a text editor. In fact, as engineers climb the seniority ladder, they tend to spend less and less time actually writing code, which further diminishes the expected returns of being good at editing text.    

There is one important difference, however, between hammering nails and using a text editor: _you can get better at hammering nails by just doing it_. 
A woodworker that has been in the business for decades will hardly ever hit his fingers with a hammer. 
An engineer can spend an entire career writing code and still be painfully inept at using his text editor of choice, using the most basic features that any text box on a browser would provide and nothing else.

## It's not about productivity, it's about joy

I strongly believe developers should seek to make their work tooling as [joyful](/posts/joy) as possible. Pressing and holding backspace until an entire line of text is deleted doesn't bring joy.

Getting better at editing text like having a 4k monitor. It won't allow you to deliver software any better or faster. You can type and read code perfectly fine on, say, a full HD monitor. But looking at text characters on a 4K monitor is just more enjoyable. It's like getting a next generation video game console. When you first play the new-generation games, they don't look that much better. But when you go back and play the old games again they look much worse than you remembered.

Going beyond the basics with a text editor feels the same way. When you first start using multiple cursors to edit several lines at once, it feels nice but you don't make a big deal out of it. It is only much later when you're used to have multi-cursor editing and for some reason you can't use it that you realize how much better it is to have it. 

Once you're bitten, there's no way back. You'll start to mildly suffer when watching colleagues editing text inefficiently in zoom calls. I sometimes fail to restrain myself and just start yelling keyboard shortcuts at people I have more intimacy with. I know, I'm a terrible person. 

## Seeking the joy of Vim

If you've read this far, you're quite probably expecting me to start talking about the virtues of Vim or Emacs now. I'm not going to do that. I've never used any of these for anything other than some occasional file editing on some terminal I SSH'd into. I'm nothing but an average VSCode/IntelliJ Joe who really appreciates keyboard shortcuts and multi-cursor support at this point.

I'm planning to change that. If I'm going to annoy my colleagues by telling them about shortcuts that will save them less than 5 minutes over the course of an entire day, I might as well just annoy them by telling them how much better Vim is instead. 

I read many times about the benefits of both Emacs and Vim, and tried to actually use them for work a couple times. In my previous attempts, my motivation quickly fizzled out as I struggled with all the new shortcuts and the notoriously poor on-boarding experience of both editors.

This time, however, I'm hoping to get past these initial hurdles by making my efforts public. Starting now, this and all future posts in this blog will be written using nvim.  

## The rules

* __Real nvim, no VSCode addons__: I'm going in cold turkey. This entire post was edited with my very basic Vim knowledge in neovim and nothing else. 
* __No distros__: I'm not using any neovim distro with pre-installed addons of any sort. Just raw neovim, any addons will have to be added by me.
* __Hard mode__: I re-mapped my arrow and other navigation keys to `Nop`. If I'm going to use Vim, I'm going to use it properly with HJKL.
* __Blog posts only -- for now__: I'm not going to force myself to use vim for work. Not for now at least.  

That's it. I'll stick to these rules for a couple more posts and write my impressions. Maybe if things go well enough I'll also give it a shot at work too.

[^1]: Not with an acceptable level of productivity at least.
