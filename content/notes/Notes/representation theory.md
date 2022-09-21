A $n$-dimensional representation of a group $G$ on a vector space $\mathbb{V}$ denoted $\Gamma$ is a mapping from $G$ to the set $GL(\mathbb{V})$. The $n$-dimensional vector space $\mathbb{V}$ is known as the **representation space** of $\Gamma$. 

## Irreducible representations
The representation space $\mathbb{V}$ can, in general, be decomposed into a set of **invariant subspaces** $\mathbb{V}_l$ each with dimension $d_{i}< n$. That is,
$$
\mathbb{V} \cong \mathbb{V}_{1}\oplus \mathbb{V}_{2}\oplus\mathbb{V}_{3}\oplus \ldots
$$
A vector $\mathbf{v}\in \mathbb{V}_l$ remains in $\mathbb{V}_i$ upon the action of an element of the group $G$:
$$
\mathbf{v}\in \mathbb{V}_l \, \Rightarrow \,\Gamma(g)\mathbf{v} \in \mathbb{V}_l, \quad \forall g \in G,\mathbf{v} \in \mathbb{V}_l
$$
Each invariant subspace corresponds to an [[irreducible representation]] (irrep) of the group $G$. What this means is that you can write any representation $\Gamma(g)$ in block diagonal form, where the blocks are irreducible representations of $G$ denoted $U_l(g)$
$$
\Gamma(g) \cong 

\begin{pmatrix} U_1(g)&&\\&U_2(g)&\\&&U_3(g) \\ \end{pmatrix} 
$$
The irrep $U_{l}(g)$ corresponds to the invariant subspace $\mathbb{V}_{l}$. An irreducible representation cannot be reduced further. That is, an irreducible representation cannot be block-diagonalised into smaller representations still.  For an **abelian group**, all the irreps are one-dimensional.