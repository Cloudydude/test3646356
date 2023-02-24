# Shared Memory

## Stored data

Address values that are automatically stored in PersistentData and SRAM. Be careful when making your changes to the data, as this may damage your saves.

<details>

<summary><code>0x8fe660</code> ... <code>0x8fe667</code></summary>

* Related functions:\


Addresses for saving character IDs in Data Select slots. Each subsequent byte corresponds to a slot in the menu. (Don't consider No Save and Delete slots)

Base u32 Address: `0x8fe660`\
Address key: `sharedmemory.xtrachar`\
``PersistentData key: `SRAM_Extraslots`\
``SRAM info: \
&#x20;   Offset: `0x660`\
``    Size: `0x08`

```javascript
// - 0x8fe660	-> Save slot 1 (Saved extra character)
// - 0x8fe661	-> Save slot 2 (Saved extra character)
// - 0x8fe662	-> Save slot 3 (Saved extra character)
// - 0x8fe663	-> Save slot 4 (Saved extra character)
// - 0x8fe664	-> Save slot 5 (Saved extra character)
// - 0x8fe665	-> Save slot 6 (Saved extra character)
// - 0x8fe666	-> Save slot 7 (Saved extra character)
// - 0x8fe667	-> Save slot 8 (Saved extra character)
```

</details>

<details>

<summary><code>0x8fe668</code> ... <code>0x8fe676</code></summary>

Addresses for saving character IDs in the slots of the Competition mode zones. Every 3 bytes is a slot with the corresponding places in the list.

Base u32 Address: `0x8fe668`\
Address key: `sharedmemory.records.xtrachar`\
PersistentData key: `SRAM_CompetitionExtraChars`\
``SRAM info: \
&#x20;   Offset: `0x668`\
&#x20;   Size: `0x0f`

```javascript
// - 0x8fe668	-> Azure Lake (Best time extra character)
// - 0x8fe669	-> Azure Lake (Second time extra character)
// - 0x8fe66a	-> Azure Lake (Third time extra character)

// - 0x8fe66b	-> Balloon Park (Best time extra character)
// - 0x8fe66c	-> Balloon Park (Second time extra character)
// - 0x8fe66d	-> Balloon Park (Third time extra character)

// - 0x8fe66e	-> Desert Palace (Best time extra character)
// - 0x8fe66f	-> Desert Palace (Second time extra character)
// - 0x8fe670	-> Desert Palace (Third time extra character)

// - 0x8fe671	-> Chrome Gadget (Best time extra character)
// - 0x8fe672	-> Chrome Gadget (Second time extra character)
// - 0x8fe673	-> Chrome Gadget (Third time extra character)

// - 0x8fe674	-> Endless Mine (Best time extra character)
// - 0x8fe675	-> Endless Mine (Second time extra character)
// - 0x8fe676	-> Endless Mine (Third time extra character)
```

</details>

<details>

<summary><code>0x8fe677</code> ... <code>0x8fe707</code></summary>

Addresses for saving character IDs in DAGE Challenge mode slots. Every 0x48 bytes are responsible for their own mode, every 3 bytes is a zone (considering the act) of 1 byte for 3 slots.

Base u32 Address: `0x8fe677`\
Address key: `sharedmemory.challenge.xtrachar`\
PersistentData key: `SRAM_ChallengeExtraChars`\
``SRAM info: \
&#x20;   Offset: `0x678`\
&#x20;   Size: `0x48 * 0x03`

```javascript
// - 0x8fe677			-> Next 0x48 byte's is selected extra characters in Act Select mode.
// - 0x8fe677 + 0x48		-> Next 0x48 byte's is saved extra characters in Teme Attack mode.
// - 0x8fe677 + 0x48 + 0x48	-> Next 0x48 byte's is saved extra characters in Time Stone Run mode.

// First 0x48 bytes (Act Select mode)

// - 0x8fe677	-> AIZ Act 1 (on Sonic)
// - 0x8fe678	-> AIZ Act 1 (on Tails)
// - 0x8fe679	-> AIZ Act 1 (on Knuckles)

// - 0x8fe67a	-> AIZ Act 2 (on Sonic)
// - 0x8fe67b	-> AIZ Act 2 (on Tails)
// - 0x8fe67c	-> AIZ Act 2 (on Knuckles)
// (...)
// - 0x8fe6b9	-> DEZ Act 1 (on Sonic)
// - 0x8fe6ba	-> DEZ Act 1 (on Tails)
// - 0x8fe6bb	-> DEZ Act 1 (on Knuckles)

// - 0x8fe6bc	-> DEZ Act 2 (on Sonic)
// - 0x8fe6bd	-> DEZ Act 2 (on Tails)
// - 0x8fe6be	-> DEZ Act 2 (on Knuckles)
```

</details>
