## Tensor products of matrices
The Kronecker product of an $n_1 \times n_2$ matrix $A$ and a $m_1 \times m_2$ matrix $B$ is usually defined as the following $n_1 m_1 \times n_2 m_2$ matrix:
$$
	A \otimes B = 
		\begin{pmatrix}
			a_{11}B & \cdots & a_{1 n_2} B \\
			\vdots & \ddots  & \vdots \\
			a_{n_1 1} B & \cdots & a_{n_1 n_2} B
		\end{pmatrix}
$$
> [!NOTE] The above is the most commonly used convention, but not the only one that can be chosen.

The Kronocker product has the following properties:
- It is bilinear, i.e. linear in both arguments.
- It is associative, that is $(A\otimes B) \otimes C  =  A \otimes (B \otimes C)$
- It is generally *non*-commutative, *but* $B \otimes A = P (A \otimes B) Q^{-1}$ for some permutations $P$ and $Q$
- $(A\otimes B)(C \otimes D) = AC\otimes BD$
### Pauli matrices
The Pauli matrices are ubiquitous throughout physics. We use the following definitions
$$
\sigma^x = \mqty(\pmat{1}), \quad \sigma^y = \mqty(\pmat{2}) \qq{and} \sigma^z = \mqty(\pmat{3}) 
$$
with a basis $\ket{\uparrow}  = \smqty(1 \\ 0)$ and $\ket{\downarrow} = \smqty(0 \\ 1)$.  We can also define the Pauli raising and lowering operators as
$$
\sigma^+ = \mqty(0 & 1 \\ 0 & 0) \qq{and} \sigma^- = \mqty(0 & 0 \\ 1 & 0) 
$$
respectively.

## Heisenberg model with $S=1/2$
Consider the following Hamiltonian $H$ corresponding to the Heisenburg model for spin-half particles:
$$
H = \sum_i \left( S_i^x S_{i+1}^x + S_i^y S_{i+1}^y + S_i^z S_{i+1}^z\right) + h \sum_i S_i^z
$$
with spin matrices $S^{\alpha} = \frac{1}{2} \sigma^{\alpha}$. How can we construct $H$ explictly? Consider the case of only two sites $H^{(2)}$
$$
H^{(2)} = S_i^x S_{i+1}^x + S_i^y S_{i+1}^y + S_i^z S_{i+1}^z+ h (S_i^z \otimes \mathbb{I} + \mathbb{I} \otimes S_i^z).
$$
Now if we define $S^{\alpha (2)} = \mathbb{I} \otimes S^{\alpha}$ and $\mathbb{I}^{(2)} = \mathbb{I} \otimes \mathbb{I}$, then the three site Hamiltonian can be written as 
$$
H^{(3)} = H^{(2)} \otimes \mathbb{I} + S^{x (2)} \otimes S^x + S^{y (2)} \otimes S^y + S^{z (2)} \otimes S^z + h(\mathbb{I}^{(2)} \otimes \mathbb{I}).
$$
Following the pattern, we can define a recurrence relation for a general $n$-site Hamiltonian. Let
$$
S^{\alpha (n + 1)} = \mathbb{I}^{(n)} \otimes S^{\alpha} \qq{and} \mathbb{I}^{(n+1)} = \mathbb{I}^{(n)} \otimes \mathbb{I}
$$
then 
$$
H^{(n+1)} = H^{(n)} \otimes \mathbb{I} + S^{x (n)} \otimes S^x + S^{y (n)} \otimes S^y + S^{z (n)} \otimes S^z + h(\mathbb{I}^{(n)} \otimes \mathbb{I}).
$$
The size of the matrix $H^{(2)}$ is $2^{n} \times 2^n$, i.e. exponential in the number of particles $n$. Pratically, this presents a challenge as modern supercomputers can only store "small" matrices, and there is no concievable way to store the exact Hamiltonian of a $100$ particle system, as this would require more matter than exists in the Universe. A proposed solution is to *make $H^{(n)}$ smaller* by truncating the Hilbert space onto *relevant* degrees of freedom. As an initial guess, one might chose to project onto the $m$ lowest eigenstates of $H^{(n)}$. We can capitulate this into the following following algorithm.

This algorithm is akin to the numerical renormalization group (NRG), with a slight difference which I cannot remember, but that doesnt matter---the point is that this truncation procedure performs *poorly*. We might that be? Fundamentally we are constructing eigenfunctions of a $(n+1)$-site lattice from eigenfunctions of a $n$-site lattice. Looking at the form of these eigenfunctions, which are essentially non-iteracting and thus plane waves, we can say that issues arrise at the related to the boundary conditions. 

## Steven White (1992)
Instead of projecting onto the eigenstates of a smaller system, we instead project the *wavefunction* onto a subset of the *reduced density matrix*. 


