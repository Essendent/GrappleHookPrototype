# GrappleHookPrototype
A simple grappling hook prototype package for unity 2020.3

Contains a few simple scripts and operates on a very simple premise. When the grapple makes a connection it will compare the weight of the object against the player's weight and use that to determine which object should be moved when the player reels in the grapple. Currently the line acts more like a bungee cord than a solid rope.
As connected objects move farther apart, the force pulling them together will grow stronger.

Controlls:
  - left click will fire the grappling hook, if using physics grapple the "hook" will travel infinitely so returning the grapple will be necessary to fire again.
  - left click (while hook attatched to an object) will reel in the grapple. If the object is lighter than the player it will be pulled, otherwise the player will be pulled.
  - right click will break/return the "hook"
  - w/a/s/d for movement, currently no jump function and diagnal movement is NOT supported.

On the Player Object:

    -BasicCharacterController
      Move Force = the strength of physical force applied to the player when pressing w,a,s or d. Currently no diagnal or jump.
      Turn Sensitivity = A value multiplied against mouse input and used to rotate the camera on the y AND x axis. Recommend slow increments.
      X Angle Max = An absolute value of how far the camera is allowed to rotate on the x axis. A range between 0 and 1 where zero is full clamp and 1 is no clamp.

    -GrappleController
      Physics based hook OR raycast based hook, USE ONLY ONE AT A TIME.
      Physics Grapple will fire a physical object that will "hook" onto an object it hits, if it hits something.
      Raycast Grapple will immediately grapple and object if it hits one. Due to this, it can be spammed to grapple something unlike physics grapple which must be reeled in.
      Firing Point = the transform that the grapple will be fired from, in the transforms local positive z axis.
      Grappling Hook Prefab = the game object that will be fired in the physics grapple mode.
      Line Renderer = placeholder to provide visual confirmation of grapple state.
      Grapple Strength = the strength of force that will be applied to the player when the grapple is reeled in.
      Grapple Object Strength = the force that will be applied to an object weighing less than the player when the grapple is reeled in.
      Elastic Force = a multiplier used to increase the returning force exerted on player/object when the grapple is "stretched".
