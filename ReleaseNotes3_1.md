# SketchyPhysics 3.1 Release Notes #

While this version was over a year in the making it is largely the same as SP3x. The biggest change is that this is a formal version and models can be posted to 3dwarehouse. That said there are a few very exciting features in this release, including sound support and some very powerful new scripting commands. Plus some bug fixes that were long over due.

# Changes in 3.1 Oct 7 #
[See here](http://code.google.com/p/sketchyphysics/wiki/SP31Oct7)

# Changes since SketchyPhysics3RC1 #

  * Sound support. Wav files can be embedded in models for playback at runtime.
  * Added logging support. Allows messages to be printed to the screen.
  * Better runtime error checking of the Scripted field. Makes it easier to find errors.
  * Automatic checking for new versions. Only checks once per day and can be disabled.
  * Many new script commands. [ScriptFunctions](ScriptFunctions.md)

# Bugs fixed since SketchyPhysics3RC1 #
  * Fixed a SU8 crash bug.
  * Fixed bug where operations (like create solids) were slow when the outliner was open.
  * Fixed bug with groups that only contained one group. May break existing models but oh well...
  * Fixed FOV not being saved by at simulation start.