---
layout: custom
title: Engine
---

# Engine: Introduction

## Intro
I choose to create my own custom engine for the Shelly Ann game, because I wanted to learn the very basic mechanics behind a game engine. Even though using an engine like Unity would have enabled me to develop my game much faster and easier, I chose this as a way for me to learn the nitty gritty details of how a game works. 

I have allowed myself to use a couple of libraries. First of all, to speed up the development of the game just a little bit and second, because I would like to be familiar with some of these libraries that are very widely used and serve as the basis for many game engines. 

### [SDL](https://www.libsdl.org/)
SDL is a library for accessing low level platform features such as window management, keyboard/mouse input and sound. 

### [OpenGL](https://www.opengl.org/)
OpenGL is graphics api that enables you to render graphics on the screen using your graphics card. Is basically enables you to use the computing power of your graphics card to do all the low level calculations such as rasterization and texture mapping. I am using OpenGL to render my sprites to the screen.

### [OpenGL Mathematics](https://glm.g-truc.net)
OpenGL mathematics is a library for creating and manipulating vectors. I am using the structures in this library as the basis of the geometry in my game. This library is propably not an essential library to know, but it provided me with some essential basics for vector manipulation that I found very useful.

## Features
The Shelly Engine is being developed specifically for the game Shelly Ann, but in theory many of it's parts could be re-purposed to create any 2D game. The game is currently divided into gameplay code specific to the game (Enemies, Projectiles, Levels) and Engine code, which is more generic. To connect the two parts, there are a series of managers, each of which handle a domain of the game. When I add a new feature to the game, which touches a completely new domain, I will encapsulate this new domain functionality in a manager. 

The features currently in the Shelly Engine are:


### Level creation
A simple tile editor for creating different levels. Each level is defined as an ASCII file of characters, where each characters defines a tile
or an object in the game world. In this example '.' defines empty space, 'R' defines an invisible tile, '@' is the player and the rest of the
letters define different types of enemies.

```javascript
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
R......................................................................R
R......................................................................R
R......................................................................R
R......................................................................R
RL.......@.....EL.E.L..................................................R
RRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR
........................................................................
```
It is a very simple system that has worked well for me until now. At this point though, I would like to be able
to add some more information to my game objects, such as the direction of the object. In the current version, each zombie
has a default direction (left) and they will all walk in this direction until they hit a wall. To be able to define more
precisely the enemies, there are several approaches. I could abandon the ASCII format and make an actual world editor where
I modify each level "live" in engine and find a system to add objects on the fly. 

I could also add new features to the existing ASCII system, that allows me more control. Right now, I imagine a system where I can
define each enemy before or after the actual level data as a kind of a header (one per line). Then, in the actual level data, I can place each of these
enemies in the place where I want them to be.. This allows me to add attributes to each enemy, such as the direction, the life, speed etc. 

```javascript
E: Slimzombie RIGHT 100 12
R: Slimzombie LEFT 120 5
T: Crawlingzombie RIGHT 100 12
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
........................................................................
R......................................................................R
R......................................................................R
R......................................................................R
R......................................................................R
RL........@......E.R.T.................................................R
RRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR
........................................................................
```
### Rendering
A system for rendering to the screen. The system is using OpenGL as well as fragment and vertex shaders. (MORE DETAILS LATER)

### Collision Detection
It has a collision dection system to detect and resolve collision between entities and between entities and the level.  (MORE DETAILS LATER)

### Sound and Music
It has a system for loading and playing sound effects and music. (MORE DETAILS LATER)

### User Input
It has a system for handeling use input (keyboard). (MORE DETAILS LATER)

### Particle Effects
I has a simple particle effect system for creating things like blood and scrapnel. (MORE DETAILS LATER)

### Debug
The engine has a debug mode that enables you to play the game frame by frame and to highlight important things such as collision and rendering boxes. (MORE DETAILS LATER)

### Menu
A system for adding menus and submenus. (MORE DETAILS LATER)


