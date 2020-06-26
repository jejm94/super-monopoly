## Adventure in Super Monopoly and Reinforcement Learning
##### Jesse Moore
------

![picture](“https://www.publicdomainpictures.net/pictures/210000/velka/monopoly-game-board.jpg”)

Research Question: Can I use Reinforcement Learning to create an optimal strategy for playing Super Monopoly?

Spoiler alert, I'm still working out the kinks a bit, but the enviroment is vast, complex, and a lot of fun to play around in. My love of Monopoly comes from early chidlhood years playing with my grandpa and brothers by the poolside. Being all arithmetically gifted, the games went lightning fast. Naturally, we sought to add some spice to the game when a regular single-board game would barely fill an hour for us. And thus, Super Monopoly was born! The new rules are simple and are as follows:


1) n boards with each ‘go’ space acting as a single spot warp from board i to board i + 1 
2) All groups of colors on different boards are distinct (i.e., each color has a subscript per board like red1, red2, …)
3) Utilities now have X5 dice roll multiplier for owning one and X20 dice roll multiplier for owning both
4) Players begin with (normal starting money) + ((n – 1) X 500)
5) Players can now choose to invest in any complete set of properties owned by other players


My approach with this project was to get my environment--the game that I hold so near and dear to my heart--absolutely perfect. While the agent is not quite finished, I do believe that the game itself would be fully playable by two humans with a few print statements for guidance. The State Space and Action Space of this grew wildly out of hand, but I was determined to be as accurate as possible to the real thing. 

The granularity of player interactions and decsisions are what really challenged me. My ultimate choice was to lump things together in a single type of actions. The "invest" action would make a random investment, the "liquidate" action would mortgage your cheapest assets, and the "build" action would put a set of house on your best properties. There's also the option of not doing anything at all and just rolling, of course.

I wanted so badly to implement the complex trades and deals that my brothers and I have devised over the years, but I fell into the trap of biting off a bit more than I could chew. It is better to start from a simple, functional model and to gradually add complexity; that way issues and other bugs can be isolated and addressed efficiently. 


### RL Approach

For the reinforcement learning aspect of this, I referenced a wonderful paper entitled "Learning to Play Monopoly: A Reinforcement Learning Approach." (Link will be listed below). Their simplification of the state space is something I tried to reproduce, but with the added aspect of accounted for equity investments. I was aiming and nearly succeeded at a classic Q-Learning approach. A 3-dimensional matrix of all zeros was created for intitial values. The dimensions were money, space, and location, but a simplified version of the information available on the board. The four simplified actions that I listed would have been tested for each state and the one with the highest reward would have been chosen.

Naturally, an element of epsilone-greedy would have been present in order to explore from time to time and not be stuck in local extrema. My metric of interest would have been the numnber of turns in the games and the margin of victory. Two trained agents going neck and neck would likely have a long, epic battle in Super Monopoly. 

So here you have what I have created so far. Needless to say, it will be improved on in the coming days and weeks because it's shaping up to be something that I am trully proud of. I've learned a lesson in humility, but still had an amazing time approaching this problem. 

http://doc.gold.ac.uk/aisb50/AISB50-S02/AISB50-S2-Bailis-paper.pdf
