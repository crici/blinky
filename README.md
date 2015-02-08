# blinky
Proof of concept for a multi-platform, native Gradle project

## Scope

Gradle evolves more and more in the native application space. 
This project tries to evaluate its support for embedded platform development which aim different 
target architecture / embedded OS combinations in a common Gradle based framework.

The initial project consists of three simple components:

    apps/blinky		The main application written in C
    comps/timer		A simple timer driver mock-up written in C.
    comps/gpio		A simple library that provides control of a GPIO port, written in C.

The goal of this proof of concept is to build different variants of the blinky application in one shot.
The different variants differ by

	buildTypes	_debug_ and _release_
	flavors		_red_ and _green_

The mix of flavors and build types is set up in central `*.gradle` files at top-level project scope in:

	project/gradle/
		buildtypes.gradle	
		flavors.gradle		
		platforms.gradle	
		repositories.gradle	
		toolchains.gradle


### Build Types

	debug 
	releae

### Flavors

	green
	red

### Platforms 

	x86 		Simualtion of the application on x86 based hardware (PC/Mac)
	x86_64		Simualtion of the application on x86 based hardware (PC/Mac)
	arm 		Bare metal ARM applicaiton (under development)

