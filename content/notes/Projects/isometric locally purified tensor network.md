---
aliases: [isoLPTN]
tags: [tensor-network, algorithms]
---

## Background and motivation
This is effectively combining an [[isometric tensor network]] ansatz, with a locally purified one, motivated by the following:
1. It is potentially efficient in truncation by making use of an isometric tensor network ansatz (isoTNS)---no approximate contractions required.
2. Potentially efficient in calculation of observables. To see this, note that the isometric form makes calculating quantities like $\tr(\rho^{\dagger} \mathcal{O}_{i}\rho)$, with local $\mathcal{O}_i$ trivial, however for mixed states, $\braket{\mathcal{O}_{i}}= \tr(\mathcal{O}_{i} \rho )$ and thus the isometric structure cannot be exploited. If instead we represent $X$, where $\rho = X X^{\dagger}$,  as a isometric tensor network, then observables can be calculated efficiently. 
	- This has the additional benefit that the ansatz remains positive.
3. One could then potentially use a time-evolution algorithm to compute approximations to eigenvalues of the Liouvillian spectrum via so-called Arnoldi-Lindblad evolution. 

Specifically in the context of the work in this group:
1. We wish to investigate finite systems *without* translational invariance, such as strained graphene. 
2. We can do finite scaling analysis to verify the output of iPEPO based algorithms. 

## Potential problems
There is no theoretical basis suggesting isometric tensor networks can represent steady states of the Liouvillians of interest (or any). Work would be appreciated here. Potentially possible to prove within the context of quantum circuits as quantum circuits are naturally isometric. Perhaps it would be wise to get in contact with Andrew Green about this. This is likely a hard problem however, as very little progress has been made *at all* in the theory connecting TNs and open quantum systems. I am unsure whether this is because it is very hard (likely) or that closed systems are yielding enough results that researchers haven't bothered yet (also likely). I reckon that making connections between isoTNS and steady states of certain Liouvillians is an easier problem than connecting the latter with quantum information theory such as proving area-law entanglment growth. Probably a bit too ambitious. 

Isometric tensor networks require a "Moses move"  step to move the orthogonality centre. This is approximate, and will introduce error proportional to the system size and number of time steps. This is unlikely a problem provided the system converges to the steady state fast enough, as such, in contrast to coherent time-evolution, minimising the error at each time step is may be more important than minimising total compounding error. On the other hand, choosing a too small time step may result in the error dominating the time evolution resulting in poor convergence. 
