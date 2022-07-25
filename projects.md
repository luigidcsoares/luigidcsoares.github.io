---
layout: page
title: Projects
---

---

### Lif 
<a href="https://github.com/lac-dcc/lif" target="_blank" 
    class="fa-icon" title="Source Code">
    <span class="fab fa-github fa-lg fa-github-colored"></span>
</a> <a href="http://cuda.dcc.ufmg.br/lif/" target="_blank" 
    class="fa-icon" title="Online Tool">
    <span class="fas fa-tools fa-lg fa-tools-colored"></span>
</a> 

A program is said to be isochronous if its running time does not depend on
classified information. Isochronicity is an essential property in cryptographic
implementations, for isochronous programs do not leak time-related information.
In this project, we adapted Moll and Hack’s Partial Control-Flow Linearization
algorithm, initially developed in the context of vectorization to remove
divergent branches, to the context of side-channel resistance. We developed a
prototype on top of LLVM. Lif extends previous work in non-trivial ways: it can
handle programs with unbounded loops and does not require runtime information.

**[MSc Thesis]**{: style="font-family: Courier New, Helvetica, monospace"}  
_Memory-Safe Elimination of Side Channels_ 
<a href="/papers/ufmg-msc.pdf" target="_blank"
    class="fa-icon" title="Paper">
    <span class="fas fa-file-pdf fa-lg fa-pdf-colored"></span>
</a> <a href="https://youtu.be/ZB5QoPhSaBU" target="_blank"
    class="fa-icon" title="Presentation">
    <span class="fab fa-youtube fa-lg fa-youtube-colored"></span>

**[CGO 2021]**{: style="font-family: Courier New, Helvetica, monospace"}  
_Memory-Safe Elimination of Side Channels_ 
<a href="/papers/cgo21-lif.pdf" target="_blank"
    class="fa-icon" title="Paper">
    <span class="fas fa-file-pdf fa-lg fa-pdf-colored"></span>
</a> <a href="https://youtu.be/k_EMQibQxas" target="_blank"
    class="fa-icon" title="Presentation">
    <span class="fab fa-youtube fa-lg fa-youtube-colored"></span>

---

### Escape Analysis

We implemented an Escape Analysis on top of Go’s SSA intermediate
representation, as an extension of Go’s existing Escape Analysis.  We tested our
implementation against four real benchmarks and we obtained an average speedup
of 1.3%, with the highest speedup being 3.4%.

**[Bachelor's Thesis]**{: style="font-family: Courier New, Helvetica, monospace"}  
_Escape Analysis for Static Single Assignment Form_ 
<a href="/papers/pucmg-escape.pdf" target="_blank"
    class="fa-icon" title="Paper">
    <span class="fas fa-file-pdf fa-lg fa-pdf-colored"></span>
</a> 

---
