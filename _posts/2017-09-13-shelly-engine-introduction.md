---
layout: custom
title: Shelly Engine - Introduction
---

# Shelly Engine: Introduction

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
The Shelly Engine is being developed specifically for the game Shelly Ann, but in theory many of it's parts could be re-purposed to create any 2D game. The game is currently divided into gameplay code specific to the game (Enemies, Projectiles, Levels) and Engine code, which is more generic. Go connect the two parts, there are a series of managers, each of which handle a domain of the game. When I add a new feature to the game, which touches a completely new domain, I will encapsulate this new domain functionality in a manager. 

The features currently in the Shelly Engine are:

### Entity System
It has a system for creating and rendering entities to the screen. The entities are packed together in one contigous datastructure for performance purposes.

### Collision Detection
It has a collision dection system to detect and resolve collision between entities and between entites and the level.

### Sound and Music
It has a system for loading and playing sound effects and music.

### User Input
It has a system for handeling use input (keyboard)

### Particle Effects
I has a simple particle effect system for creating things like blood and scrapnel.

### Debug
The engine has a debug mode that enables you to play the game frame by frame and to highlight important things such as collision and rendering boxes.

