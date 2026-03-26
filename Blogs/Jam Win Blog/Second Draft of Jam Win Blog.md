---
type: blog
tags:
  - blog
date: 2026-03-26
title: Second Draft of Jam Win Blog
author: Justin
draft: true
---
NOTE: Introduce we're using Unity and who Brackeys is maybe?

This is a blog about how we made a game in a week that won a jam with 1,400+ entries, but its more than that its a story of redemption and recognition. Its about how a team of four people, none professional game developers, went from barely finishing a game that landed dead average in our last jam, GMTK 25, to winning 1st place in the Brackeys game jam in enjoyment, gameplay and overall categories just six months later. So I want to tell you how we failed, learned from that failure and quickly turned around to produce our best title ever.

Background

I'll keep it brief, but we are a team of four friends: Jacob Engelbrecht, Ian McBee, Gabriel Soares, and me (going by Dalichrome). This is our third attempt at a game jam, we first did GMTK 24 then next GMTK 25 in August 2025. In that second jam we did much more poorly than the first and you can read about [that postmortem here](https://dalichro.me/blog/gmtk-2025-experience/), but to synopsize it, it was a mess from a leadership standpoint and a conceptual standpoint. But I learned a lot from that failure and as the team lead, it made me realize what we really needed to improve on to even be competitive in a jam at all.

The Plan

 This jam, I wanted to relentlessly focus on three things: to make sure we had time to polish the game, to make sure players would enjoy the game, and that our team would enjoy making the game. Makes sense right, but its easier said than done. Unintuitively, the first step we did was to make sure we had time to polish the game, I started thinking about that long before I even knew we would enter Brackeys 2026.1. 
 
 Time To Polish
 
 Specifically, I was thinking about how we could limit the scope without knowing the theme. I tried to think about successful jam games that had limited scope that stayed engaging and fun. The game [Flora](https://itch.io/jam/gmtk-2025/rate/3776086) in GMTK came to mind, a game my friend had really liked in GMTK 25, its jazzy music set to a cozy puzzles about growing flowers and having moles eat those flowers.  Each level is a stage that introduces new mechanics which naturally guides the player into learning them while having fun. I thought we should replicate this format and we should only come up with concepts that are stage based to try this approach of intuitively tutorial-izing players, limiting the scope, and of course while keeping the game fun.

Making it Fun

But every game also needs to be fun, so I also set a second constraint, based on the fact that stage based games need to start from a basic mechanic then build upon it, the basic mechanic that the game is based around **must** be interesting and fun in isolation. Essentially if the game is about jumping, the jumping by itself, lacking music, visuals, et cetera must be enjoyable.

I thought if we only chose concepts that fulfilled those two constraints, even if we lacked development time, we could just cut additional mechanics, it wouldn't sacrifice the soul and enjoyment of the game and we'd have that time to polish. 

With that in mind I also set a hard timeline that we we'd build a playable version of the game halfway through the jam and I'd get friends to act as testers so we'd have new feedback every night to ensure that we could identify and fix unintuitive elements. 

![[Pasted image 20260314182910.png]]

I hoped pre-planning this would ensure that we would choose a well scoped and fun concept. I was so focused on getting something polished since our last jam entries never really got there, that even with these constraints I felt that we still had to scope the concept correctly to our team specifically in order to really accomplish what I envisioned.

Choosing the Concept / Making it Fun to Develop

When choosing a concept, I've learned the most important thing is to not choose what you think others wont do, to not choose what sounds the best and to not choose what will make the best game, but instead to choose something that your team can excel at and will enjoy doing. I heard a lot from my friends Jacob and Ian that they wished they could code more, as both are career programmers more than game developers, so when we were choosing concepts I tried to keep this in top of mind. The theme of the jam was *"Strange Places"* and we did some brainstorming and eventually, three ideas stuck out: a platformer about environments made of silhouettes that a flashlight reveals are not what you think they would be, a game about drawing triangles that disappear ships, and a game about playing a board game that has a whole bunch of strange variant rules, where one rule gets added a stage. 

The platformer, I think failed the basic mechanic is fun rule, the triangle game seemed like a great idea, but it seemed *code-light* to me. A lot of it would be physics work and ship AI work which would be a lot interacting with Unity API and or our AI Pathing Package (Aaron Granberg's). The board game idea didn't really sound fun, but I knew we just had to design it so that the core part was fun and it would meet all my other constraints. I also thought maybe if we based it on chess, Jacob and Ian would be able to spend all their time outside the Unity API making their own chess API and I could hook everything together. This way the concept would maximize what they wanted to do and are good at. So I basically tried as hard as I could to convince the team that despite the fact that it did not *'sound sexy'* that the many chess variants game would be the best for us. 

Everyone was really hesitant. It wasn't really like any concept that we had done before but everyone was willing to hear me out and with enough explaining everyone started to feel excited about the concept. But we still needed to decide on the core mechanic. I had imagined that the simplest form of chess would just be the simplest pieces on a small board fighting each other. I thought about four pawns against four pawns on a 4 x 4 where the first pawn across wins. But I was unsure if it was fun or viable to be the base of the game. So we tested it.

![[Pasted image 20260314182932.png]]

We drew the concept in paint.net and played by just giving each other coordinates and by moving the pictures into the right spot. Even just on the 4x4, we actually had to think a little bit and eventually we decided, yeah this is fun. 

So with that we locked in the theme and started working. 

Development

We split the roles pretty cleanly, I acted like a director/artist/UI developer, Jacob worked on mechanic design and chess backend, Ian did some UI, some design work and a lot of dialog writing, and Gabe did all the music and sound effects. Our primary concern was getting a prototype up and running where someone could play the game against an AI. But since Gabe needed direction for music, before that we first outlined a quick story. Some world event has lead to the creation of 'pawn chess' and our main character wants to go and conquer all varieties of the game, become the first world champion of this new game. He learns how to play in a NYC park, then learns about the "*en passant*" in Paris, gets the new *'poison pawn'* in the Amazon, gets the 5x5 board in Antarctica, and finally gets the knight or the 'cow' piece in the UFO for stage five. With that rough outline, he set off on the music and we began to code. 

![[Pasted image 20260326133418.png]]

UI Design

I was in charge of the UI Design and from the get-go I wanted to have a very tactile and visceral type of chess. Nothing like the clinical and clean interface of 'chess.com' I wanted to instead have something grounded and with character. So instead I wanted a board with perspective and I wanted players to have hands and for the hands to be a way to express the character of the opponent. I thought that adding silly hand movements was a quick and easy way for players to figure out the vibe of the game they were playing and to not just get hooked into the gameplay but also the world of the game. I started with referencing my own hands for the player and scratched up some simple picking up and idle hand frames. 

(PIC: insert pic of old house rules)

For removing pieces, I had the idea that the player would just chuck the piece off the board which I think captured exactly the vibe I was looking for. After I had the player hand set up I transitioned to getting the map working.

For the map, I really just wanted something incredibly intuitive that made people feel like they were visiting different places. So a world map was chosen with little google maps style pins and numbers. It was cheap and easy, but we wanted to have a little line renderer create a line between pins like an Indiana Jones movie, but alas time constraints again.

Essentially I just wanted everything to be as easily understood as possible, so we could reduce tutorial-izing as much as possible. That included the hands, map and of course the chess itself and the design of the pieces. 

Chess  Design

The game within the game, 'pawn chess', as we started calling it, really focuses on constrained movement. Pawns themselves are very restricted pieces and the joy of the game we believed really came from this locked down and limited option gameplay. So when we designed new pieces, we wanted to add new pieces that were similarly constrained. The poison pawn, introduced on level three, destroys any piece that takes it and moves like a normal pawn. The 'cow' was just a knight, but it could not win the game, it was introduced in level five. Jacob was coding the AI and doing the stage design and was able to get these and more coded in before our first build.

(PIC: insert pic of poison pawn and cow piece)

The Prototype

So with the UI done and the backend done, it was all just about wiring them together. Jacob and I did quite a bit of coordinating what I needed from him: legal positions to move pieces, ai moves, what type of move were we doing, when we did a move what was the move type, etc. As soon as we had it hooked up, Jacob began to test the mechanics and I began to start hooking up the stages to the map. I made each stage a scriptable object that took in things like board states, backgrounds, and Gabe's music tracks and just wired those into each map pin. With that we had a minimally viable game done on Wednesday just before our testing deadline. So after work on Thursday, yes we all had day jobs during this, we got together, built the game, put it up on a private itch page and waited for my friend and first tester, Jack.

(PIC: insert gif of first prototype)

Initial Testing

Choice of who you have test your game is really important. You want someone who is honest, likes the genre you're shooting for, gives good advice and won't forget to show up. Jack is all those things and a great guy so I was very happy that he was our first tester. We just barely had a game, no AI hand, no dialog yet and just five stages. But he really enjoyed it. He blasted through it with little complaints and navigated the map and UI with zero problems. His main criticisms were that he found that the AI moving instantly (since there was no AI hand yet) was confused and that it could use some story or dialog to draw it together. As these were things we were already aware of and working on, I was incredibly surprised. This was the moment I realized this was a good game and our direction was right on the money.

Realization

Often times is jams prior I found myself delusional about the state and status of my game. I would think only about how my random generation was so cool and impressive when the combat was spammy and goal was unclear. I would think that the second stage is the best when no one could figure out how to get to the second stage. Therefore for my thoughts about the game to align with Jack's meant something big to me. I thought we've accomplished something that is genuinely intuitive and fun, now if we can polish the hell out of it and then we will have truly made a really good game.

Second Half of the Game

So with that realization in mind, I began to double my efforts. See this year I've been extremely busy between work, starting marathon training, doing development projects, art practice, and more, I was incredibly burnt out going into this jam and just wanted to simply the design process as much as possible. So this was the moment I really began to lock in.

Ian began to work on the Dialog UI as I started work on the AI hands. The whole team was worried about the AI Hand specifically as it seemed like a big lift. But in reality though, since I coded the player hand via using the [DoTween](https://dotween.demigiant.com/) package, all the animations were procedural. So it was actually incredibly easy to swap some of the values and just reuse the same script that I had used for the player while reversing something like throw direction if the hand was labeled an 'ai' hand.

Ian being a young father then had go that night and I began to finish up the dialog UI and incorporate dialog into each stage. Staying up extra late designing the title screen/ logo and drawing all the different fun characters in the game.

The next day, Friday, was just rapid content expansion, we had actually planned out stages six to ten on Wednesday due to some of Gabe's time constraints, so we began to put those stages together. Jacob was recreating broken board states and fixing issues where the AI had no moves, the player had no moves, player had no winning pieces, etc. 

I had another friend, Brendan, come to my apartment and play test and he gave me very similar affirmative feedback to Jack the day before, but helped me tweak some of the piece hitboxes so they felt better.

Ian began to write all the dialog for the game and I started to whip up the game's intro sequence.
We were truly entering the polishing territory at this point.

Polish

I probably spent nearly fourteen hours plus that last Saturday just turning dev art to real art while Jacob did play tests. We planned it so well we even had enough time to make five more bonus stages with all of our unfinished mechanics. 

(PIC: final map)

We were feeling really proud in what we had made and were ready to submit around 1AM several hours before the deadline, but I remembered that Gabe had given me some ambience tracks to back the music and I just didn't have the mental wavelength to figure out how to get the ambience tracks looping and persistent between scene loads. This is when Gabe called in as he just finished a Metal show (*yes Gabe is in a metal band*) and he said as soon as he got home that he would re-render all the music in the game with the ambience in it and I was kinda surprised but also game and said lets do it.

Last Minutes

So as Gabe drove home, I added more hand variants, fixed up some of the 'table' graphics especially the stump and starting table and just gave the whole game one more art pass. We found a fixed a bug that broke the visibility of the clock in WebGL builds (had some async code) and when Gabe finally came back and rendered the tracks, we quickly put them in the game did a short test, submitted at around 4AM and then we crashed.

Reception

I woke up on Sunday after about 5 hours of sleep and saw all these amazing reviews. People saying they hope we win and that they thought it was 'full release' even. A type of positivity we've never received before. The whole team was abuzz and frankly in shock that we finally had made a good game in a jam! The next two week were frankly, an anxious waiting game. I knew that we were doing well, so I really wanted to do everything I could to win. But there's a weird quality in a jam where only other developers can vote as you want to be very nice and get people to play your game. So I felt like there was probably a lot of people leaving positive comments just hiding their true impressions of the game and just trying to field people to their jam page. So it was kind of hard to feel which comments were genuine and what people were really thinking. So I just tried to leave nice comments on devs that I thought would enjoy our game, but the whole psychological element in peer voting, especially when you think you might have a shot, is anxiety provoking. I in total played around 50 games and called it at that.

Winning

I'm American so the results for the Jam came out on Sunday at 7am on the day that Daylight Savings time '*springed back*'. Not only that but I had had laser eye surgery two days before. So I was wearing goggles to prevent rubbing my eyes in my sleep and woke up what I felt like was the middle of the night, checked my phone, which was super bright and blurry still and saw it was around 7:20 AM. I quickly checked the results and learned that we won first in overall, first in gameplay, and first in enjoyment. The feeling was a mixture of shock, totally overwhelmed, and brimming with joy. I'm been developing games for more than seven years now and to have such recognition felt unreal and so good, like I finally knew that I was good at this. I then thought immediately I have to let everyone else know and called Gabe as he messaged back first. He was laying bed with the flu, voice gravely as he hadn't had a wink of sleep all night. Then Ian called in, turned on his camera, he was on stage about to perform music for his church. And we were all just kind of in this weird state of shock and excitement, trying to figure out, what does this mean?

(PIC: Results Page)

Whats Next?

Well its been a couple weeks, and the answer is we're not done with this concept. We want to keep making 'House Rules' in fact we've already renamed the game to 'Rulehouse' and made a second patch, with mobile compatibility, premoving, and hardmode, which you can check out on Itch. But I want to say how grateful we are to everyone that voted for us in the jam and to all the readers reading this.

We've made a steam page now for 'Rulehouse' and it'd be great if you could wishlist the game, so we can notify you when it comes out.

(PIC: Wishlist Pic)

In addition, if you want to follow our itch page, my bluesky, or this medium page. Or even see some of my other blogs on my own site, it'd be much appreciated!

Thanks!

