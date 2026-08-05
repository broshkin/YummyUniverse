# Yummy Universe

An eat and grow arcade game in the spirit of Tasty Planet. You swallow everything smaller than you are, get bigger, and then swallow the things that used to be too big. Solo project, built in Unreal Engine 5.

**[Trailer](https://youtu.be/5Ti2gLjg3hk)**

> screenshot or gameplay gif goes here

## What is in it

**Mass is the only stat.** Everything the player eats adds to a single mass value, and that value decides what can be eaten next, how large the player renders, and how the camera pulls back. `WBP_PlayerMass` shows it, `EasyScale_MS` handles the scaling.

**Objects are sorted into weight categories.** `WeightCategory` groups everything edible into tiers, so the game can answer "can this be eaten yet" with a comparison instead of a per object check.

**Gravity spheres.** `BP_Gravity_Sphere` and a separate AI variant. This is where most of the interesting movement comes from, since the player is not walking on a flat plane.

**A spawner keeps the world populated** as the player scales up and clears an area.

## Built with

Unreal Engine 5. The gameplay is built in Blueprints rather than C++. GitHub reports the repository as C++ because of the engine boilerplate in `Source/`, but the actual work is in `Content/Blueprints/`.

## When this was made

Early 2026. Presented and defended twice as a university project, with a trailer cut for the
second review.

## What I would do differently today

It is a Blueprint project made by one person in a hurry, so there is not much architecture to
defend. The honest value here is different: it shows I can pick up a second engine and ship
something playable in it.

If I came back to it I would move the mass and weight category logic into C++ and leave Blueprints
for the things Blueprints are actually good at. Right now everything lives in the graph, and the
graph is hard to read.

For the Unity work, where there is real structure to look at, see
[FigureSpider](https://github.com/broshkin/FigureSpider).
