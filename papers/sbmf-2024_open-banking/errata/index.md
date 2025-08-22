---
layout: page
title: Errata
subtitle: Formal privacy analyses for open banking (SBMF 2024)
---

<style>
  .code {
    white-space: pre-wrap;
  }

  .code.wrap-indent {
    text-indent: -5rem;
    padding-left: 5rem;
  }

  .join-top {
    margin-top: 0;
  }

  .join-bottom {
    margin-bottom: 0;
  }
</style>

This is a list of typos and other issues found in the paper:

* Page 14: The posterior probability of "High" given "Uber" should be 2/7, so that the column adds up to one
    (i.e., it is a valid probability distribution).  

* Page 22: On Table 7,
  - The caption should read "when demographic data is **not** available".
  - The number of randomly constructed joints is 30, not 1000.
  - The confidence interval for (Neuroticism, a_tot) should be \[−0.1016, −0.1015\]*.
  - The confidence interval for (Neuroticism, a_avg) should be \[-0.1273, -0.1272\]*.
  - The confidence interval for (Self-control, a_avg) should be \[+0.1351, +0.1352\]*.
  - Yep, I copied the wrong table... but these numbers don't impact results.  

* Page 23: Algorithm 1 has a bug: if the result of shuffling X and Z
    yields a Pearson correlation that is larger (or smaller, if negative) than the target,
    the while loop never terminates (e.g., if we are unlucky and shuffling sorts the data...).
    Here is an updated algorithm with a fix to this bug:

    {:.code}
    **function** generate_joint(Z, X, target_pcorr, ε)
    &nbsp; // First, update target if original target is unreachable
    &nbsp; **if** target_pcorr = 0 **then**
    &nbsp;   target_sign ⟵ 1
    &nbsp;   target pcorr ⟵ min(target_pcorr, pearson_upper_limit(Z, X))
    &nbsp; **else**
    &nbsp;   target_sign ⟵ -1
    &nbsp;   target pcorr ⟵ max(target_pcorr, pearson_lower_limit(Z, X))
    &nbsp; **end if**
    &nbsp; // Then, shuffle data to get an initial joint, making sure that
    &nbsp; // the pearson correlation does not go past the target
    &nbsp;  **repeat**
    &nbsp;   Z ⟵ shuffle Z
    &nbsp;   X ⟵ shuffle X
    &nbsp; **until** pearson(Z, X) * target_sign ≤ |target_pcorr| + ε
    &nbsp; n ⟵ |Z|
    &nbsp; // Finally, iteratively sort data at random
    &nbsp; **while** |pearson(Z, X) - target_pcorr| > ε **do**
    &nbsp;   **repeat**
    &nbsp;     indices ⟵ choose n indices at random
    &nbsp;     sort_dir ⟵ ascending **if** target_pcorr ≥ **else** descending
    &nbsp;     Z' ⟵ Z, with Z\[indices\] sorted according to sort_dir
    &nbsp;     X' ⟵ X, with X\[indices\] sorted in ascending order
    &nbsp;     retry ⟵ pearson(Z', X') * target_sign > |target_pcorr| + ε
    &nbsp;     n ⟵ ⌈n / 2⌉ **only if** retry is true
    &nbsp;   **until** retry is false
    &nbsp;   Z ⟵ Z'
    &nbsp;   X ⟵ X'
    &nbsp; **end while**
    &nbsp; **return** (Z,X)
    **end function**
