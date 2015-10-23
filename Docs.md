[Quick Reference Card](http://sketchyphysics.googlecode.com/files/SketchyPhysics%20-%20Quick%20Reference%20Card.pdf)

# Basics #
When you run Sketchup you should see several new tool bars.
If you don't see the toolbars go to View->Tool Bars and turn on all the Sketchy ones.

This is the main tool bar
![http://sketchyphysics.googlecode.com/files/SketchPhysics-Toolbar1.jpg](http://sketchyphysics.googlecode.com/files/SketchPhysics-Toolbar1.jpg)

The three buttons are Play/pause,reset and UI.
  * Play/pause starts and pauses the physics simulation.
  * Reset resets everything.
  * UI opens a dialog has convient versions of the toolbars and will soon host a easy to use attribute editor developed by Jim Foltz.

Load one of the examples and press the play button on the toolbar. You should see the scene animate.

## Dragging ##
  * While the scene is playing you can use the mouse to drag objects around the scene.
  * Press and hold left mouse button to drag horizontally. Hold SHIFT to lift up and down.

# Creating #
Any group can be a physics object. But the physics engine can only simulate certian types of shapes. Those shapes or "primitives" are box,sphere,cylinder,capsule,chamfered cylinder and convex hull. This isnt as limiting as it sounds because you can combine those simple primitives into far more complex shapes.

## Primitives tool bar ##
The easiest way to create a physics object is to use the SketchySolids tool bar.

![http://sketchyphysics.googlecode.com/files/SketchySolids-Toolbar1.png](http://sketchyphysics.googlecode.com/files/SketchySolids-Toolbar1.png)

Load one of the examples and try adding a few primitives to see how they react.

Notice how the primitives can be built on top of each other.

### Box ###
Fastest and most flexible of the primitives.
Can be scaled in any direction.

### Sphere ###
Can be scaled in any direction.

### Cylinder ###
Can only be scaled uniformly or non-uniformly in the up/down direction. You cant "squash" the cone.

### Cone ###
Can only be scaled uniformly or non-uniformly in the up/down direction. You cant "squash" the cylinder.

### Capsule/chamfer ###
Can only be scaled uniformly.

### Floor ###
The last primitive (the gray one) is a "floor" you usually only add one per scene. It gives the objects something to land on. If you dont have a floor the objects will just fall.

Scaling may cause unpredictable behavior.

### Convex Hull ###
Used when none of the existing primitives will do.
Made by right clicking a group.
Group must contain only faces (no sub groups)
The shape is a "shrink wrapped" version of the mesh.

Here is a very detailed explanation of what a convex hull is:
http://www.rustycode.com/tutorials/convex.html

Scaling may cause unpredictable behavior.

### Static Mesh ###
Acts as the non moving part of a scene.
Can be almost any arbitrary mesh but it cannot move.
Made by right clicking a group.
Group must contain only faces (no sub groups)

Scaling may cause unpredictable behavior.

## Object attributes ##
Right click an object to set its attributes.

### Frozen ###
Object will not move until touched by another object. Very handy when setting up scenes.

### Static ###
Object will act solid and unmovable

### Ignore ###
Object will be ignored. Used to keep an object from having collision. Not quite the same as NoCollision

### NoCollision ###
Object wont collide with anything.
**Doesn't work yet.**

### EmbededGeometry ###
Not used anymore. Will be removed

## Joints ##
![http://sketchyphysics.googlecode.com/files/SketchyPhysicsJoints-Toolbar1.png](http://sketchyphysics.googlecode.com/files/SketchyPhysicsJoints-Toolbar1.png)

Hinge is like a door hinge. But it can also be a wheel. Hinge is the joint you will use most often.

Slider allows the object to move like its on a rail.

Corkscrew is a combination hinge and slider

Spring is like a slider but the object will try to "spring" back to its original position

Universal joint is like 2 hinges at right angles to one another. This joint can become unstable and fly appart if moved to fast.

Ball joint will allow an object to move freely around a single point. This joint is also unstable if moved too fast.

## Joint connector ##

The joint connector tool is used to connect and disconnect objects from joints.

### Example ###
  * Create a box
  * Create a slider on top of the box
  * Click the Joint Connection Tool (JCT)
  * Click on the box
  * Hold CTRL and click on the slider joint.
  * Now the box is connected to the slider joint. If you press play the box will only move along the slider
  * Reset the simulation
  * Press JCT
  * Click the box
  * Notice both the box and the joint are selected
  * Press shift and click on the joint. They are now disconnected

You can connect joints to multiple objects by selecting the joint first, then selecting each of the objects in turn.

You can connect connect a object to multiple joints (rarely done) by selecting the object first and then the joints.

## Joint attributes ##
If you right click a joint you can edit its joint settings. Each type of joint has its own  settings.

### Hinge ###
  * Min=Minimum joint angle (0 to -360)
  * Max=Max joint angle (0 to 30)
  * Acceleration=The joint will act like a motor. Positive and negative values will work.
  * Dampening=Acts like a brake to keep the motor from spinning out of control.

### Slider ###
  * Min=Min slide distance in inches. Should be negative
  * Max=Max slide distance in inches. Should be positive

### Spring ###
  * Min/Max=same as slider.
  * Accel=Adjust how hard the spring will try to pull the object back.
  * Damp=Adjust how fast spring will try to pull the object back.


## Compound objects ##
You can group 2 or more objects to make a compound object. This means that the objects will move together as if they are attached.

If you made a table out of 5 boxes (4 legs and a top) then started the simulation the table will fall appart as soon as something bumped it. If you group them they will behave like a table.

## Grouping joints ##
Joints can be grouped with other objects. Because this allows the joint to move it allows you to make more complex machines.

**NOTE:** You can only connect objects to joints that are only one layer deep inside a group.

<more to follow>

# Bugs and known issues #
  * Deleting joints without first disconnecting can the connection tool to get confused.
  * In general you should avoid copying joints. Copying top level joints _should_ work. But any joint in a copied group will not be recognized.
  * If you copy a object that is connect to a joint that object will also be connected to that joint.
  * Certain objects can only be scaled in one direction. See the prims section for details.
  * Flipped objects will usually fail to work.
  * Grouping just joints will crash Sketchup.
  * When using the joint connection tool you may see "ghost" versions of selected objects
  * Having any of the "info" windows (model info, materials, outliner etc) open will slow the simulation down.


# Future work #
  * Animation saving and editing
  * Lots of new UI and usablity improvements
  * Gears

# Credits #
  * Main developer: Chris Phillips
  * Icons: Daniel Slavin
  * Webdialog interface: Jim Foltz
  * Physics engine: [Newton Physics SDK](http://www.newtondynamics.com/news.html)