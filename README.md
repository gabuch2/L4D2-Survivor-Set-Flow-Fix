# Survivor Set Flow Fix
This plugin fixes oddities when playing with an unintended survivor set in campaigns.

This plugin fixes the following:
- Custom maps often detect which survivor triggered some button or sequence to play certain conversation lines, however in many custom maps important events are bound by these conversations happening so if, for example, Nick activates a radio on a map with the L4D1 survivor set, the map would softlock because the entity flow never considered Nick. The fix is done by manipulating the filter_activator_model's logic (the entity used most of the time to check the survivor), so it would also fix problems if your server has custom models.
- If a campaign sequence has a func_orator entity managing survivor conversations, whenever an unintended survivor activates it, it would keep playing conversations as if the event would never had happened. For example: Survivors keep telling to turn off the alarm in the second map of The Parish, or most radios keep asking if there's anyone alive when activated (All official campaigns).

Note that if your server has survivors with the `m_survivorCharacter` value higher than 7, they will be considered as Nick/Bill.

## ConVars
- sm_l4d2_triggerflowfix_enabled
  - Determines if the plugin should try to fix this flow or not.
    - Default: 1

## Changelog
- 2.0.1
  - Fixed the plugin not working if, for some reason, it loads after Left 4 DHooks Direct. Thanks Silvers for the fix.
    - Upgrading from an older version requires Left 4 DHooks Direct 1.135 or newer.
- 2.0
  - The plugin now fully fixes the oddities with func_orator (Most official maps)
  - Plugin renamed to Survivor Set Flow Fix (from Trigger Flow Flix) to better represent the original problem the plugin aims to fix. The plugin filename is kept the same for legacy purposes.
- 1.0
  - Initial Release

## Dependencies
- [Left 4 DHooks Direct (1.135 or newer)](https://forums.alliedmods.net/showthread.php?t=321696)

## Supported Games
- Left 4 Dead 2 only