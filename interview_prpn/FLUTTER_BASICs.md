Minimize widget builds
optimized build methods
manage heavy asynchronomous task
reduce heavy package and dependencies
Un-necessary heavy asstes removal , use cached widgets


OOP concept ✅

Object
Class
Inheritance
Polymorphism
Abstraction
Encapsulation

Coupling
Cohesion
Association
Aggregation
Composition


Solid principle https://www.linkedin.com/pulse/solid-principles-using-dart-marius-atasiei-jhsvf/


Single responsibility

Open/close principle

open for ongoing extension, but closed to edits and modification

Liskov subsitution
Interface segregation
Dependency inversion

Design patterns : Behavioural, creational , Structural : https://scottt2.github.io/design-patterns-in-dart/
Animation & Custom paints in flutter ✅
Testing in flutter ✅
Advance topic - Method channel and plugin and Isolates ✅
State management solutions ✅
Leet-code basics 🚧
Fundamental of List, Arrays, types  in dart [Queue, Stack, Array]✅
NoSQL and local database

## Animation
### Ticker class
Calls its callback once per animation frame.


A linear interpolation between a beginning and ending value.
Tween is useful if you want to interpolate across a range.

To use a Tween object with an animation, call the Tween object's animate method and pass it the Animation object that you want to modify.



Provides a single Ticker that is configured to only tick while the current tree is enabled, as defined by TickerMode.

Animation An animation with a value of type T. An animation consists of a value (of type T) together with a status.


### SingleTickerProviderStateMixin

Provides a single Ticker that is configured to only tick while the current tree is enabled, as defined by TickerMode.
To create the AnimationController in a State that only uses a single AnimationController, mix in this class, then pass vsync: this to the animation controller construct

