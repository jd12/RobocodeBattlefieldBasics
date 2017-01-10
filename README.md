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

You will note that this is a little different from the Unit Circle you learned in Trigonometry. This model is more akin to the vector system used in airplanes, submarines and (dare I say) tanks.

Sample robot: [WallBanger](http://mark.random-article.com/robocode/lessons/WallBanger.java) - demonstrates how you can move around the battlefield and hit the walls.

Note that even though we called `ahead(10000)` the call returns as soon as the robot hits a wall. (See the [Robocode API](http://mark.random-article.com/robocode/javadoc/index.html).)

The sample robot "Walls" will also show you how a robot can interact with the battlefield walls.

## Bearings

You can get your degree heading by calling `getHeading()`, but there are occasions where you get a Bearing, that is to say, a degree measurement from -180 to 180 that represents your offset from something (a wall, another robot, etc.)

![Image of Bearings]
(http://mark.random-article.com/robocode/bearings.jpg)

By using the bearing, you can easily turn toward something else like so:

```
turnRight(event.getBearing());
```

Which is a pretty common idiom. Note that because a bearing is a value from -180 to 180, calling turnRight() will actually make you turn left if the bearing is negative -- this is by design and it is what you want to have happen.

## Assignment: Make BearingBot Live

For this assignment, use the above information to make a robot called BearingBot that does the following.

1. Scans for their enemy (just whip your radar around in the while (true) loop of your run() method)
2. Turns toward them (right or left, depending; use the bearing reported by the ScannedRobotEvent object passed to the onScannedRobot() method)
3. Fires at them
4. Lastly, rams into them (Hint: use the getDistance() method of the onScannedRobot() object passed to the onScannedRobot() method. The sample robot "RamFire" further demonstrates the virtues of ramming.)

Hint: The code for steps 2-4 will go in the onScannedRobot() method.

Match up your BearingBot against a single other opponent (not more than one - you'll see). Start by matching your robot up against SittingDuck and Target to test, then try with Tracker, SpinBot and Crazy.

Note: Remove the onHitByBullet() method that is automatically generated for you. It's boilerplate code that's just going to get in your way right now.
