# Discord RPC

## Introduction:

To change the character name displayed during the game in your Discord profile, use `string ExtraChar.getCharacterName(u8 xtrachar)` function.

This function will also automatically display your character's name, along with the number of emeralds collected, so that apart from specifying the name, you don't need anything else.

## Usage example:

Return a `string` with the name to check with your character ID.

```javascript
// Returns the name of active Extra character.
function string ExtraChar.getCharacterName(u8 xtrachar)
{
	// Shadow's check
	if (xtrachar == 0x05)
		return "Shadow"
	
	// Call the base function
	return base.ExtraChar.getCharacterName(xtrachar)
}
```

<figure><img src="../../.gitbook/assets/Снимок экрана (323).png" alt=""><figcaption></figcaption></figure>
