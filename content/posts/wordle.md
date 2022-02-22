---
title: "Wordle is pretty damn smart in many subtle ways"
date: 2022-02-22T18:03:17-03:00
draft: false
---

I love [Wordle](https://www.nytimes.com/games/wordle/). I play it pretty much every single day.
I also play the [portuguese version](https://term.ooo) immediately afterwards too.
It is now part of my morning routine.

Wordle is one of those ideas that just click and immediately have you wishing you were the one to have them.
If you don't know what Wordle is, just click [here](https://www.nytimes.com/games/wordle/) and play it.
Give it a try, you'll probably like it. It won't take you more than 10 minutes.

On a superficial level, there's nothing special about Wordle, every day, you everyone gets a 5 character word, you have to guess what it is.
As you try, you get some information about what you got wrong that helps you move towards the correct answer. You only get 6 attempts.

It is a very simple core mechanic, any programmer with some frontend knowledge could put together something similar in a few hours.

What makes Wordle special is not the core mechanic itself, but the series of very intelligent decisions that were made around this very simple (but still fun) core mechanic.

## No ads, no log-in

When you first open the Wordle website, you're immediately greeted with a simple text tutorial explaining how to play the game.
There are no ads, no login prompt, no attempts to get you to buy skins or donate money.
Compare this with something like [agar.io](https://www.agar.io/) or any other `.io` hyper casual game and you'll see Wordle is truly special in this regard.

I know, people need to make a living. Games are not hosted for free, specially when they're multiplayer games with loads of players.
Wordle was acquired by the New York Times some weeks ago, so I wouldn't expect it to stay this way for too long anyway.

No ads is just icing on the cake, not having them is more a privilege of a game that doesn't need to make money than a true long term differentiator. There are other design decisions that make Wordle truly shine.

## You play one word per day

There's one new word every day. Everyone gets the same word.

You only get to play once, if you try 6 words and fail, Wordle will just give you the answer.
There's no point in opening another browser or cleaning your cache to keep trying.
No need for an account either.
Wordle will ensure you can only try once a day by spoiling you if you fail.
You can't tryhard your way into victory.

It is simple and elegant. Even when you lose, the game ends on a high note.

After you played the day's word, that's it. You want more but you'll have to come back on the next day.

Hoping users will remember your hyper casual game with an average play time of a couple minutes sounds like a sure way to be quickly forgotten, but wordle gets around this just as elegantly.

## Sharing

After you finish a Wordle match, you get a share button. If you click it, you don't get a list of supported social media websites or some twitter OAuth prompt.
All you get is a message saying _"Copied results to clipboard"_. This is what mine for today's puzzle looks like:

```markdown
Wordle 248 4/6

⬜🟨⬜🟨⬜
🟨⬜⬜🟨⬜
🟨🟨🟨🟨🟨
🟩🟩🟩🟩🟩
```

This is, again, smart on multiple levels.

It communicates how your game went in meaningful detail without spoiling the day's word for people who haven't played it yet. At the same time, people who already played today can immediately look at it and know you were struggling in the same ways, which can be pretty fun and engaging.

It also brings players back into the game, but not in an annoying way like Farmville Facebook notifications. Shared Wordle games actively improve your experience by adding a social factor.

You can share it anywhere, it is just some emoji and text. There's not even an image or hyperlink. Anywhere you can type, you can share your Wordle game.

## And repeat

- You play your first Wordle match, you have some fun, but it is short, you want some more but you have to wait, so you move on with your day and forget about it.
- On the next day, you're scrolling Twitter and someone posts their Wordle score. You remember the game exists, you remember you wanted more. You play it again.
- If you're so inclined, you share your score as well.
- Repeat

Do this for a couple of days, and you're hooked. You don't even need Twitter to remind you about Wordle anymore.
Some people in my feed play the new word every day after midnight.

## Takeaway

Some people say the biggest difference between an engineer and a senior engineer is not on the code they write, but on the senior engineer ability to figure out ways to not write code.

Wordle is a great example of how this looks like in practice. It avoids loads of complexity at design time, making lots of features unnecessary and still delivering a superior experience in the end.

No login, just give users a satisfying end when they fail. No social media integration, some emojis they can paste anywhere clipboard will do. No ads, make something people like first, figure money out later. Add a tight social media reminders + leave users wanting more loop, and you have a hit.
