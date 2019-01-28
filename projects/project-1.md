---
layout: project
type: project
image: images/dotsicsmenu.png
title: dots.ics
permalink: projects/dotsics
# All dates must be YYYY-MM-DD format!
date: 2019-01-22
labels:
  - Java
  - Eclipse
summary: An agar.io clone created in my ICS 111 class.
---

For my final project in my ICS 111 course at UH Manoa, we were assigned in small groups of four to create a game that utilizes EZ Graphics, a custom Java library that allows the user to create animations and pictures in a window resolution determined by the user. Before starting the actual programming, we were responsible for creating an outline for the game such as the concept of it, and what kind of classes in Java we need to create for the whole project. They did this so that each member is responsible for contributing an equal amount of effort and work into the whole project (which I personally thought was an excellent idea). 

## History of our game

Our game is based off of a simple, yet popular game that blew up in 2015 called [agar.io](http://agar.io/). Although the original game was written in Javascript and C++, we thought it was a good idea to write it in Java to demonstrate our understanding of the language itself. Here is a comparison between our game: 

<img class="ui medium centered rounded image" src="../images/dotsicsgameplay.png"> 

and the original:

<img class="ui medium centered rounded image" src="../images/agariogameplay.png">

## Well, how do you play it?

The player starts off as a small circle on the screen. You are able to control the circle via mouse as it will follow your cursor. The speed of which your circle follows your cursor depends on the size of your circle, and the size of your circle depends on how many small dots you eat. There are also A.I Computers who are also "playing the game". The objective of the game is to collect the small dots on the screen and eliminate other players. If your circle is significantly larger than the enemy, then you have the ability to consume the other player's circle which also makes you larger. Once all the enemy A.I has been eliminated, you win. To watch gameplay, here is a [demo](https://youtu.be/7lx8PrkpHqQ) posted via Youtube by one of my group members, Gian. 

## My personal contributions

For this project, I was responsible for creating the dot class. Within the game, there will be multiple randomly generated dots on the playfield for the player to consume. The class includes a randomizer for the RGB properties and X and Y properties to randomly color and place the dots. To avoid having white dots on the screen, there was also a custom boolean method implemented that detects if the random dot object is not white, then it is safe to place. Here is a small snippet of the code:

```java
	public Dot(int x, int y) { //Constructor
		this.x = x;
		this.y = y;

		//If the random generated r,g,b values are not in the white scale palette, draw a EZCircle element for a Dot object
		if(isRGBNotWhite()) { 
			drawDot();
		}
	}

	/** Draws a Dot object as an EZCircle */
	public void drawDot() {
		int border = 4; //Thickness value for the outline border for the Dot EZCircle
		dOutline = EZ.addCircle(x, y, DOT_RAD * 2 + 4, DOT_RAD * 2 + border, c.darker(), true); //The color of the outline is a darker version of the color of the dot
		dot = EZ.addCircle(x, y, DOT_RAD * 2, DOT_RAD * 2, c, true);
	}
```

You can find the source code to dots.ics [here](
https://github.com/sjavella/agar.io).

