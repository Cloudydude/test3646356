---
description: Empty ROM addresses used by the framework
---

# ROM Addresses

<details>

<summary><code>0xffffe653</code></summary>

Sets flags when loading the zone, if the character has a custom objects, layout, rings. See `HAS_*` constants.

Size: `u8`\
``Address key: `global.xtrachar`

</details>

<details>

<summary><code>0xffffe654</code></summary>

Current active extra character in the Main game. It is also sets in some menus when selecting an extra character.

Size: `u8`\
``Address key: `global.xtrachar`

</details>

<details>

<summary><code>0xffffe655</code></summary>

Current active extra character in Competition mode (P1).

Size: `u8`\
``Address key: `competition_mode.xtrachar.player1`

</details>

<details>

<summary><code>0xffffe656</code></summary>

Current active extra character in Competition mode (P2).

Size: `u8`\
``Address key: `competition_mode.xtrachar.player2`

</details>

<details>

<summary><code>0xffffe657</code> ... <code>0xffffe65c</code></summary>

Stores a backup of selected extra characters in all slots on Competition mode character selection.

Base u32 Address: `0xffffe657`\
Address key: `competition_mode.xtrachar.backup`

```
// - 0xffffe657		->	Player 1's (on Sonic)
// - 0xffffe658		->	Player 1's (on Tails)
// - 0xffffe659		->	Player 1's (on Knuckles)

// - 0xffffe65a		->	Player 2's (on Sonic)
// - 0xffffe65b		->	Player 2's (on Tails)
// - 0xffffe65c		->	Player 2's (on Knuckles)
```

</details>

<details>

<summary><code>0xffffe65d</code></summary>

Stores a backup of player 1's vanilla character before the race. (Competiton mode)

Size: `u8`\
``Address key: `competition_mode.character.backup1`

</details>

<details>

<summary><code>0xffffe65e</code></summary>

Stores a backup of player 2's vanilla character before the race. (Competiton mode)

Size: `u8`\
``Address key: `competition_mode.character.backup2`

</details>

<details>

<summary><code>0xffffe65f</code></summary>

Sets the total number of extra characters available on the ending screen.

Size: `u8`\
``Address key: `global.ending.xtrachar`

</details>
