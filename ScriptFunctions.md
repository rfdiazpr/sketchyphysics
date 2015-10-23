# Events #
Events are defined in the Scripted field in the UI.

  * ontouch
```
#Event is triggered when body is touched by another.
ontouch{|toucher,position,speed|
   logLine("I was touched")
}
```

  * ontouching
```
#Event is triggered every tick as long as bodies are in contact.
ontouching{|toucher|
   logLine("Still touching")
}
```
  * onuntouch
```
#Event is triggered when bodies stop touching.
onuntouch{|toucher|
   logLine("Done touching")
}
```
  * onstart
```
#Event is triggered once at the beginning of the simulation.
onstart{
   logLine("Start")
}
```
  * onend
```
#Event is triggered once at the end of the simulation.
onstart{
   logLine("End")
}
```
  * onpreframe
```
#Event is called at the beginning of each frame.
onpreframe{
   logLine("Preframe")
}
```
  * ontick
```
#Event is once per frame just before the physics simulation step.
ontick{
   logLine("Tick")
}
```
  * onpostframe
```
#Event is called at the end of each frame after the physics simulation step
onpreframe{
   logLine("Postframe")
}
```
  * onclick
```
#Event is called when the user mouse clicks a body.
onclick{
   logLine("Click")
}
```
  * ondrag
```
#Event is called each frame the user holds the mouse button after clicking.
ondrag{
   logLine("Dragging")
}
```
  * onunclick
```
#Event is called when the user releases the mouse button after clicking.
ondrag{
   logLine("Unclick")
}
```


# Script functions #

## Simulation variables ##
Varibles are used to communicate between fields and bodies. Setting a variable in the scripted field and reading it in a controller field for example.
  * setVar(name,value)
  * getVar(name)
  * getSetVar(name,value=0)#shortcut function that allows you to get the current value and set it at the same time.

## Inputs ##
Inputs return a value depending on the state of the key/joystick etc. For example key("space") returns 1.0 if the space key is down 0.0 if it is not.
  * key(name)
  * joy(name)
  * joybutton(name)
  * slider(sname,defaultValue=0.5,min=0.0,max=1.0)


## Physics body ##
These functions change the physics body as described.
  * magnetic=true/false
  * nocollision=true/false
  * solid=true/false
  * push(direction)
  * getVelocity()
  * setVelocity(velocity).
```
# setVelocity takes a vector that is the direction the object will 
#be moving and the length of the vector is how fast. It is different 
#from push because it actually sets the objects velocity rather than 
#just try to push it.
onstart{
   setVector([0,0,10]) #set object to moving straight up at speed 10
}
```

  * setLinearDamping(damp)
  * setAngularDamping(damp)
  * getTorque()
  * setTorque(torque).
```
#setTorque does the same thing as setVelocity but with the objects
#rotation 
onstart{
   setTorque([0,0,10])#spin object around blue axis
}
```
  * destroy()
  * teleport(pos,recurse=true)
  * copy(pos=nil,velocity=nil,lifetime=0)
  * split(bdy=self,recurse=0)
  * setCamera()

## Joints ##
  * createJoint(parent,child,type="ball",min=0,max=0,accel=0,damp=0,breakingForce=0)
  * disconnect()
  * attach(child,breakingForce=0)#shortcut that creates a fixed joint connection to child
  * connect(child,type="ball",min=0,max=0,accel=0,damp=0,breakingForce=0)#shortcut for createJoint that uses the current body as the parent.
  * lookAt(target,stiff=10.0,damp=10.0)

## Utility ##
  * playSound(name)#play an embedded sound. See SoundUI.
  * logLine(str)#put a message on the screen.
  * frame()#get current frame
  * group()#get current Sketchup group
  * camera()#get the Sketchup camera
  * position()#get the current position of the body
  * transformation()#get the current transformation of the body.
  * simulation()#get the simulation object(seldom used)

  * evalCurveAbs(name,dist)
  * getCurveLength(curveVerts)
  * findCurve(name)