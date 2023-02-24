# Character physics

## Introduction:

To set up custom physics for your character, use the `void ExtraChar.CompetitionMode.Character.setupPhysics(u8 xtrachar, u16 speedcap, u16 acceleration, u16 deceleration)` function.

## Usage example:

<pre class="language-javascript"><code class="lang-javascript"><strong>// Sets physics in Competition mode for Extra characters.
</strong>function void ExtraChar.CompetitionMode.Character.setupPhysics(u8 xtrachar, u16 speedcap, u16 acceleration, u16 deceleration)
{
	// Ray's physics
	if (xtrachar == 0x01)
	{
		speedcap = 0x04c0
		acceleration = 0x001c
		deceleration = 0x0070
	}

	// Call the base function
	base.ExtraChar.CompetitionMode.Character.setupPhysics(xtrachar, speedcap, acceleration, deceleration)
}
</code></pre>

## Analysis:

<pre class="language-javascript"><code class="lang-javascript">// Sets physics in Competition mode for Extra characters.
<strong>function void ExtraChar.CompetitionMode.Character.setupPhysics(u8 xtrachar, u16 speedcap, u16 acceleration, u16 deceleration)
</strong>{
	// Call the base function
	base.ExtraChar.CompetitionMode.Character.setupPhysics(xtrachar, speedcap, acceleration, deceleration)
}
</code></pre>

Add this function to your mod with a call to the base function. Then add a check of the variable `xtrachar` equal to the ID of your character. No additional checks are required here, such as which player `A` or `B` chose an extra character, the framework has already taken care of this.

> Also, **never return**. You only change the values, below, additional calculations occur in the called base function. When you return, your physics will be broken.

Next, let's analyze variables such as `speedcap`, `acceleration`, and `deceleration`.

`speedcap` is the value corresponding to the maximum running speed of the character. This value increases by two when receiving the _"Speed Boots"_ bonus, and decreases by half when _"Slow Boots"_.\
`acceleration` is the acceleration power of the character. No matter how large the value is set for it, it will always be limited to the `speedcap` value.\
`deceleration` is the power of slowing down your character.

The more values are set, the greater the effect it will give. Experiment! By default, if you don't specify physics for your character, Sonic physics will be used.
