---
description: Used addresses of objects for which temporary values are set.
---

# \[Object] Addresses

### `0xffffb128`, `0xffffb172`, `0xffffb1bc`, `0xffffb206`, `0xffffb250`, `0xffffb292`, `0xffffb2e4`, `0xffffb32e`

Addresses of slot objects in the Data Select menu. (Don't consider No Save and Delete slots)

Base u32 Address: `0xffffb128`\
``Offset: `0x4a`

<details>

<summary><code>u8[A0 + 0x24]</code></summary>

Returns `0x00` if not an extra character, or the ID of the shown character.

</details>

<details>

<summary><code>u8[A0 + 0x05]</code></summary>

The right value of the saved extra character for the slot. It determines the value for `u8[A0 + 0x24]`.

</details>

<details>

<summary><code>u8[A0 + 0x08]</code></summary>

A temporary value that is set when deleting a slot with an extra character. Returns `true`.

</details>

<details>

<summary><code>u8[A0 + 0x3b]</code></summary>

Returns `true` for the locked character.

</details>

<details>

<summary><code>u8[A0 + 0x3c]</code></summary>

Sets to `true` when trying to create a save with a locked extra character.

</details>

<details>

<summary><code>u8[A0 + 0x3d]</code></summary>

While `u8[A0 + 0x3c]` is set, this counts up to `48` value to stop flashing.

</details>

