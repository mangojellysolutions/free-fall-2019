# FreeFall2019
24 Hour Challenge: Programming for a total of 24 hours with sittings of no more than 1 to 2 hours per day to create a game base on the Atari Jaguar game 'Down Fall' using only Javascript, HTML5 Canvas, and Notepad ++ (without any code hints or completion). Additional libraries, game engines and frameworks will not be used, all code will be started from scratch / zero / nothing.

# Diary 

2hrs 
Started by creating a basic skeleton layout using the move, line to and shape canvas commands to draw simple graphics, scoreboard and a gradient filled background.  A basic player object was created with simple methods for draw and lateral movement across the screen controlled via the keyboard.  Also a simple platform object was create containing just the initialisation and draw methods.  The start of the main game loop was added to draw these to screen.

3hr
Added platform and player collison methods to allow player to drop and land on a static platform.  Allowed player to wrap if the sprite leaves the far right / left and bottom of screen.   Next I moved onto dealing with multiple platforms and added code to handle 
spawning of plaforms (at the moment just two) and storing them within an array. Last minute additions: methods to deal with platform movement with wrap around and making sure the player stays on the platform whilst it is moving.  

4hr 
Added a simple title and game over screen and implemented scoring logic.  The scoring is based on the amount of time the player stays on the platforms and avoids falling off the bottom of the screen.  If the high score is reach the high score is then adjusted to that of the players score.  If the player falls off the bottom or disappears off the top of the screen when riding a platform then the game over screen is shown.  The player hits any key to move back to the title screen and again to start the game where their score will be reset to zero but the high score will be maintained.  Finished off with a quick refactor.

5hr
Added simple parallax scrolling using wrapping rectangles for time being. Aligned game text.

6hr
Added a basic random platform generator that regenerates a set of platforms when the current set leaves the top of screen.  

6hr Retrospective:
Breaking down the sittings to 1 to 2 hours has lead to a defined achievable goal being set for the sitting.  The goals is to fullfil jus the minimum needed to implment a feature, these are are then built upon / fleshed out in later sittings.  If this was one continuous sitting i.e. a full day I believe that less would be achieved as the goals would have been thought of more in the larger picture.  That along with less rest to allow the brain to reset and digest what work has been achieved.  Even when I am not working on the project I have thoughts about what to work on next and how to tackle the next upcoming goal.  

7hr 
Worked on the random platform generator allowed for the platforms to distributed across the width of the screen evenly. Implemented a spawn time allowing multiple rows of platforms to be spawned between intervals.  I had some slow down of drawing which was due to test output so went through the code and cleared out these as no long need. Introduced my self to the [].reduce function which I have heard of but never used before.  

8hr
Added a small bit of animation to the player, a kind of a head bob. Added player gravity with increasing fall rate when dropping.  Added friction and acceleration and deceleration, player ramps up the speed until they reach the max speed when walking on a platform, player will slide when changing direction and forward speed will decrease to zero when dropping.  

9hrs
Some code refactoring, grabbed some graphics from https://opengameart.org to use as platform graphics and built a sprite sheet routine to display the individual platform graphics.  Started splitting out the main loop into separate draw and update sections.

Usefull links
https://itch.io/
https://opengameart.org/content/handpainted-platform-tileset
https://opengameart.org/content/block-breaking-block-pack-hd2
https://opengameart.org/content/ball-set-svg
https://www.fosshub.com/Synfig.html
https://twitter.com/GameDev_studio

10hr
Updated the platform draw code to use the new graphics and modified the platform objects spawner and bounds detection methods to use the width of the graphic rather than an overall length.  Identified a few bugs; when the player first starts they cannot travel left or right through the air as I have removed this ability to make the game harder, this has a knock on effect as you can't move the player until it hits a plaform when the player is respawned. This means that you have to hope there will be a plaformed spawned directly under the player otherwise you will fall off the screen. I need to allow the player to move left or right whilst falling for the first drop.  The player animation doesn't work when travelling left.  Also the source is becoming hard to work with.  I need to section it out into object per page.

11hr 
Looking at some graphics for the parallax scroll.  After a bit of image internet searching for inspiration I decided that I would use a simple transparent hex background.  I put together the code in a separate html file allowing me to play about with creating hexagons in different formations and colours until I get something close to what I want.  Finished with 2 groups of hexagons running down the left hand of the screen the smaller hexagons are the foreground the larger the background.

13hr
Worked on the background layout to alow for seamlessly scroll. After which I needed to get these out of the canvas as separate images.  Getting the code down to actually produce these as usable transparent images which was a bit harder than I thought.  Luckily someone had perfected the task which I was able to lift into my code.  Finished with some code clean up and arrange the images on-screen to where they would be in the game.

14hr 
Added new style platforms to the hexagon background so it ties in nicely with the style and worked on platform generation and spacing logic which is going back to the vector drawing rather than the sprite sheet.  Also would like to add a speed difference when the platforms move.  The smaller the plaform the faster it will move so you will get platform crossing over each other making the game harder.

15hr Applied hexagon background to the main game

16hr Playing with a neon effect for the hexagons.

17hr Applied neon hexagon background to the game.  Also applied the new style vector drawn plaforms but only for the smallest platform and added a neon effect to these.  The draw rate is now slow so will have to create these as graphics.

18hr Added random spawning platform code to place the platforms across the screen

20hr Platforms are now firest rendered to an image array and these images are used to speed up drawing.  Code clean up including separation into separate files for objects.

21hr A number of different sized platform images are now rendered.  More code clean up

22hr Created player animation as a svg in inkscape, implement async image loader, neatened up some code.

23hr Implemented player animation, fixed scoreboard layout, bug fixes

24hr Implemented animated rings to collect which will increase score, stylised start and end title text

Extra siting.  Cleaned up but didn't alter code calls i.e. removed spaces, comments, renamed some methods etc