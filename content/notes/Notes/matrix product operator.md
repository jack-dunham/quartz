---
aliases: [MPO]
tags: [tensor-network/mpo]
---

In analogy to that of the [matrix product state (MPS)]({{< relref "20220504125719-matrix_product_state.md" >}}) representation of quantum states, operators can also be written as products of matrices. Consider the operator $O$ given by

$$
    O = \sum_{\{s_i\}, \{s'_i\} } O^{s_1, \ldots, s_N}_{s'_1, \ldots, s'_N}\dyad{s'_1\cdots s'_N}{s_1,\cdots,s_N},
$$

or graphically:
```tikz
\begin{document}
	\begin{tikzpicture}[t/.style = {draw, thick, minimum size=0.8cm}, thick, scale=1.2]
	        \node (0) at (0.3,0) {};
	        \node (5) at (4.7,0) {};
	        \node[t, label=center:$O^{[1]}$] (1) at (1,0){};
	        \node[t, label=center:$O^{[2]}$] (2) at (2,0){};
	        \node (3) at (3,0){$\ldots$};
	        \node[t, label=center:$O^{[N]}$] (4) at (4,0){};
	        \foreach \i in {0,...,4}
	        {
	          \pgfmathtruncatemacro{\iplus}{\i + 1};
	          \draw[-] (\i) -- (\iplus);
	        }
	        \foreach \i in {1,2,4}
	        {
	          \draw[-] (\i) -- (\i, -0.6);
	          \draw[-] (\i) -- (\i, 0.6);
	        }
	\end{tikzpicture}
\end{document}
```
Now suppose the operator can be expressed as

$$
    O = \sum_{i=1}^{N-1} A_i A_{i+1} + \sum_{i=1}^{N} B_i
$$

The corresponding tensors $M^{[i]s_i's_i}_{ \alpha_{i-1} \alpha_{i} }$ in the MPO representation are then

$$
    M^{ [i] s_i' s_i}_{\alpha_{i-1 } \alpha_{i}} = \begin{pmatrix}
        \mathbb{I}^{s_i' s_i} & A_i^{s_i' s_i} & B_i^{s_i' s_i} \\\\
        0 & 0 & A_i^{s_i' s_i} \\\\
        0 & 0 & \mathbb{I}^{s_i' s_i}
    \end{pmatrix}
$$

such that

$$
    O = \sum_{\\{s_i\\},\\{s_i'\\} }
    M^{[1]s_1's_{1} }_{1 \alpha_{1} }
    \cdots
    M^{[i]s_i's_i}_{\alpha_{i-1} \alpha_{i}  }
    \cdots
    M^{[N]s_{N}'s_{N} }_{\alpha_{N} 1}
    \dyad{s'_1\cdots s'_N}{s_1,\cdots,s_N}
$$


The left- and right-most matrices $M^{[1]s_1's_{1} }_{1 \alpha_{1} }$and $M^{[N]s_N's_{N} }_{ \alpha_{N-1} 1}$ are given by

$$
    M^{[1]s_1's_{1} }_{1 \alpha_{1} } = \begin{pmatrix}
        \mathbb{I}^{s_1's_1} & A_1^{s_1's_1} & B_1^{s_1's_1}
    \end{pmatrix}
    \qq{and}
    M^{[N]s_N's_{N}}_{\alpha_{N-1}1} = \begin{pmatrix}
        \mathbb{I}^{s_N's_N} \\\ A_N^{s_N's_N} \\\ B_N^{s_N's_N}
    \end{pmatrix}
$$


## Further reading
