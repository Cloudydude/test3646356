---
description: Optional special function, for characters, with combinations (partner) support
---

# Force to update

{% hint style="info" %}
This is a special optional feature. Use it only if you know what you are doing.
{% endhint %}

## Introduction:

You can also force a Discord RPC update for non-Extra characters, but for [character partners](#user-content-fn-1)[^1], like _Extra Slot Ray_ or _Extra Slot Amy Rose_.

To do this, use `bool ExtraChar.RPCManager.checkForceToUpdate()` function.

### Usage example:

Return `true` for the states when the Discord RPC needs to be updated. For example, _Extra Slot Ray_ can be a partner for Sonic, Knuckles, and for _Extra Slot Mighty_.

```javascript
// The function forcibly updates the Discord RPC.
function bool ExtraChar.RPCManager.checkForceToUpdate()
{
	// Only for main game
	if (global.game_mode == 0x8c)
	{
		if (global.characters == CHARS_SONIC_AND_TAILS && (Ray_Partner == 0x01 || Ray_Partner == 0x04))
			return true
		else if ((useKnucklesAndTails || global.characters == CHARS_KNUCKLES_AND_TAILS) && (Ray_Partner == 0x02 || Ray_Partner == 0x04))
			return true
	}
	
	// Call the base function
	return base.ExtraChar.RPCManager.checkForceToUpdate()
}
```

Now, when the RPC is updated for the partner character, we need to specify the name displayed in your profile. Just add the same checks as in the forced update function, for `string ExtraChar.getCharacterName(u8 xtrachar)`, but return the name of your character in combination.

```javascript
// Only for main game
if (global.game_mode == 0x8c)
{
	if (global.characters == CHARS_SONIC_AND_TAILS && (Ray_Partner == 0x01 || Ray_Partner == 0x04))
		return "Sonic & Ray"
	else if ((useKnucklesAndTails || global.characters == CHARS_KNUCKLES_AND_TAILS) && (Ray_Partner == 0x02 || Ray_Partner == 0x04))
		return "Knuckles & Ray"
}
```

### Usage example:

```javascript
// Returns the name of active Extra character.
function string ExtraChar.getCharacterName(u8 xtrachar)
{
	// Ray's check
	if (xtrachar == 0x02) // As active Extra character
		return "Ray"
	
	// Only for main game
	if (global.game_mode == 0x8c) // As Partner character
	{
		if (global.characters == CHARS_SONIC_AND_TAILS && (Ray_Partner == 0x01 || Ray_Partner == 0x04))
			return "Sonic & Ray"
		else if ((useKnucklesAndTails || global.characters == CHARS_KNUCKLES_AND_TAILS) && (Ray_Partner == 0x02 || Ray_Partner == 0x04))
			return "Knuckles & Ray"
	}
	
	// Call the base function
	return base.ExtraChar.getCharacterName(xtrachar)
j
```

<figure><img src="../../.gitbook/assets/Снимок экрана (320).png" alt=""><figcaption></figcaption></figure>

[^1]: The partner system is not part of the framework at the moment, but it is in the plans for updating in the future.
