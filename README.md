# RimWorldReverseEngineeringMod
A RimWorld mod for reverse engineering technologies and techprints from items.

Planned functionality:
* Craft techprints from items/uninstalled buildings
  * Techprint produced should be for the research option needed to craft that item
  * If that techprint requirement is already fulfilled, recipe should result in research towards the tech
  * If the techprint produced could not be used to advance research, recipe should be disabled
  * Recipe requires capable of Intellectual
* Add use of acquired/crafted techprints to advance research
  * Advancement based on rounded integer of `(3000) * (value of item) / (value of techprof subpersona core)`
  * Above is multiplied by `1 + ((Intellectual - 5) * .05)`
  * Acquired techprint's value is set at highest cost item allowed by research or 1000 if none available
  * If prerequisite research is not complete:
    * Research bonus applied to most expensive researchable prerequisite
    * Research points applied are based on the research that allows crafting of the item
    * Disabled if lowest related research requires a techprint to unlock
  * Any overflow is lost

* Should be applicable to all research options and items added by other mods

Originally considered functionality that is currently out of scope:
* Similar effect for reverse engineering buildings
  * Warns on building deconstruction if pawn Intellectual < 5
  * More explicit warning if pawn is incapable of Intellectual
  * Unsure how to do value calculation on some buildings
* Add techprint requirement to existing research options based on tech level.
