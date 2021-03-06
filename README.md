# Unreal Multiplayer Course - Section 4 - Krazy Karts

In follow up to our hugely successful [Complete Unreal Engine Developer](http://gdev.tv/urcgithub) course we bring you [Unreal Multiplayer Mastery](http://gdev.tv/uemgithub) - as on featured on [Epic's UE4 blog](https://www.unrealengine.com/en-US/blog/getting-started-with-unreal-multiplayer-in-cpp).

In this section make your games feel responsive no matter what network conditions your players face. Understand and explain concepts such as lag. Devise mechanism to compensate for lag in your games.

You're welcome to download, fork or do whatever else legal with all the files! The real value is in our huge, high-quality online tutorials that accompany this repo. You can check out the course here: [Unreal Multiplayer Mastery](http://gdev.tv/uemgithub)


### 0 Introduction to Krazy Karts ###

+ We overview the sections topics.

### 1 Creating A Go-Kart Pawn ###

+ Create the project.
+ Create a pawn.
+ Setup GameMode Spawning.
+ Setup Camera.
+ Attach throttle controls.

### 2 Understanding Forces And Movement ###

+ Revision of forces in physics.
+ Calculating movement from force.
+ Providing the driving force.

### 3 Blocking Movement Without Physics ###

+ Setting up collision volumes.
+ Sweeping with `AddActorWorldOffset`.
+ Resetting velocity on collision.
+ Refactoring the `Tick` function.

### 4 Rotations With Quaternions ###

+ Angle axis rotations with FQuat.
+ Adding rotations actors.
+ Rotating our velocity.

### 5 Simulating Air Resistance ###

+ Understanding air resistance.
+ Getting the "speed".
+ Calculating force due to air resistance.

### 6 Simulating Rolling Resistance ###

+ What is rolling resistance?
+ Finding the gravity in Unreal.
+ Implementing rolling resistance.
+ Example rolling resistance coeffients. 

### 7 Steering And Turning Circles ###

+ Why we get turning circles.
+ Calculating our rotation geometry.
+ Correcting steering behaviour.

### 8 Server Functions & Cheat Protection ###

+ How to change state from the client.
+ Introduction to RPC server functions.
+ What is validation?
+ Implementing validation for input.

### 9 AutonomousProxy vs SimulatedProxy ###

+ What are Actor roles?
+ Investigating the network roles.
+ Updating the `AutonomousProxy`.

### 10 Sources Of Simulation Error ###

+ How simulation error effect our game.
+ Overview the different sources of error.
+ Investigate approaches to eliminating them.

### 11 Replicating Variables From The Server ###

+ Overview of property replication.
+ Replicating the actor position.
+ Setting and reading the property.
+ Replicating the actor rotation.

### 12 Triggering Code On Replication ###

+ Deep dive on property replication.
+ Setting the network update interval.
+ Notify on replicate.
+ Simulate between updates.

### 13 Smooth Simulated Proxies ###

+ Replicating velocity.
+ Why is movement jerky?
+ Replicating control input to SimulatedProxy.

### 14 Simulating Lag And Packet Loss ###

+ What is lag?
+ Simulating lag and packet loss.
+ Why does lag cause glitching?

### 15 Replay Autonomous Moves ###

+ Why do we reset when accelerating?
+ Keeping AutonomousProxy ahead of the Server.
+ What information needs to be sent to the server.
+ Compare our different simulation approaches.

### 16 Planning Client-Side Prediction ###

+ Pseudocode for client prediction.
+ Adding structs for synchronisation.

### 17 Replicating Structs ###

+ What do we have already?
+ Replicating state via a struct.
+ Sending the `Move` struct via RPC.

### 18 Simulating A Move ###

+ The `SimulateMove` signature.
+ Updating the canonical state.
+ Implement `SimulateMove`.

### 19 Unacknowledged Move Queue ###

+ `TArray` for the Move queue.
+ Tidying the move creation code.
+ Printing the queue length.
+ Removing acknowledged moves.

### 20 Simulating Unacknowledged Moves ###

+ Simulate all moves.
+ Testing for smoothness.
+ How can we still make it glitch?

### 21 Fixing SimulatedProxy Prediction ###

+ Ensuring the Server simulates once.
+ Local prediction on the client.
+ Making smoother predictions.

### 22 Refactoring Into Components ###

+ Red-Green-Refactor process.
+ How to spot your "code smells".
+ Identifying a suitable refactor.
+ Planning our refactor.

### 23 Extracting A Movement Component ###

+ Create and name the component.
+ Move member declarations across.
+ Move function implementations.
+ Fix build errors.

### 24 Extracting A Replication Component ###

+ Creating the component.
+ Enable replication.
+ Move member declarations across.
+ Move function implementations.
+ Fix build errors.

### 25 Decoupling Movement & Replication ###

+ What happens if we disable the replicator?
+ Allow the Movement Component to tick.
+ Getting the information to replicate.

### 26 Linear Interpolation For Position ###

+ How does linear interpolation work?
+ Overview of client interpolation.
+ Pseudocode for client interpolation.

### 27 FMath::Lerp For Client Interpolation ###

+ Ensure movement replication is off.
+ Updating the time variables.
+ `FMath::Lerp` vs `FMath::LerpStable`.
+ Implementing the pseudocode.

### 28 FQuat::Slerp For Rotation ###

+ `Slerp` vs `Lerp`.
+ Store tranform instead of location.
+ Implementing `Slerp`ed location.

### 29 Hermite Cubic Spline Interpolation ###

+ Understanding jarring movement.
+ How velocity can help or hinder.
+ A brief overview of polynomials.
+ Introducing the Hermite Cubic Spline.

### 30 FMath::CubicInterp For Velocity ###

+ Slopes, derivatives and velocity.
+ Using `CubicInterp` for location.
+ Using `CubicInterpDerivative` for velocity.

### 31 Refactoring With Structs ###

+ Assessing the existing code.
+ Creating a plain C++ struct.
+ Pulling out methods.

### 32 Client Interpolation Mesh Offset ##

+ Understanding mesh offseting.
+ Set up the mesh offset root component.
+ Manipulating the offset instead.

### 33 Advanced Cheat Protection ###

+ Bounding the inputs.
+ Stressing our DeltaTime.
+ Tracking simulation time.

### 99 End Of Course Wrap-up ##

+ Congratulations on making it this far!
+ Why we don't cover dedicated server.
+ How to continue practicing your skills
