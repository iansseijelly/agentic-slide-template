---
layout: figure
---

<div class="eyebrow">06 · Figure and caption</div>

# Duis aute irure dolor.

<p class="lead">In reprehenderit in voluptate velit esse cillum dolore.</p>

::figure::

<FigurePlaceholder label="Lorem ipsum dolor sit amet" />

::caption::

Lorem ipsum · Consectetur adipiscing elit, sed do eiusmod tempor incididunt.

<!--
Figure: replace FigurePlaceholder with an image, SVG, or another Vue component.
Example: <img src="../assets/figures/example.svg" alt="Describe what the figure shows" />.
Use src/assets/figures for local images; paths here are relative to this Markdown file.
Vite bundles images referenced by img tags or Markdown image syntax.
Keep the source / citation in the caption slot.
-->

---
layout: split
ratio: wide-left
---

<div class="eyebrow">07 · Code and explanation</div>

# Ut enim ad minim veniam.

<p class="lead">Quis nostrud exercitation ullamco laboris nisi ut aliquip.</p>

::left::

```python
def lorem(ipsum):
    dolor = [sit for sit in ipsum
             if sit > 0]
    return sum(dolor)

amet = lorem([3, 1, -2, 4])
print(amet)
```

<p class="caption">Lorem ipsum · Dolor sit amet.</p>

::right::

<div class="code-notes">
<h3>Lorem</h3>
<p>Ipsum dolor sit amet,<br>consectetur adipiscing elit.</p>
<h3>Dolor</h3>
<p>Sed do eiusmod tempor<br>incididunt ut labore.</p>
<h3>Amet</h3>
<p>Et dolore magna aliqua.</p>
</div>

<!--
Code: use a real language identifier for syntax highlighting. Prefer fewer than 12 lines.
The example is valid Python; replace it with a small, complete example for your topic.
-->

---
layout: default
---

<div class="eyebrow">08 · Table</div>

# Ex ea commodo consequat.

<p class="lead">Duis aute irure dolor in reprehenderit in voluptate.</p>

| Lorem | Ipsum | Dolor | Amet |
| :--- | :--- | ---: | ---: |
| Consectetur | Adipiscing | 24 | 1.2 |
| Sed eiusmod | Tempor | 38 | 1.8 |
| Ut labore | Dolore | 52 | 2.4 |
| Magna aliqua | Veniam | **64** | **3.1** |

<p class="caption">Lorem ipsum · Dolor sit amet, consectetur adipiscing elit.</p>

<!--
Table: four rows and four columns keep it readable. Right-align quantities.
All numbers in this gallery are placeholders, not measurements.
-->

---
layout: split
ratio: wide-left
---

<div class="eyebrow">09 · Chart and takeaway</div>

# Sed ut perspiciatis unde.

<p class="lead">Omnis iste natus error sit voluptatem accusantium.</p>

::left::

<BarChart :items="[{ label: 'Lorem', value: 38 }, { label: 'Ipsum', value: 64 }, { label: 'Dolor', value: 52 }, { label: 'Amet', value: 86 }]" :max="100" label="Lorem ipsum · 00–100" />

<p class="caption">Lorem ipsum · 00–100 · Dolor sit amet.</p>

::right::

<div class="chart-notes">
<div class="key-number">86</div>
<h3>Lorem ipsum</h3>
<p>Dolor sit amet, consectetur adipiscing elit.</p>
<p>Sed do eiusmod tempor incididunt ut labore.</p>
</div>

<!--
Chart: pass labels and non-negative values to BarChart. The scale includes the largest value.
This component suits a few short categories; use a plotting tool for scientific figures.
A prominent number must agree with the chart. The 86 here is illustrative.
-->

---
layout: figure
---

<div class="eyebrow">10 · Process diagram</div>

# Nemo enim ipsam voluptatem.

<p class="lead">Quia voluptas sit aspernatur aut odit aut fugit.</p>

::figure::

<ProcessDiagram :steps="[{ title: 'Lorem', detail: 'Dolor sit amet' }, { title: 'Ipsum', detail: 'Consectetur elit' }, { title: 'Dolor', detail: 'Sed do eiusmod' }]" />

::caption::

Lorem ipsum → Dolor sit amet → Consectetur adipiscing elit.

<!--
Process: pass three or four short steps. The component spaces them and draws arrows.
For branching graphs, substitute a Mermaid diagram or a custom SVG in the figure slot.
-->

---
layout: figure
---

<div class="eyebrow">11 · Timeline / roadmap</div>

# Ut labore et dolore magna.

<p class="lead">Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>

::figure::

<MilestoneTimeline :items="[{ date: '01', title: 'Lorem ipsum', detail: 'Dolor sit amet' }, { date: '02', title: 'Consectetur', detail: 'Adipiscing elit' }, { date: '03', title: 'Sed eiusmod', detail: 'Tempor incididunt' }, { date: '04', title: 'Ut labore', detail: 'Dolore magna' }]" />

::caption::

Lorem ipsum · Sed do eiusmod tempor incididunt.

<!--
Timeline: three or four milestones with short labels. Dates are display labels, not a time scale.
Use a different chart if actual elapsed durations need to be represented.
-->
