# Robocode Lesson Battlefield Basics

In this lesson, you will become familiar the basics of getting around the battlefield.

If you're unfamiliar with Java's fundamental language constructs, you may wish to read Sun's [Language Basics](http://java.sun.com/docs/books/tutorial/java/nutsandbolts/index.html) tutorial.

## Robot Anatomy

Your robot consists of three parts: the "tank" (body), the gun, and the radar.

![Image of Robot]
(http://mark.random-article.com/robocode/robot_anatomy.gif)
_Image taken from [Rock 'em, sock 'em Robocode!](http://www-106.ibm.com/developerworks/java/library/j-robocode/index.html)_

Each of these parts can be moved independently from each other.

Sample robot: [AnatomyBot](http://mark.random-article.com/robocode/lessons/AnatomyBot.java) - shows each of the three parts turning independently. Incidentally, it also shows how you can print debug statements. (Click on the button with the robot's name on the right to see debug output.)

Notice that the tank moves pretty slow, the gun turret moves faster, and the radar moves faster still.

## Battlefield Measurements

The battlefield is laid out in a cartesian plane with the origin in the lower-left corner. Degree measurements are top-wise; 0/360 is at the top.

![Image of Degree Scale]
(http://mark.random-article.com/robocode/coordinate_system.gif)
_Image taken from [Rock 'em, sock 'em Robocode: Round 2](http://www-106.ibm.com/developerworks/java/library/j-robocode2/?loc=j)_
