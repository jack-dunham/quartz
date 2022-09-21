> cont. from written notes

Repeat SVD until one open index per tensor. 

The wavefunction in this form is known as a *matrix product state. 

A matrix product state looks like this:
```tikz
\begin{document}
	\begin{tikzpicture}
		\foreach \x in {1,...,5}{
		\node[draw, minimum size=0.5cm, thick] (\x) at (\x,0) {};
		\node (s\x) at (\x, -1) {$s_\x$};
		\draw[thick, red] (\x) to (s\x);
		}
		\foreach \x in {1,...,4}{
		\pgfmathtruncatemacro{\xp}{\x + 1};
		\draw[thick] (\x) to (\xp);
		}
	\end{tikzpicture}
\end{document}
```
A matrix product operator looks like this:
```tikz
\begin{document}
	\begin{tikzpicture}
		\foreach \x in {1,...,5}{
		\node[draw, minimum size=0.5cm, thick] (\x) at (\x,0) {};
		\node (s\x) at (\x, -1) {$s_\x$};
		\node (t\x) at (\x, 1) {$t_\x$};
		\draw[thick, red] (\x) to (s\x);
		\draw[thick, red] (\x) to (t\x);
		}
		\foreach \x in {1,...,4}{
		\pgfmathtruncatemacro{\xp}{\x + 1};
		\draw[thick] (\x) to (\xp);
		}
	\end{tikzpicture}
\end{document}
```




