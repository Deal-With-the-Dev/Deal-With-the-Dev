---
layout: post
title:  "Layers of Abstraction in Rule's Text"
date:   2022-09-01
categories: rpg-theory
---

Some RPGs are a mess of wildly inconsistent mini-rules, others are a towering hierarchy of indirection. 

## One-Off Rules vs Abstraction

Older editions of Dungeons and Dragons had lots of "one-off" rules, specific rules text which only applies to a very particular situation. Look at *web* from HYPERBOREA 3rd edition

> If the webs are set ablaze with a torch or other fire source, they will catch quickly, the entire mass burning in 2 rounds. Those trapped within the conflagration suffer 1d6 hp damage per round (1d8 hp vs. undead), and any flammable clothing or gear is subject to burning and ruination

Notice how the spell does more damage against undead when burning, but if we compare this to *fireball* or *flame strike* theres no additional damage. Contrast this with Pathfinder 1e's paladin, who has bonuses against "evil outsiders"

> ...If the target of smite evil is an outsider with the evil subtype, an evil-aligned dragon, or an undead creature, the bonus to damage on the first successful attack increases

This means that if a paladin is doing battle with a succubus we have to understand a series of type-based inclusions similar to "object oriented programming" in order to understand the meaning of the rules. A `succubus` is a type of `demon`, and a `demon` is a type of `evil outsider` which also has the `evil` subtype, meaning that the paladin's bonus applies. 

All these layers of abstraction make for a more consistent and extensible system. If I come up with a homebrew creature I call the "hellspawn" and have a story about an order of paladins who do battle with them, all I have to do to make this fit in the existing system is say that hellspawn are a type of `evil outsiders`. 

On the other hand if we look at Hyperborea, magical fire sometimes does more damage to undead, but other times doesn't. Despite this inconsistency the rules are pretty much all there, *fireball* does what it says, and I don't need to understand a complex hierarchy of type inclusions to understand what a fireball is.

Because older editions tend to be less legalistic and literal there are a few ways to interpret this
- There is something about the nature of magic and the cosmos which makes burning *webs* and *flame swords* fundamentally different from the fires of *fireball* in relation to the undead, and I can reflect this in the lore
- The lack of specificity of *fireball* in regards to undead is an oversight, and as a GM I am free to increase the damage of *fireball* against undead as I see fit. The absence of the specific language does not convey absence of intent.
- The entire debate is a non-issue, as the rules of the game aren't meant to be taken as indications of world-building but rather as the rules of a particular tactical game 

## Keywords

When a rule comes up often enough, some games use "keywords" as a way to codify a particular type of rule. Hearthstone has [deathrattle][deathrattle], which are effects that trigger when a particular creature dies. Magic the Gathering on the other hand uses the language "when X dies...", such as with [Beskir Shieldmate][beskir].

> When Beskir Shieldmate dies, create a 1/1 white Human Warrior creature token.

The lack of keyword here means that it is (fairly) obvious what happens when Beskir Shieldmate dies (although dies itself is a keyword in MTG in a complex way...). However this makes effects which interact with this difficult to do. Hearthstone can make something like [Baron Rivendare][baron] fairly easily

> Your minions trigger their **Deathrattles** twice

But how would MTG make something similar, it would have to be a complex procedural mess like what [Teysa Karlov][teysa] says

> If a creature dying causes a triggered ability of a permanent you control to trigger, that ability triggers an additional time.

Even this isn't specific enough, because that would include cards which trigger when other cards die, you'd have to include some additional language about "if a creature dying causes one of its triggered abilities to trigger...". The moral is that keywords can be an easier way to 'hook' game mechanics into other game mechanics and create more consistency. 

But this comes at the cost of greater connection between disparate parts of the game, keywords make rules text less self-evident by virtue of being references to other rules.

## "Is-A" vs "Has-A"

In essence rule text has replicated the sort of relationships seen in Object-Oriented Programming. DnD 3.5 and Pathfinder have type inheritance, literally, as the basis for determining the abilities of monsters. Keywords are a way to "favor composition over inheritance" but still maintain a layer of abstraction with rules. MTG uses imperative language, saying what happens when, while other games have more declarative language - stating outcomes and ignoring control flow.

Looking at it from this perspective the same goals apply as they do to programming.
- How extensible are the rules? Is it easy to add new content? Does new content cause unexpected behavior?
- How clear are the rules? Is the text readable?
- How resilient are the rules to "bugs" or unexpected interpretations?


## Thoughts

Of course, all of this only matters if your goal is to create clear and consistent rules. RPGs are free to operate on a more loose or narrative plane if they wish. From my perspective I enjoy an RPG which
- uses rules text as a form of world-building
- has clear and consistent rules
- makes adding homebrew content straightforward 

It is much easier to choose which rules to ignore or what situations to be flexible on if the text itself is clear in the first place, and the rules of the game can form the "laws of physics" for your world; a great opportunity to convey aspects of the lore through play.

Based on this I think there are good times to introduce keywords
- many aspects of the game interact with this effect, such as "vulnerability to fire"
- you want to draw attention to this aspect of the world, a game with "deathrattle" aesthetically reinforces the themes that death and dying are important
- you see [many instances of the same text everywhere][dry]

And some bad times to introduce a keyword
- you don't want to gamify a particular portion of the book, such as when discussing campaign structure or in-game events
- you're already 2 or 3 keywords deep

## Other Examples

#### Lancer's Lack of "Blind"
Lancer has keywords for most all of the status effects which mechs can experience in game: stunned, impaired, prone...

But notably there is no keyword for "only have line of sight to adjacent spaces until the end of their next turn." Because taking the stabilize action can only clear conditions (things covered by keywords), theres no way to save yourself from what is essentially a "blinded" condition, because it lacks a keyword and therefore can't be interacted with via rules that entirely interact via keywords.


#### Pathfinder's Vital Strike
Pathfinder 1e has a funny situation with the [Vital Strike][vital-strike] feat. The feat essentially lets you hit harder with large weapons when you only take a single attack instead of multiple. A natural question arises, can I benefit from this if I charge an opponent? The rules say:

> No. Vital Strike can only be used as part of an attack action, which is a specific kind of standard action

But the creators mention they consistently house-rule it to allow Vital Strike on a charge. Here the keyword "when you use the **attack action**" appears to limit the feat beyond its design intent. Maybe a broader statement of "when you only make a single attack" would open that up, but in the deeply legalistic nature of Pathfinder 1e maybe that causes other problems...

[deathrattle]: https://hearthstone.fandom.com/wiki/Deathrattle
[beskir]: https://gatherer.wizards.com/Pages/Card/Details.aspx?multiverseid=503608
[baron]: https://hearthstone.fandom.com/wiki/Baron_Rivendare
[teysa]: https://gatherer.wizards.com/pages/Card/Details.aspx?multiverseid=458133
[vital-strike]: https://www.d20pfsrd.com/feats/combat-feats/vital-strike-combat/
[dry]: https://en.wikipedia.org/wiki/Don%27t_repeat_yourself