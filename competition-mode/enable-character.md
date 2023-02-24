---
description: >-
  By default, extra characters are not available for selection in Competition
  mode, so you need to manually enable it.
---

# Enable character

## Introduction:

To enable your character for selection in Competition mode, use the `bool ExtraChar.CompetitionMode.isCharacterAvailable(u8 xtrachar)` function.

## Usage example:

Return `true` to check with your character's ID to enable it for the Competition mode.

```javascript
// Sets the availability status of the character for selection in the Competition menu.
function bool ExtraChar.CompetitionMode.isCharacterAvailable(u8 xtrachar)
{
	// Mighty check
	if (xtrachar == 0x01)
		return true
	
	// Call the base function
	return base.ExtraChar.CompetitionMode.isCharacterAvailable(xtrachar)
}
```
