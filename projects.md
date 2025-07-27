---
layout: page
title: Projects
---

---

### Open banking

The term “Open Banking” describes a series of global initiatives to allow the sharing of customer data between financial companies 
to facilitate competition within their sector.
In this project, we formalise in the rigorous framework of quantitative information flow (QIF)
relevant privacy risks in a concrete Open Banking scenario, namely:
(i) transaction-history recovery and (ii) collateral attribute-inferences using external correlations.
We provide extensive analyses of these risks in real-world data from Open Banking, supplied by a fintech in Australia.
We show that the Open Banking system studied presents considerable privacy risks with respect to transactions,
both in the presence and in the absence of demographic data.
Finally, we exemplify potential real-world collateral attribute-inference attacks,
in which we show how an attacker might leverage scientific correlations 
to infer individuals’ level of neuroticism and self-control from their transaction history.
We hope that this work may: 
(i) help financial customers in Australia make better-informed decisions about what kind of information, 
and how much of it, to share via Open Banking;
(ii) raise awareness about the potential privacy risks of Open Banking in other countries; and
(iii) foster the development of privacy regulation in digital finance and the open data economy.

{: style="white-space: pre-wrap;"}
**def** publication_list(), **do**: [
   %{
      **type**: "Conference",
      **where**: "SBMF 2024",
      **title**: "Formal privacy analyses for open banking",
      **links**: [[DOI](https://doi.org/10.1007/978-3-031-78116-2_11), [PDF](/papers/sbmf-2024_open-banking/manuscript.pdf)],
      **errata**: [Click here](/papers/sbmf-2024_open-banking/errata/)
   }
]

---

### QIF - Operational Significance

There are emerging needs in quantitative theories of information flow
to assess privacy. Until recently, the consensus was that quantitative
information flow should be founded on the concepts of Shannon
Entropy and its related measures. Geoffrey Smith showed, in 2009,
that Shannon Entropy and Mutual Information do a poor job in
characterizing confidentiality. The truth is that Shannon's work was
not devised in the context of privacy, but rather for communication.
This shows the importance of understanding the operational
significance of the measures that we choose. Yet, till these days
people continue to adopt measures indiscriminately, without reasoning
about the meaning of such measures and without providing explanation
on why such measures are good in the contexts they are being applied.
In this project, we explore case studies that show the failure of some
measures when applied in the context of privacy, to demonstrate and
reinforce the importance of understanding a measure's operational
interpretation.

---

### Lif 
<a href="https://github.com/lac-dcc/lif" 
    class="fa-icon" title="Source Code">
    <span class="fa-brands fa-github fa-lg" aria-hidden="true"></span>
</a> <a href="http://cuda.dcc.ufmg.br/lif/"
    class="fa-icon" title="Online Tool">
    <span class="fa-solid fa-screwdriver-wrench fa-lg" aria-hidden="true"></span>
</a> 

A program is said to be isochronous if its running time does not depend on
classified information. Isochronicity is an essential property in cryptographic
implementations, for isochronous programs do not leak time-related information.
In this project, we adapted Moll and Hack’s Partial Control-Flow Linearization
algorithm, initially developed in the context of vectorization to remove
divergent branches, to the context of side-channel resistance. We developed a
prototype on top of LLVM. Lif extends previous work in non-trivial ways: it can
handle programs with unbounded loops and does not require runtime information.

{: style="white-space: pre-wrap;"}
**def** publication_list(), **do**: [
   %{
      **type**: "Journal",
      **where**: "TOPLAS",
      **title**: "Side-channel elimination via partial control-flow linearization",
      **links**: [[DOI](https://doi.org/10.1145/3594736?cid=99659884520)]
   },
   %{
      **type**: "Conference (extended abstract)",
      **where**: "CTD",
      **title**: "Memory-safe elimination of side channels",
      **links**: [[DOI](https://doi.org/10.5753/ctd.2023.229445)]
   },
   %{
      **type**: "MSc thesis",
      **title**: "Memory-safe elimination of side channels",
      **links**: [[PDF](/papers/ufmg-msc.pdf)]
   },
   %{
      **type**: "Conference",
      **where**: "CGO 2021",
      **title**: "Memory-safe elimination of side channels",
      **links**: [[DOI](https://doi.org/10.1109/CGO51591.2021.9370305), [PDF](/papers/cgo21-lif.pdf), [Talk](https://youtu.be/k_EMQibQxas)]
   }
]


---

### Escape Analysis

Escape analysis refers to a compile-time approach that simply establishes
whether an object can be stack-allocated or not. An object is said to escape
from a function or procedure _m_ if its lifetime exceeds the lifetime of _m_.
We implemented an Escape Analysis on top of Go’s SSA intermediate
representation, as an extension of Go’s existing Escape Analysis.  We tested our
implementation against four real benchmarks and we obtained an average speedup
of 1.3%, with the highest speedup being 3.4%.

{: style="white-space: pre-wrap;"}
**def** publication_list(), **do**: [
   %{
      **type**: "BSc thesis",
      **title**: "Escape analysis for static single assignment form",
      **links**: [[PDF](/papers/pucmg-escape.pdf)]
   }
]

---
