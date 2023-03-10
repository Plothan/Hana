# Hana

Hana is an execution framework intended as a temporary solution for scheduling coroutines in Lune.

Hana is built similarly to how Roblox's coroutine scheduler work as Hana acts as the main loop, so its `start` function (require("src/init")) is a yielding operation.

Hana works by searching for `.work.luau`s in a directory which returns a function that expects a `task` library. Hana itself is composed of two parts, the first is a scheduler and a module importer, while the second is a coroutine yielding utility that mimic Roblox's `task` library.

Keep in mind that once the scheduler starts running, it will yield the calling coroutine until all imported coroutines + coroutines that were created during execution finish execution. As such, treat the calling coroutine *(or file)* as a starter function that purely starts the scheduling + all other pre/post execution.

## Name
The "Hana" name is actually a Hawaiian word which means Work, hence the primitives of Hana are called "Workables"!

## Usage
Currently there is no documentation, though the source code is simple enough so go take a look at it.

## Notes
* Once a coroutine yields, it will only resume again in the next frame.
* Lune V0.0.3+ is supported for running Hana.
* The Lune project might potentially implement and expose a custom `task` library similar to Roblox's, which would be used for scheduling coroutines, until then, this library is useful!
* You can look both at the `.lune` and `test` dirs for examples. 