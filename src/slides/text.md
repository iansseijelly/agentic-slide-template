---
layout: default
---

<div class="eyebrow">04 · Text and bullets</div>

# Lorem ipsum dolor sit amet.

<p class="lead">Consectetur adipiscing elit, sed do eiusmod tempor incididunt.</p>

<div class="body-copy">

- **Lorem ipsum.** Dolor sit amet, consectetur adipiscing elit.
- **Sed do eiusmod.** Tempor incididunt ut labore et dolore magna aliqua.
- **Ut enim ad minim.** Veniam, quis nostrud exercitation ullamco laboris.

</div>

<p class="bottom-note accent">Duis aute irure dolor in reprehenderit.</p>

<!--
Text: keep to three or four points. Bold the phrase the audience should remember.
For progressive delivery, wrap the Markdown list in <v-clicks> ... </v-clicks>.
-->

---
layout: split
ratio: equal
---

<div class="eyebrow">05 · Two-column comparison</div>

# Lorem ipsum, dolor sit amet.

<p class="lead">Consectetur adipiscing elit. Ut enim ad minim veniam.</p>

::left::

<h2 class="comparison-heading">Lorem ipsum</h2>

- Dolor sit amet, consectetur.
- Adipiscing elit, sed do eiusmod.
- Tempor incididunt ut labore.

::right::

<h2 class="comparison-heading">Dolor sit amet</h2>

- Ut enim ad minim veniam.
- Quis nostrud exercitation.
- Ullamco laboris nisi ut aliquip.

::bottom::

<span class="accent">Lorem ipsum.</span> Ex ea commodo consequat.

<!--
Comparison: the default slot is the shared heading; left and right are independent columns.
Use ratio: wide-left or wide-right when one side needs more room.
-->
