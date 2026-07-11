
---
title: "Assignment 3"
author: "Suwetha A/P S Raman Naidu"
csl: vancouver.csl
theme: serif
background-color: "#ffffff"
transition: slide
navigationMode: linear
hash: true
---

## Effect of Pressure and Temperature on PartResistance for Machine 1

This boxplot illustrates the distribution of `PartResistance` for `Machine 1` across different levels of `Pressure`, with the boxes further colored by `Temperature`. This visualization helps to understand how these factors, both individually and in combination, influence the part's resistance.

From the ANOVA, we observe the following statistical significances (Pr(>F) values):

*   **Pressure**: `Pr(>F) = NA`
*   **Temperature**: `Pr(>F) = 0.000000`
*   **Pressure * Temperature interaction**: `Pr(>F) = 0.082204`

These values indicate the probability of observing such an effect by chance. A smaller Pr(>F) (typically < 0.05) suggests a statistically significant effect.

<div class="r-stretch">
<iframe data-src='media/plots/machine1_boxplot_plot.html' width='100%' height='500px' style='border:none;'></iframe>
</div>

---
