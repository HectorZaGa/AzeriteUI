# AzeriteUI Change Log
All notable changes to this project will be documented in this file. Be aware that the [Unreleased] features might not all be part of the next update, nor will all of them even be available in the latest development version. Instead they are provided to give the users somewhat of a preview of what's to come. 

The format is based on [Keep a Changelog](http://keepachangelog.com/) 
and this project adheres to [Semantic Versioning](http://semver.org/).

## [2.1.401-RC] 2020-09-04
- Bumping the minor addon version because of backwards incompatible file structure, not because of any sparkling new feature.
- Extra important to remember to exit the game client before updating now, as I'm in the process of re-arranging the file structure, squashing down some of the content, and moving all we can to a generic back-end which works for all our user interfaces, not just this one. I'm doing this in a manner that should make no difference to the regular user, but will cause some extra work for tinkerers that manually modify the files, as most of the editable ones in the front-end now have changed position. In the end the UI will be easier to edit, though, so hang in there!

### Changed
- Swapped the middle and right click actions on the cogwheel button. Middle button now opens the user interface menu, and right button opens the Blizzard micro menu and access to the standard game panels. The left click action to toggle your bags remain unchanged.

### Fixed
- Fixed an issue where the saved aspect ratio wasn't updated on logon or reloads, just on settings changes. 
- Fixed an issue where enabling the pet bar during combat would cause the explorer mode mouseover anchors to bug out.
- Fixed an issue where the pet bar would remain hidden on mouseover until fade settings change, if the bar was initially disabled upon login or reload and changed to enabled.

## [2.0.400-RC] 2020-08-30
### Added
- Hunters (Retail) now both have aura filter choices, as well as a few aura lists to make them viable (which was missing in the previous update). 
- You can now also disable on-screen raid warnings, boss and monster emotes, boss kill announcements, level up announcements and loot announcements from the HUD menu!

## Fixed
- Made the method used to hide various HUD widgets a bit safer, to avoid some logon bugs when switching character.

## [2.0.399-RC] 2020-08-30
- Continuing the work on 9.0.1 compatibility, though chances are there will still be endgame bugs on the PTR and in the beta. Please do NOT report them. They are per say not "real" bugs, I just haven't reached that point yet. I am not in the beta, and the PTR takes 5-10 minutes to log into, then I get randomly disconnected after 2-3 minutes. Working there is hard. And takes time. 
- First round of changes to move a lot more of the generic code into the back-end. The goal is to make the UI far more stylesheet-driven, making it easier for others to edit, and easier for me to transfer to other UIs. No ETA on this mad scientist change, nor any guarantees I'll actually take it all the way.

### Changed
- Windwalker Monks with the Ascension talent should now get all their 6 Chi visible at once.
- Did some more adjustments to the nameplate distance- and target scaling, as our previous changes were a bit too extreme.
- Chat bubbles should now be visible in instances when not engaged in combat, making it easier to understand what is going on before boss encounters or during the large amount of dialog in some scenarios.

## [2.0.398-RC] 2020-08-28
- First round of changes to make this WoW 9.0.1 compatible. Note that due to loading issues and client instability, I have been unable to test most max level features at this point, and have only been able to play a fresh character leveling in the new starting zone. The fixes reflect this. Also note that the majority of changes, bug fixes and updates related to this will NOT be listed here while 9.0.1 is still on the PTR and not live. 

### Changed
- Action button backdrops become visible and buttons faded in when holding a pet ability on the cursor in retail now.

### Fixed
- Added a raid frame sorting call after toggling the frames on from the menu. This should hopefully solve the bug of raid frames not appearing.

## [2.0.394-RC] 2020-08-20
### Changed
- The UIs master frame is now forcefully turned visible upon entering combat, and a previous system that hid it when zoning between instances has been disabled, as this was proving to be buggy.
- The slightly delayed UI fade-in after logging in or reloading has been disabled. This might too have misfired at some point. Taking the safe route today.

## [2.0.393-RC] 2020-08-14
### Changed
- The minimap blip icon for the city mission boards leading to the various BfA storyline chapters now have a similar exclamation mark to the others. 
- The new rare/elite/boss icon on the nameplates now ignores the nameplate alpha. They look weird when faded, and we want to know the classification at all times. This is really needed when deciding what plate to click for the rare mob that's about to die in half a second. 
- The buff and debuff unitframe plugins - which this UI actually doesn't use - now obeys the same filter rules as the aura element does. This is just a bonus inherited from the GoldpawUI7 development. 
- The Irontide Recruit buff is now whitelisted regardless of aura filter level. This is a buff we need to toggle during the Tiragarde Sound storyline.

### Fixed
- Fixed another issue related to the objective tracker's random loading order. Hopefully we're done with these bugs for a while now. 
- Fixed nameplate castbar spell name alignment, as this would only be fully correct directly after changing between a protected and regular cast. Now it updates on every cast.

## [2.0.390-RC] 2020-08-13
### Fixed
- Fixed a back-end issue that would break the UI for some users, as it wrongly assumed the Blizzard_ObjectiveTracker always would be loaded prior to itself. Which it isn't. Though it strangely enough always is for me. 

## [2.0.389-RC] 2020-08-12
### Fixed
- Fixed a back-end issue introduced in the previous update that could cause a bug when name info was unavailable on a unit frame.

## [2.0.388-RC] 2020-08-12
### Changed
- Updated the UI switcher chat commands for compatibility with new upcoming UIs. More on this later!

### Fixed
- Modified Minimap back-end to not require our objectives tracker module anymore. Also detached Minimap alpha from the rest of the UI. We don't want to fade this frame in and out, the actual map section and its blips and pins is incompatible with this. It is now possible for tinkerers to disable the objectives tracker and minimap modules form the ToC file separately.
- We previously scaled up the Minimap blip icons about 15%, as it simply looked better. This has proven to be incompatible with addons adding their own pins to the Minimap, like GatherMate, HandyNotes or Questie, so we are removing it and going back to tiny icons. 
- We are now re-applying the game's saved setting for Minimap rotation after logging in, in an attempt to forcefully update the rotation setting in addons adding their own pins to the Minimap, as this sometimes simply did not happen after reloads, and icons would act as if no rotation was enabled, even though it was. Experimental solution, still keeping an eye on this.

## [2.0.387-RC] 2020-08-09
### Changed
- Styled a few more Minimap blip icons for better consistency.

### Fixed
- Fixed an issue that sometimes would produce a bug if a new nameplate was created in the middle of combat.
- Fixed an unalignment issue with nameplate castbar spellnames.

## [2.0.386-RC] 2020-08-09
### Fixed
- Our raid frames appear instantly once again, and not just when changing between 26 or more and 25 or less group members. The bugs get ever more interesting.

## [2.0.385-RC] 2020-08-08
### Added
- Trying to see if our pretty Nazjatar rune/line minigame interface works without imploding the game client this time.

### Changed
- No more Blizzard raid frames. We tried having it compatible for a while, it didn't work out. Use our frames, or another 3rd party raid frame addon like Grid.
- Re-adjusting most nameplate element anchors to use nameplate corners instead of the nameplate center as their reference points, as the center regions for some reason are super buggy in the game and somehow tends to make the elements drift. Parts of the nameplate are rendered by the game engine, and not the UI. And when the game devs venture into UI territory, it usually turns out comparibly to a dog standing on two legs thinking itself human. This change may or may not solve the problem.

### Fixed
- Fixed a mixup that would cause aura buttons set for mouse input to not get any, and those set to ignore mouse to get mouse input. It should once more be possible to cancel auras out of combat now. 

## [2.0.384-RC] 2020-08-07
### Fixed
- Fixed a wrong upvalue that would cause the Personal Resource Display (your own nameplate) to break.

## [2.0.383-RC] 2020-08-07
### Added
- Added Demon Hunter Soul Fragments tracking to our class resource system.

### Fixed
- Fixed a bug where the experience percent value on the minimap badge sometimes would show the percentage sign, cluttering up everything.
- Fixed a bug that made nameplates unclickable. 

## [2.0.382-RC] 2020-08-07
### Added
- Nameplates now show unit names when targeted or mouseovered, or if it's owner is attackable and you're currently engaged in combat.
- Nameplates belonging to attackable units now show health values when targeted or mouseovered.
- Nameplates belonging to attackable units now show a classification badge for rares, elites and bosses, in the same manner the target unit frame currently does.
- There should now once more be a threat glow around nameplate healthbars.

### Changed
- Classic target nameplate is now locked to the screen, thanks to the new CVar `clampTargetNameplateToScreen` introduced into the game July 14th 2020. 
- Most threat glows and threat coloring should even in Classic be visible when solo or outside of instances now. The setting might be affected by other addons using LibThreatClassic2 turning it off.

### Fixed
- Changed how the default Blizzard pet unit frame is hidden, as this was affecting the retail totem bar, causing it to not appear at times.

## [2.0.380-RC] 2020-08-03
### Added
- Trying out a new tooltip texture. Work in progress!
- The retail totem frame should be available now!

### Changed
- Split the chat filter setting into multiple options for styling and filtering.
- Adjusted how action button stack/charge count is detected. Should see a few missing things now.

## [2.0.379-RC] 2020-08-02
### Changed
- (Classic) TOC bump to WoW Classic Client Patch 1.13.5.
- (Classic) Updated Minimap blips to patch 1.13.15.
- (Retail) Updated Minimap blips to patch 8.3.7.

## [2.0.378-Alpha] 2020-08-01
### Added
- Protected casts should now have a shielded nameplate castbar.

### Changed
- Actionbuttons above the 7 default ones now fill towards the right in an up and down zig zag manner, instead of by rows as previously. This will probably mess up the bars for a lot of people. I'm fine with that, as it's a better choice to keep the bars this way, letting them grow as a solid unit from left to right.
- Actionbuttons will now show empty slots only for single empty slots which has a filled button to both its sides, while other empty slots will be hidden.
- You should see less "Failed" messages for spells that are interrupted within the spell queue window and actually completed despite the interruption.
- Healthbars are now colored according to threat where applicable. This update only applies to Retail, Classic will be done next week as it requires a little more work to avoid any additional performance cost during large group combat.

## [2.0.377-Alpha] 2020-07-30
### Fixed
- Fixed the wrong upvalue in today's previous update. You should no longer get a bug everytime something goes on full cooldown.

## [2.0.376-Alpha] 2020-07-30
### Fixed
- Retail spell charge cooldowns are now in place!

## [2.0.375-Alpha] 2020-07-23
### Fixed
- Monks should finally get their mana orb back in retail. 
- Neutral Pandaren no longer has to wait until they've chosen a faction to be able to use the micromenu without causing a bug. 

## [2.0.374-Alpha] 2020-07-14
### Fixed
- Bufftimers in certain retail quests and world quests (like "Show-Off" where you mount Cooper and score style points) should no longer bug out!

## [2.0.373-Alpha] 2020-07-07
### Changed
- Restricting certain checks and updates done by unitframes and nameplates in an effort to increase the performance in large groups a bit.

### Fixed
- Working around some issues related to checking for threat in retail.

## [2.0.372-Alpha] 2020-07-02
### Changed
- Lowered the objectives tracker strata, to prevent it from covering the Immersion buttons.

### Fixed
- Attempting a different set of visibility conditionals to avoid the pet action bar popping up as a copy of the main bar in certain Retail world quests like Beachhead.
- Fixed the Retail issue where logging in after having logged out while inside an instance would lead to weird errors.

## [2.0.371-Alpha] 2020-07-02
### Fixed
#### Retail
- Fixed an issue that would cause our keybind interface to bug out when you attempted to save the new bindings.

## [2.0.370-Alpha] 2020-07-02
### Fixed
- Tried to fix some inconsistencies in when the "Failed" message appears on the castbars.
- Fixed an issue related to multiple unregistrations of custom messages, that amongst other things affected the chat module and caused problems when using Prat. 

## [2.0.369-Alpha] 2020-07-01
### Fixed
- The fader system should no longer randomly throw errors upon logging in while inside an instance.

#### Retail
- You should no longer be spammed with messages upon entering or leaving a grouped instance.

## [2.0.368-Alpha] 2020-07-01
### Changed
#### Retail
- The Personal Resource Display now has a power bar. 
- The Personal Resource Display's castbar now shows the currently set spell queue window. Remember you can always change this with `/run SetCVar("spellQueueWindow", 55)`, where you replace the number `55` with your desired queue window in milliseconds. For a fluent gameplay for melee I recommend adding 5 to your world latency, and rounding up to the nearest 5 after that. Meaning if your latency is 28ms, you should put the spell queue window to 35ms. If you're a caster that thrive on spell batching to the point of madness, putting it to something outlandishly high like 400ms would probably work well. 
- The Personal Resource Display now grows towards the right, like the player unitframe. This is to match the said player unitframe, and also to make sure this special nameplate stands out from all the others. 
- The floating on-screen castbar is now disabled when the Personal Resource Display is enabled, since they occupy the same area on the screen.

### Removed
#### Retail
- The Blizzard interface options menu entry to show target of target has been removed, as it does not apply to our unitframes.
- The Blizzard interface options menu entry to show combo points and personal resources on the target plate has been removed, as we're already using a very centered system for secondary resources like combo points, runes, holy power and so on.

## [2.0.367-Alpha] 2020-06-29
### Fixed
- Chat filters should no longer bug out when you receive the awesome amount of 0 gold, 0 silver and 0 copper.

## [2.0.363-Alpha] 2020-06-29
### Fixed
- Chat filters should no longer bug out for non-English game clients. Tested with at least deDe.

## [2.0.362-Alpha] 2020-06-28
This update contains WoW Retail compatibility. A major part of this update is in that added compatibility, and a lot of features that previously only were a part of the Classic version will now also be a part of the Retail version. The project version has because of this been bumped to indicate the amount of added, changed and updated features, as well as the number of builds we've passed since the last public update. This changelog is meant to be read by humans, by the users, and thus will not include most of the numerous back-end changes.

### Added
- Added aspect ratio features, which allows you use the full width of the monitor or limit it to either a 21:9 ratio, or have it remain at the now default 16:9 setting, as the UI originally was designed for.
- Added a new optional default feature to have the chat window move to the bottom of the screen when player explorer mode is enabled, and the player area is faded out. This does not affect the chat window when healer mode is enabled, nor when you have a target, are engaged in combat, or any of the other elements that would cause the player area to fade back in. Furthermore, when hovering over either the player area or the chat window, the chat will return to its original position, and remain there until a few seconds after you move the mouse cursor away.
- Added a new optional default feature to clean up the multitude of chat messages sent by the game client, like when you gain loot, gold, experience, reputation, skill levels and so on. This filter does not add any messages, it only affects or throttle message types you already have chosen in your blizzard chat window settings to display in the first place. The idea is to allow you to have the kinds of messages you normally would put in separate windows in your primary one instead, without it feeling cluttered or messy. 
- Added a resting indicator to the zone name located next to the minimap.

#### Classic
- Added strict aura filter lists for Druids, Mages and Warriors, as well as menu options to choose the filter level. The other classes are getting it too, just haven't gotten there yet!
- Added threat glow to the player- and target unitframes.
- Added better Questie compatibility in unit tooltips.

#### Retail
- Added strict aura filter lists for Druids, Mages and Warriors, as well as menu options to choose the filter level. The other classes are getting it too, just haven't gotten there yet!
- Added extensive aura filter whitelists for all current BfA instances and raids.
- Added pet bar and visibility options for it. 
- Added minimap blips for WoW client patch 8.3.0.
- Added the option disable the floating castbar, and the player class power elements.
- Added a new feature that hides the rest of the interface when the Nazjatar minigame world quests are in progress, as well as put a large exit button in the upper right corner of the screen during those minigames. The minigames currently affected are the non-vehicle ones, meaning the Bejeweled ripoff and the line untangling. This feature is not available when you are part of a raidgroup, but then again, the world quest can't be completed then anyway, so that should be a non-problem.

### Changed
- Any type of eating or drinking while explorer mode is enable should force the interface to fade back in now. We previously used auraID to identify eating and drinking, but seeing as blizzard just keeps adding more and more versions of the same action, with the same name, it made sense to just identify this by name instead.
- Changed the default fallback aura filters for all unit frames and nameplates. Also note that classes that haven't gotten their strict filters finished yet, will automatically fall back to the most inclusive version of the aura filters, to ensure important auras are visible.

#### Retail
- Death Knight runes are never fully hidden anymore. This will only be the case for runes, not other types of class resources.

### Fixed
- Changed the search patterns deciding the spell cost in our actionbar tooltips. Any type of resource cost should now be detected and displayed. This was previously an issue hiding multiple spell costs from several classes and vehicles.
- Changed how difficulty coloring is decided for both Classic and Retail.

#### Retail
- The blizzard minimap widgets like PvP capture bars and the Azshara fight's Ancient Wards should now be visible above our minimap.

## [1.0.115-RC] 2020-04-01
### Fixed
- Solved an issue where pet bar actions that required a right-click weren't usable through their keybinds, only through the aforementioned right-click.

## [1.0.114-RC] 2020-03-30
### Added
- Added a battleground chat filter that removes all messages about players joining or leaving, in an effort to make the chat more readable.

### Changed
- Changed the default number of actionbuttons to 7, as the user interface was intended to have in the first place. Options to add more will always remain.

## [1.0.113-RC] 2020-03-15
### Added
- Added chat outlines. This is enabled by default, but can be toggled through the menu.
- Added highly experimental temporary enchants. Placement and design should only be considered placeholders. Shaman weapon buffs should be possible to remove in combat by right-clicking, but this is currently untested.

### Changed
- Optimized the spell activation highlight code a bit. Changed how timers are disabled.

### Fixed
- Fixed an issue that would cause a bug on logon and reloads when only the main 7 actionbuttons was enabled.
- Fixed issues related to reactive spell highlighting, where spells sometimes wouldn't trigger properly, or not go away once triggered.

## [1.0.107-RC] 2020-03-11
### Changed
- Updated minimap blips to work with patch 1.13.4.

## [1.0.106-RC] 2020-03-11
- Updated for WoW Classic Client Patch 1.13.4.

### Added
- Added spell activation highlights for Hunter Counterattack and Mongoose Bite.
- Added spell activation highlight for Paladin Hammer of Wrath.
- Added spell activation highlight for Rogue Riposte.
- Added spell activation highlights for Warrior Execute, Overpower and Revenge.

### Fixed
- Fixed a problem where the group debuff display wouldn't properly update on unit GUID changes. Fixed it in the plugin, but plan to write this into the aura back-end to make sure all modules and plugins using it automatically gets updated.

## [1.0.105-RC] 2020-03-05
### Changed
- Further adjusted the spell highlight coloring a bit. This is a work in progress, as I want the three highlight types to have easily identifiable coloring, stand out when active, and still fit the general coloring of the user interface.

### Fixed
- Finishing move spell highlights for rogues and druids should have consistent coloring now, and not suddenly switch to the reactive coloring.

## [1.0.104-RC] 2020-03-03
### Added
- Added Rogue and Druid finishing moves spell highlighting when combo points are maxed out.

## [1.0.103-RC] 2020-03-01
### Fixed
- Fixed an issue with the dispellable group frame debuff display that could cause an error when leveling up.
- Fixed an issue that could cause exact mob health values to not be displayed. This was related to API changes in the classic client that since February 18th 2020 now reveals exact mob health to the player, where we previously used RealMobHealth interaction to show this.
- Redid how it is decided whether a full health value is available or not.
- Made the clearcast highlight color brighter, as it wasn't standing enough out from its surroundings.
- Attempting to work around an issue that would cause a bug and require a `/reload` upon reaching level 60. A little hard to reproduce, though.

## [1.0.101-RC] 2020-02-29
### Changed
- Actionbutton spell highlight alerts have been moved to a new back-end of its own. 
- Actionbutton spell highlights have gotten new coloring. Clearcasts are now blue, reactive abilities bright yellow, finishing moves range.
- Added Shadow Bolt highlighting when Warlock Shadow Trance is active.

### Fixed
- Fixed an issue in the mana orb plugin that would sometimes cause it to be forcefully reshown even though the element had been disabled.
- Fixed an issue where a custom styling method would overwrite the minimap module's ring bar text display, and people hitting new experience- or reputation levels would still be seeing the "New" text.

## [1.0.99-RC] 2020-02-28
### Added
- Mana users now now have the option to use the azerite crystal for all power types, instead of the mana orb.
- There are now mana bars visible for mana users on the group frames. Note that for non-healer units the bars will only become visible when the unit is running really low on mana.
- Chat spam on logon or manual reloads is now suppressed. This is a forced setting. The Guild Message of the Day will be shown after roughly 10-12 seconds after logging in or reloading the interface. Messages after zoning in or out of instances and other portals are not affected.

### Changed
- Most non-targeted nameplates should be more visible both in and out of combat now, making tanking and healing easier.
- The dispellable debuff display on group frames now checks if the character has high enough level to actually do the dispel.
- Debuffs on unit frames belonging to hostile units are now all colored red, as displaying the debuff type using color should only be used for dispelling purposes.
- Debuffs on hostile units not cast by the player is now desaturated.
- Buffs on friendly units not cast by the player is now desaturated.
- Auras are now sorted. 
- Auras on the target frame when you target a boss now take advantage of the larger width of the frame. 
- The chat frame buttons should now always be visible if the frame isn't currently scrolled to the bottom of its content.
- When just having reached a new level, or reputation level if that is what you're current tracking, the minimap badge text should now be an asterisk `*`, and not the word "New". The latter was never intended, as we used a graphical exclamation mark in the retail version of this addon, but Blizzard changed that to the text "New" to better reflect how their quest dialogs looked in vanilla.

### Fixed
- When a group frame's unit changes while mouseovered, its tooltip should now properly update to show the new unit.
- When the target frame's unit changes during a cast or channel and the new unit isn't currently casting or channeling anything, its castbar should now properly be cleared.

## [1.0.98-RC] 2020-02-14
### Added
- The pet bar now has similar fading options as the additional action buttons. So in addition to fully being able to toggle the pet bar, you can now choose its visibility between always, in combat and mouseover, or only on mouseover.

## [1.0.97-RC] 2020-02-14
### Changed
- Player and target unit frames should now display two rows of auras, up from one.

## [1.0.96-RC] 2020-02-12
### Added
- Added cooldowns to the pet bar.

### Changed
- Updated love festival dates for 2020.

### Fixed
- May or may not have fixed an issue with additional action buttons not fading properly.

## [1.0.95-RC] 2020-02-06
### Added
- The pet buttons have been added to the `/bind` mode.

### Changed
- Actionbutton backdrops no longer become visible when you're holding a pet ability on the cursor. This was a remnant from retail where it's possible to put pet abilities on normal actionbars, something we cannot do in Classic.

### Fixed
- You should now be able to toggle autocasting of pet abilities by right-clicking the ability on the pet bar, or using your keybind.
- The Blizzard reputation watch bar should no longer invisibly interfere with your ability to click the bottom part of the action bars when you are tracking a reputation.

## [1.0.94-RC] 2020-02-03
### Added
- Added the first draft of the pet bar. Finally you can order your pet around, do something else than just stand there while mindcontrolling opposing players, and even finish killing Emberstrife for your UBRS attunement quest without having to disable the addon mid fight. 

### Changed
- Primary chat window buttons will now become visible when hovering over the window.
- Empty backdrops of actionbuttons will now be visible if there are visible buttons with content farther down along the bars. This is to prevent "holes" in the layout.

### Fixed
- PvP rank names in unit tooltips should no longer show your own faction's rank names on players from the opposite faction.

## [1.0.93-RC] 2020-01-29
### Changed
- 5 player party frames will no longer be used when player is in a raid group, even if that raid group has less than 5 total members. Party frames by default only show the raid subgroup you're in, leaving people placed in other groups invisible. This behavior was unintended, so we're sticking to party frames with portraits for parties, and smaller raid frames for any and all raid groups. 

### Fixed
- Finally fixed the small frame flickering after interrupted casts. This was an issue related to the frequent updates of frames lacking distinct unit events, like the ToT frame.

## [1.0.92-RC] 2020-01-29
### Fixed
- Party aura tooltips show now grow towards the right, instead of towards the left and straight out of the screen. Now you can read them.

## [1.0.91-RC] 2020-01-28
### Added
- First draft of aura durations added. Better filtering and display coming this week! Yay!

## [1.0.90-RC] 2020-01-11
### Added
- Spells that require reagents should now show their remaining reagent count when placed on the action bars.

### Fixed
- Trying to work around some language issues that would cause placing items on the actionbar to sometimes bug out when hovering over them. The issue was related to different formatting of some game strings in English and non-English clients.

## [1.0.89-RC] 2020-01-09
### Changed
- Added a forced update of all ToT unitframe elements on player target change, as this previously had up to half a second delay on player target changes when the ToT frame remained visible throughout the change.

## [1.0.88-RC] 2020-01-07
### Added
- Added subgroup numbers to the bottom left part of the raid frames. No more headache trying to figure out who's in what group, or where the Alliance AV leecher you want to report is!

### Fixed
- Fixed an issue with some raid frame elements like leader/assistant status as well as raid marks which sometimes only would update on a GUID change.

## [1.0.87-RC] 2020-01-05
### Fixed
- Fixed a typo in the frFR translation that caused reputation tracking on frFR game clients to bug out.

## [1.0.86-RC] 2019-12-31
### Added
- Added the very first experimental draft of our spell highlight system. Druids with Omen of Clarity will now find that Shred, Ravage, Maul and Regrowth are marked when their clearcast proc fires. This is a work in progress, and I'll expand the list for more classes, as well as write other methods into this system to light up reactive abilities like Warrior's Overpower and similar.
- Started on the nameplate aura blacklist. Certain spam like Mark of the Wild, Leader of the Pack and various other auras will no longer show up on party member nameplates. This too is a list in growth.

## [1.0.85-RC] 2019-12-18
### Changed
- Expanded the group frame hitboxes to cover the bottom part of the health border as well. Super easy to select targets now.
- Further tuned the outline and shadow of both the raid warnings and error messages.
- Dispellable and boss debuffs visible on the group frames should should now always be fully opaque, even if the group frame itself is faded down from being out of range.

### Fixed
- Fixed an issue that prevented raid marks, leader- and assistant crowns as well as main tank and main assist icons from showing up on the raid frames.

## [1.0.84-RC] 2019-12-17
### Changed
- Prettied up the raid warnings a bit more.
- Slightly trimmed the popups.
- Went for a more elegant fix for the bg popups, where instead of changing their text hide them completely. Now a flashing red message - in addition to the usual bg ready sound - will tell you how to enter the available battleground. This change is Tukz-inspired.

### Fixed
- Fixed the health value of group member pet tooltips, where their actual health value would be presented with a percentage sign behind. That was a visual bug, the value was their actual health all along.

## [1.0.83-RC] 2019-12-16
### Changed
- Boss/dispellable debuff slot on group frames should no longer react to mouseover events. There won't be a tooltip anymore, but it won't be in the way of clicking on the unitframe to select it as your target anymore.
- RaidWarnings shouldn't look as freaky and warped anymore, as we have disabled certain very faulty scaling features the default user interface applies to these messages. We also changed the font slightly to make it more readably on action filled backgrounds in raid situations.

## [1.0.82-RC] 2019-12-15
### Changed
- Fixing a wrong date in some secret code. No biggie, it'll fire tomorrow for those lacking this update. But I want pretty colors!

## [1.0.81-RC] 2019-12-14
### Changed
- The minimap tracking button now changes position based on whether the BG eye is visible or not.

## [1.0.80-RC] 2019-12-12
### Changed
- Removed the ability to enter BGs through the bugged popup. Now we'll have to learn to use the eye, or simply not get anywhere. I changed the text in the popup to reflect this new behavior. This is a temporary fix until I can figure out how to get a working BG entry popup again.

## [1.0.79-RC] 2019-12-11
### Fixed
- Both the Minimap button and BG entry popup should work... better, now. 

### Removed
- Removed the popup styling. It's problematic right now.

## [1.0.78-RC] 2019-12-11
### Fixed
- Fixed spam filter issues. Clearly chat events have changed since I was a young noob. Luckily this older noob figured it out.

## [1.0.77-RC] 2019-12-11
### Changed
- Only apply our spam removal to system messages. That should be the correct message group.

## [1.0.76-RC] 2019-12-11
### Added
- Added the Minimap Battlefield button. We're using our green groupfinder eye from the retail version of this addon.
- Added a minor chat filter to remove the "You're not in a raid group" spam that keeps happening within Battlegrounds. Cause can be other addons, but for now we're just filtering it out.

### Changed
- Slightly re-aligned the Minimap tracking button to make a little room for the new Battlefield button.
- Added back the Minimap blip textures, as they appear to be more or less unchanged from the previous patch.

### Fixed
- The Blizzard static popups will no longer be repositioned by us to accomodate our styling of them, as this was causing taint with the new Battleground popups, making the enter button unclickable. This change might cause some graphical overlap in situations with two popups visible at once, though this should be purely visual and not affect the ability to click the buttons. We'll come up with better styling soon. 

## [1.0.75-RC] 2019-12-11
### Added
- Added the keyring button to the backpack.
- Added in some groundwork for a couple of upcoming features.

### Changed
- Updated the TOC version to WoW Client Patch 1.13.3.
- Adjusted statusbar code to avoid a very subtle wobbling that nobody but me seem to have noticed.

## [1.0.74-RC] 2019-12-04
### Fixed
- The chat window position should once again instantly update without needing to reload when the Healer Layout is toggled in the menu.

## [1.0.73-RC] 2019-11-29
### Added
- Added back Blizzard's `/stopwatch` command. The stopwatch exists in Classic, so why not?

### Changed
- Left-Clicking the clock now toggles the stopwatch.
- Casts should no longer appear to continue after the unit has died.

## [1.0.72-RC] 2019-11-20
### Added
- Added in group tools with raid icon assignment, ready check and raid/party conversion buttons.
- Added player PvP titles to unit tooltips.

## [1.0.71-RC] 2019-11-20
### Fixed
- The blizzard durability frame should once again be hidden, preventing double up when our own is shown. 

## [1.0.70-RC] 2019-11-16
### Added
- Tooltips should now display when units are civilians. Gotta stay clear of those Dishonorable Kills! 

### Changed
- Adjusted nameplate raid icon position to stop it from colliding with the auras. 
- Tooltip health values now show a percentage sign when only percentage and not the real health value is available.

## [1.0.69-RC] 2019-11-08
### Changed
- The HUD castbar is now anchored to the bottom rather than the center of the screen. It has also been moved farther down, to not be as much in the way.
- Removed the target level badge for most units. 
- Added the target's level to its name text, like in the tooltips.
- Added the small target power crystal for all units that have power. 
- Changed the small target power crystal to be slightly larger, and slightly more toned down. 

## [1.0.68-RC] 2019-11-07

_**DISCLAIMER:**_  
_Loss of limbs, life or sanity is not the responsibility of the author._

### Changed
- There is now a new HUD entry in our options menu, where you can choose to disable the combo point display and the on-screen castbar. 
- Added a highly experimental feature to work around the Blizzard issue where macro buttons sometimes are missing their info and icon until the macro frame is opened or the interface reloaded. This fix might cause the whole universe to implode, and you're thus installing this at your own risk. 

## [1.0.67-RC] 2019-11-02
### Fixed
- Targeted high level hostile players should no longer get a wooden unit frame border, but instead the same spiked stone frame as max level units.
- Skinnable dead units should once more show that they can be skinned in the tooltips. This applies to both units that can be skinned for leather, as well as herbs or ore. 

## [1.0.66-RC] 2019-10-29
### Changed
- Started major reformatting of stylesheet and unitframe styling code structure. First step in changes that eventually will affect the whole addon. 
- Every time you reach a new reputation standing or experience level and your current value in these are below one percent, the minimap badge tracking these will now show an exclamation mark instead of the non-localized "xp" or "rp" texts they used to show. 
- Tooltips should now show dead players in spirit form as simply "Dead", not "Corpse". 
- Tooltips now indicates the rare- or elite status of NPCs much better. 

### Fixed
- Health numbers and percentages should no longer be visible on critters with the tiny critter unitframe, even if they're above level one. 
- Changed the way the blizzard gametooltip fonts are set to work around some alignment issues that arose in a recent version.
- Fixed an issue where the vendor sell price in some cases (e.g. AtlasLoot) would be displayed twice in the same tooltip.

## [1.0.65-RC] 2019-10-28
### Changed
- Renamed the whole library system for classic, since some adventurous tinkerers kept mixing files from retail into the classic files, leading to a series of unpredictable issues. 
- Tooltips should indicate a lot better when a unit is dead now. 

## [1.0.64-RC] 2019-10-27
### Changed
- Disable tooltip vendor sell prices when Auctionator or TradeSkillMaster is loaded. More addons will be added to this list. 

### Fixed
- Fixed a tooltip issue where the wrong object type was assumed. 

## [1.0.63-RC] 2019-10-25
### Fixed
- Item tooltips now show the correct vendor sell price for partially full item stacks. 

## [1.0.62-RC] 2019-10-25
### Added
- Added vendor sell prices to items when not at a vendor. 

### Changed
- Mouseover unit tooltips should now be much more similar to our unitframe tooltips.
- Mouseover tooltips shouldn't have a different scale before and after hovering over a unit anymore. 

### Fixed
- Fixed some tooltip parsing issues that would use the spell description as the spell cost in some cases where spells had a cost but not a range. 

## [1.0.61-RC] 2019-10-22
### Fixed
- Fixed an issue with wrongly named custom events which caused interrupted spellcasts to appear to still be casting. 

## [1.0.60-RC] 2019-10-17
### Fixed
- Fixed wrong field name causing a nil bug when channeled player spells were pushed back. 

## [1.0.59-RC] 2019-10-16
### Added
- Added in raid frames. Frames can be toggled through the menu, just like the party frames. 
- Added the first draft of castbars to other units than the player. 

## [1.0.58-RC] 2019-10-13
- Files have been added, remember to restart the game client! 

### Changed
- Added some slight filtering to party frame auras to make it easier for healers to heal. 

### Fixed
- Group frames should now spawn in the correct place after a reload when healer layout was enabled previously. 

## [1.0.57-RC] 2019-10-09
### Added
- Now compatible with RealMobHealth. 

## [1.0.56-RC] 2019-10-08
### Changed
- Now compatible with Plater Nameplates. 

## [1.0.55-RC] 2019-10-08
### Added
- Added in party frames. Might have undiscovered bugs. Frames can be toggled through our menu. 
- Added the Healer Layout (previously known as Healer Mode) back in, now that we have party frames. This layout switches the positions of the group frames and chat frames, resulting in all friendly unit frames being grouped in the bottom left corner of the screen above the actionbars, making it easier for healers. 

## [1.0.54-RC] 2019-10-08
- ToC updates. 

## [1.0.53-RC] 2019-10-07
### Changed
- Removed the immovable object also known as the Blizzard durability frame, and replaced it with our own that looks exactly the same but has the benefit of actually working without stupid bug messages about mafia anchor connections. Fuck you secure anchoring system.  

## [1.0.52-RC] 2019-09-27
### Added
- Added reputation tracking to the minimap ring bars! 
- Aura tooltips now show the magic school of the aura.

### Changed
- Aura tooltips no longer show the spellID. You don't need to see that. 
- Various aura filter tweaks, and the beginning of the Druid aura overhaul in preparation of that. All classes will eventually be covered, and I'm starting with Druid since that is my main and something I currently have direct access to. 

## [1.0.51-RC] 2019-09-25
### Added
- Added a right-click menu to the minimap to select tracking when available.
- Added a tracking button to the minimap. When left-clicked, it displays a menu of the available tracking types, when right-clicked, it disables the current tracking. 

## [1.0.50-RC] 2019-09-23
### Fixed
- Slight bug in yesterday's update that caused all auras to sometimes be hidden in combat. Working as intended with this fix. This too is temporary, as I'm currently in the process of overhauling the aura system with parsed combat log information to make it far more functional for Classic. 

## [1.0.49-RC] 2019-09-22
### Changed
- Slightly adjusted the player aura filter to be more responsive to combat changes, and to only show long duration buffs in combat when they have 30 seconds or less time remaining before running out. Debuffs are displayed as before. This is not "the final filter", it's just a minor tweak to improve the current for as long as that may remain. 

## [1.0.48-RC] 2019-09-21
### Changed
- Healer Mode currently disabled, as it made no sense to switch just the chat around without the group frames. We'll re-introduce this option later once the group frames are in place. 
- Slightly increased the size of the actionbutton hit rectangles, to make the tooltips feel a bit more responsive when hovering over the buttons. 

## [1.0.47-RC] 2019-09-18
### Changed
- If Leatrix Maps or Enhanced World Map for WoW Classic is loaded, this addon won't interfere with the World Map anymore.

## [1.0.46-RC] 2019-09-17
### Removed
- Removed our anti-spam chat throttle filter that was working fine in BfA, as it's fully borked in Classic and probably the cause of all the missing chat messages in new chat windows that people have been experiencing. 

## [1.0.45-RC] 2019-09-16
### Changed
- Switch the middle- and left mouse button actions on our config button, and made the tooltip a bit more directly descriptive. 

### Fixed
- Fixed a potential nil bug in the quest tracker. I was unable to reproduce this, but put in a safeguard. 

## [1.0.44-RC] 2019-09-11
### Changed
- I made something just about twenty percent brighter then they needed to be. Now hush! 

## [1.0.43-RC] 2019-09-10
### Changed
- Disabling aura filters for now, until we can get a proper combat event tracking system in place, and maybe some durations for class abilities too.

## [1.0.42-RC] 2019-09-09
### Changed
- Move the chat window slightly farther down the screen. 
- Removed an unannounced experimental feature that I felt belonged in an addon of its own. 
- Redid the scaling system to just be simpler. 

## [1.0.41-RC] 2019-09-08
### Fixed
- Fixed the wrong function call introduced in the previous build. 

## [1.0.40-RC] 2019-09-08
### Changed
- All target unit frames (except the tiny critter/novise frame) now shows the unit health percentage on the left side, and will only show the actual health value on the right side when it's currently available. For now that limits it to you, your pet, and your group. 

### Fixed
- Fixed a forgotten upvalue in the target unit frame aura filter which prevented most auras from being shown in combat.
- Players will now see their health at level 1, they don't have to wait until level 2 anymore. Weird bug. 

## [1.0.39-RC] 2019-09-05
### Changed
- Changed some inconsistencies in the selection- and highlight coloring of the quest log. 

## [1.0.38-RC] 2019-09-05
### Added
- Added quest levels to the quest log.
- Added a minor blacklist to the red error messages, mainly filtering out redundant information that was visually available elsewhere in the interface, or just became highly intrusive and spammy. Because we know there's not enough Energy to do that. We know. 

### Changed
- Using better quest difficulty coloring in the quest log, and not the slightly too easy looking default one. 
- Improved the Explorer Mode logic for mana for druids, as well as prevented the fading while drinking. 

## [1.0.37-RC] 2019-09-04
### Added
- Added the command `/clear` to clear the main chat window. Because why not. 

### Changed
- Most abilities should now have their resource cost displayed in the actionbar tooltips. 
- The text on the power crystal showing druid mana in forms should now be colored red when very little mana is left. 

## [1.0.36-RC] 2019-09-01
### Added
- Added a "secret" feature to automate group invites and declines a bit. The commands `/blockinvites` and `/allowinvites` have been added, where the latter is the normal all manual mode, and the former is an automated mode where invites from wow friends, bnet friends and guild are automatically accepted, and everything else automatically declined. No options for this behavior exists as of yet, except the ability to turn it on. It is disabled by default, but there for those that me that are dead tired of brainless muppets spamming invites without ever uttering a single word. 

### Changed
- Toned down the opacity and reduced the number of messages visible at once in the red error message frame. Because I get it, there's not enough energy to do that now. I get it. 
- Slightly tuned the tracker size and position for better alignment with everything else. You probably didn't even notice it, so subtle was it. 
- The World Map now becomes slightly transparent when the player is moving. Just feels better to not completely block out the center of the screen when traveling from place to place on a fresh and very ganky PvP realm. 

## [1.0.35-RC] 2019-08-31
### Fixed
- Locked the main chat in a manner not affecting its DropDown, thus preventing taint from spreading to the Compact group frames. 

## [1.0.34-RC] 2019-08-31
### Fixed
- Fixed a typo causing the UI to bug out when your pet was just content, not happy. I thought this was a feature? :)

### Changed
- Made the aura filters even less filterish. We need actual lists here, since we can't check any real meta info of units not in our group. Will get myself up a few levels, then take a day to get this right!
- Removed the 3 limit buff cap on the target frame aura element. When you're a healer, you probably need to see more than just 3 happy ones. 
- Added an extra row of auras to the target frame, just to make sure we don't miss stuff while the filters are unfilterish. 

## [1.0.33-RC] 2019-08-31
### Added
- Added an experimental feature to show spell rank on actionbuttons when more than one instance of the spell currently exists on your buttons. 

### Changed
- Made the difference between usable and not usable spells more distinct. 

## [1.0.32-RC] 2019-08-30
### Fixed
- Fixed a typo causing an error when summoning pets. 

## [1.0.31-RC] 2019-08-30
### Changed
- Fixed some aura border coloring inconsistencies, as well as applied debuff type coloring to most auras that have a type. 

## [1.0.30-RC] 2019-08-30
### Fixed
- There should no longer be any misalignment when mousing over the world map to select zones.

## [1.0.29-RC] 2019-08-30
### Added
- Added a fix for players that suffered from AzeriteUI not loading because they mistakingly has TukUI or ElvUI installed. AzeriteUI should now load anyway, despite that horrible addon list. 

## [1.0.28-RC] 2019-08-30
### Fixed
- Player PvP icon should now properly be hidden while engaged in combat, to make room for the combat indicator. 

## [1.0.27-RC] 2019-08-30
### Added
- Added Pet Happiness as an experimental message to the bottom of the screen. 

## [1.0.26-RC] 2019-08-29
### Added
- Added a player PvP icon. It is placed where the combat indicator is, and thus hidden while in combat. 

### Changed
- Made the world map smaller, and stopped it from blocking out the world. We are aware that the overlay to click on zones is slightly misaligned, working on that. 
- Changed the aura filters to be pretty all inclusive. Will tune it for classic later on. 

### Fixed
- Fixed the display of Druid cat form combo points. It should now appear. If you're wondering why the points disappear everytime you change target, that's not a bug. That's a classic feature. 
- Fixed a bug when opening the talent window. 
- Fixed a lot of small issues and bugs related to auras and castbars. 

### Removed
- Disabled all castbars on frames other than the player and the pet. We will add a limited tracking system for hostile player casts by tracking combat log events later on. 

## [1.0.16-RC] 2019-08-12
### Changed
- The quest tracker now looks far more awesome. 
- The texture for active or checked abilities on the action buttons will now be hidden if the red auto-attack flash is currently flashing, making everything far easier to see and relate to. 
- Made the tooltip for auto-attack much more interesting, as it now shows your main- and off hand damage, attack speed and damage per second. Just like the weapon tooltips in principle, but with actual damage modifiers from attack power and such taken into account. 

### Fixed
- Fixed some issues that would cause attacks on the next swing to have their tooltips displayed slightly wonky. 

## [1.0.15-RC] 2019-08-11
### Changed
- The quest watcher is now visible again. We might write a prettier one later, this old one is kind of boring. 
- Improved the size and anchoring of the bag slot buttons beneath the backpack. 

## [1.0.14-RC] 2019-08-11
### Changed
- The durability frame is now placed more wisely. 

## [1.0.13-Alpha] 2019-08-11
### Changed
- Removed the "_Classic" suffix from the UI name in options menu. It doesn't need a different display name, because it's not a different UI, just for a different client. 
- Replaced the blip icon used to indicate what I thought was just resource nodes with a yellow circle with a black dot, as it apparently also is the texture used for identifying questgivers you can turn in finished quests too. Big purple star just didn't seem right there. 

## [1.0.12-Alpha] 2019-08-11
### Added
- Added minimap blip icons for 1.13.2! 
- Added styling to the up, down and to bottom chat window buttons. 

### Changed
- The GameTooltip now follows the same scaling as our own tooltips, regardless of the actual uiScale. 

## [1.0.11-Alpha] 2019-08-10
### Changed
- Disabled the coloring of the orb glass overlay, as this looked strange when dead or empty. None of those things seem to happen in retail. They do here, however. So now I noticed. 
- Disabled castbars on nameplates, as these can't be tracked through regular events in Classic. Any nameplate units would be treated as no unit given at all, which again would default to assuming the player as the unit, resulting in mobs often getting OUR casts on their castbars. We will be adding a combatlog tracking system for this later, which relies on unitGUIDs. 

### Fixed
- Fixed a bug when right-clicking the Minimap.

## [1.0.10-Alpha] 2019-08-10
### Added
- Hunters now get a mana orb too! 

## [1.0.9-Alpha] 2019-08-09
### Changed
- Removed all API calls related to internal minimap quest area rings and blobs.
- Removed a lot of unneeded client checks, as we're not checking for any retail versions anymore. 

## [1.0.8-Alpha] 2019-08-09
### Changed
- Removed more vehicle, override and possess stuff from the unitframe library. 

## [1.0.7-Alpha] 2019-08-09
### Changed
- Removed more petbattle and vehicle stuff from actionbutton library. 

## [1.0.6-Alpha] 2019-08-09
### Changed
- Disabled Raid, Party and Boss frames. Will re-enable Raid and Party when I get it properly tested after the launch. Did Boss frames exist? 

## [1.0.5-Alpha] 2019-08-09
### Fixed
- Fixed Rogue combo points. Cannot test Druids as they get them at level 20, and level cap here in the pre-launch is 15.

## [1.0.5-Alpha] 2019-08-09
### Fixed
- Fixed micro menu.
- Fixed option menu.
- Fixed aura updates on unit changes. 

## [1.0.3-Alpha] 2019-08-09
### Fixed
- Fixed typos in bindings module.
- Fixed API for castbars. 

## [1.0.2-Alpha] 2019-08-09
### Fixed
- Changed `SaveBindings` > `AttemptToAttemptToSaveBindings`, fixing the `/bind` hover keybind mode!

## [1.0.1-Alpha] 2019-08-09
- Public Alpha. 
- Initial commit.
