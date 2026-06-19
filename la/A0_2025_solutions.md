# A0 Linear Algebra 2025 — model solutions

*Worked solutions to the Trinity 2025 paper (A0, Linear Algebra). Conventions follow the course notes: $V'=\operatorname{Hom}(V,F)$, $\chi_T(x)=\det(T-xI)$, inner products / sesquilinear forms are **conjugate-linear in the first slot**.*

---

## Question 1

### (a)(i) Definitions

The **dual space** of $V$ is $V'=\operatorname{Hom}(V,F)$, the vector space of linear functionals $f:V\to F$. For a subspace $W\subseteq V$, the **annihilator** of $W$ is
$$W^{0}=\{f\in V'\;:\;f(w)=0\ \text{for all }w\in W\}.$$

### (a)(ii) $\dim W^0 = \dim V - \dim W$

Let $\dim V=n$, $\dim W=k$. Pick a basis $e_1,\dots,e_k$ of $W$ and extend it to a basis $e_1,\dots,e_n$ of $V$; let $e_1',\dots,e_n'$ be the dual basis ($e_i'(e_j)=\delta_{ij}$). I claim $W^0=\langle e_{k+1}',\dots,e_n'\rangle$.

* For $j>k$: $e_j'(e_i)=0$ for all $i\le k$, so $e_j'$ vanishes on a basis of $W$, hence on $W$. Thus $e_j'\in W^0$.
* Conversely if $f=\sum_{i=1}^n a_i e_i'\in W^0$, then for $i\le k$ we have $e_i\in W$, so $a_i=f(e_i)=0$. Hence $f\in\langle e_{k+1}',\dots,e_n'\rangle$.

These $n-k$ functionals are part of the dual basis, so are linearly independent. Therefore $\dim W^0=n-k=\dim V-\dim W$. $\qquad\blacksquare$

### (b) $V=\mathbb{R}[x]_{\le d}$, basis $\{1,x,\dots,x^d\}$, $\dim V=d+1$

A computation used throughout: for $0\le i,j\le d$,
$$\delta_i(x^j)=\left.\frac{d^i}{dx^i}x^j\right|_{0}=j(j-1)\cdots(j-i+1)\,x^{\,j-i}\Big|_0=\begin{cases} i! & j=i\\ 0 & j\ne i,\end{cases}\qquad\text{i.e. } \delta_i(x^j)=i!\,\delta_{ij}. \tag{$\star$}$$

### (b)(i) $\delta_i\in V'$

Differentiation $f\mapsto f^{(i)}$ is linear and maps polynomials to polynomials, and evaluation at $0$ is linear; their composite $\delta_i:f\mapsto f^{(i)}(0)$ is therefore a linear map $V\to\mathbb{R}$, i.e. $\delta_i\in V'$.

### (b)(ii) $\{\delta_i:0\le i\le d\}$ is a basis of $V'$

There are $d+1$ of them and $\dim V'=\dim V=d+1$, so it suffices to prove linear independence. Suppose $\sum_{i=0}^d c_i\delta_i=0$. Applying this to $x^j$ and using $(\star)$ gives $c_j\,j!=0$, so $c_j=0$ for every $j$. Hence they are independent, and being $d+1$ independent vectors in a $(d+1)$-dimensional space, they form a basis. $\qquad\blacksquare$

*(Equivalently, $(\star)$ says $\delta_i=i!\,b_i$ where $\{b_i\}$ is the dual basis to $\{x^i\}$.)*

### (b)(iii) $I=\int_0^1$ as a combination of the $\delta_i$

$I(f)=\int_0^1 f$ is linear, so $I\in V'$. Since the $\delta_i$ form a basis, $I=\sum_{i=0}^d c_i\delta_i$ for unique $c_i$. Evaluate both sides on $x^j$ using $(\star)$ and $I(x^j)=\int_0^1 x^j\,dx=\tfrac1{j+1}$:
$$\frac1{j+1}=I(x^j)=\Big(\sum_i c_i\delta_i\Big)(x^j)=c_j\,j!\quad\Longrightarrow\quad c_j=\frac{1}{(j+1)\,j!}=\frac{1}{(j+1)!}.$$
Therefore
$$\boxed{\,I=\sum_{i=0}^{d}\frac{1}{(i+1)!}\,\delta_i\,.}$$

### (b)(iv) Minimal and characteristic polynomials of $T$

Write $f=\sum_{j=0}^d a_j x^j$. By $(\star)$, $\delta_i(f)=i!\,a_i$, so $\dfrac{\delta_i(f)}{i!}=a_i$ and
$$T f=\sum_{i=0}^d \frac{x^{d-i}}{i!}\,\delta_i(f)=\sum_{i=0}^d a_i\,x^{d-i}.$$
Thus $T$ **reverses coefficients**: $T(x^j)=x^{d-j}$. Its matrix in the basis $\{1,x,\dots,x^d\}$ is the $(d+1)\times(d+1)$ exchange (anti-identity) matrix. Consequently
$$T^2(x^j)=T(x^{d-j})=x^{j}\quad\Longrightarrow\quad T^2=\mathrm{Id}.$$
So $m_T\mid x^2-1=(x-1)(x+1)$. For $d\ge1$, $T\ne\pm\mathrm{Id}$ (e.g. $T(1)=x^d\ne 1$), and both eigenvalues occur — $1+x^d$ is a $(+1)$-eigenvector and $x^d-1$ a $(-1)$-eigenvector. Hence
$$\boxed{\,m_T(x)=x^2-1=(x-1)(x+1).}$$
In particular $T$ is diagonalisable (distinct linear factors). The $(+1)$-eigenspace is the symmetric polynomials ($a_j=a_{d-j}$) and the $(-1)$-eigenspace the antisymmetric ones ($a_j=-a_{d-j}$). Counting (with $m=d+1$ coefficients): the $(+1)$-space has dimension $\lceil m/2\rceil$ and the $(-1)$-space $\lfloor m/2\rfloor$. Hence (monic form)
$$\boxed{\,\chi_T(x)=\pm(x-1)^{\lceil (d+1)/2\rceil}(x+1)^{\lfloor (d+1)/2\rfloor},}$$
the sign being $(-1)^{d+1}$ under the convention $\chi_T=\det(T-xI)$. Concretely: if $d$ is odd, both exponents are $\tfrac{d+1}2$; if $d$ is even, they are $\tfrac{d+2}2$ and $\tfrac d2$.

---

## Question 2

### (a)(i) Unitary

$T:V\to V$ is **unitary** if $T^*T=TT^*=\mathrm{Id}$ (equivalently $T^*=T^{-1}$; equivalently $\langle Tv,Tw\rangle=\langle v,w\rangle$ for all $v,w$).

### (a)(ii) A unitary map has an orthonormal eigenbasis

Induct on $n=\dim V$. The case $n=0$ is vacuous. Since $\mathbb C$ is algebraically closed, $\chi_T$ has a root $\lambda$, giving a unit eigenvector $v$, $Tv=\lambda v$. From $\langle v,v\rangle=\langle Tv,Tv\rangle=|\lambda|^2\langle v,v\rangle$ we get $|\lambda|=1$, so $\lambda\ne0$ and $T^*v=T^{-1}v=\lambda^{-1}v$; thus $U=\langle v\rangle$ is invariant under both $T$ and $T^*$.

$U^\perp$ is $T$-invariant: for $w\in U^\perp$ and $u\in U$,
$$\langle u,Tw\rangle=\langle T^*u,w\rangle=0\qquad(\text{since }T^*u\in U,\ w\in U^\perp),$$
so $Tw\in U^\perp$. The restriction $T|_{U^\perp}$ is again unitary (it preserves the inner product). By induction $U^\perp$ has an orthonormal eigenbasis; adjoining $v$ gives one for $V$. $\qquad\blacksquare$

### (b) The Hermitian form on $\mathbb{C}^3$

With the convention that the form is conjugate-linear in the first slot,
$$\langle z,w\rangle=\overline{z_3}w_1-\overline{z_2}w_2+\overline{z_1}w_3=z^*Hw,\qquad H=\begin{pmatrix}0&0&1\\0&-1&0\\1&0&0\end{pmatrix},$$
where $z^*$ is the conjugate transpose. Note $H=H^*$ (Hermitian).

### (b)(i) Non-degeneracy

A sesquilinear form is **non-degenerate** if $\langle v,w\rangle=0$ for all $w$ forces $v=0$ — equivalently its Gram matrix is non-singular. Here
$$\det H=1\cdot\det\begin{pmatrix}0&-1\\1&0\end{pmatrix}=1\neq0,$$
so $H$ is invertible and **the form is non-degenerate.**

### (b)(ii) Positive definiteness

Positive definite means $\langle v,v\rangle>0$ for all $v\ne0$. Take $v=(0,1,0)$: $\langle v,v\rangle=-|1|^2=-1<0$ (indeed $v=(1,0,0)$ gives $\langle v,v\rangle=0$, an isotropic vector). So **the form is not positive definite** — its signature is $(1,2)$, the eigenvalues of $H$ being $+1,-1,-1$.

### (b)(iii) Jordan forms in $N\cap U$

$U=\{A:\langle Av,Aw\rangle=\langle v,w\rangle\ \forall v,w\}=\{A:A^*HA=H\}$. For $A=\begin{pmatrix}1&x&y\\0&1&z\\0&0&1\end{pmatrix}\in N$, compute
$$A^*HA=\begin{pmatrix}0&0&1\\[2pt]0&-1&\bar x-z\\[2pt]1&x-\bar z&\;y+\bar y-|z|^2\end{pmatrix}.$$
Setting $A^*HA=H$ gives $z=\bar x$ and $2\operatorname{Re}(y)=|x|^2$. Hence
$$N\cap U=\left\{\begin{pmatrix}1&x&y\\0&1&\bar x\\0&0&1\end{pmatrix}:x\in\mathbb C,\ \operatorname{Re}(y)=\tfrac12|x|^2\right\}\quad(\text{the Heisenberg group}).$$
Every such $A$ is unipotent (only eigenvalue $1$), so its Jordan type is read off from
$$A-I=\begin{pmatrix}0&x&y\\0&0&\bar x\\0&0&0\end{pmatrix},\qquad (A-I)^2=\begin{pmatrix}0&0&|x|^2\\0&0&0\\0&0&0\end{pmatrix}.$$

| condition | $(A-I)^2$ | $(A-I)$ | Jordan form | example |
|---|---|---|---|---|
| $x\ne0$ | $\ne0$ | rank $2$ | $J_3(1)$ | $x=1,\,y=\tfrac12,\,z=1$ |
| $x=0,\ y\ne0$ | $0$ | rank $1$ | $J_2(1)\oplus J_1(1)$ | $x=0,\,y=i$ |
| $x=0,\ y=0$ | $0$ | $0$ | $I_3=J_1\oplus J_1\oplus J_1$ | $A=I$ |

(When $x=0$ the constraint forces $\operatorname{Re}(y)=0$, so $y$ is purely imaginary; $y=i$ is admissible.) So the **three possible Jordan normal forms are $I_3$, $\,J_2(1)\oplus J_1(1)$, and $J_3(1)$**, with the examples above:
$$I,\qquad \begin{pmatrix}1&0&i\\0&1&0\\0&0&1\end{pmatrix},\qquad \begin{pmatrix}1&1&\tfrac12\\0&1&1\\0&0&1\end{pmatrix}.$$

### (b)(iv) $U$ acts transitively on isotropic lines

Let $\mathcal L=\{L:\dim L=1,\ \langle v,v\rangle=0\ \forall v\in L\}$. First, $e_3=(0,0,1)$ is isotropic ($\langle e_3,e_3\rangle=0$), so $L_0=\langle e_3\rangle\in\mathcal L$. I show $U\cdot L_0=\mathcal L$.

**Lines with nonzero third coordinate.** For $A\in N\cap U$ as above, $A e_3=(y,\bar x,1)$. As $x$ ranges over $\mathbb C$ and $y$ over $\{\operatorname{Re}(y)=\tfrac12|x|^2\}$, the vectors $(y,\bar x,1)$ are exactly the isotropic vectors with third coordinate $1$: writing $(\alpha,\beta,1)$ with $\alpha=y,\beta=\bar x$, the isotropy condition $\langle(\alpha,\beta,1),(\alpha,\beta,1)\rangle=2\operatorname{Re}(\alpha)-|\beta|^2=0$ is precisely $\operatorname{Re}(y)=\tfrac12|x|^2$. Now any isotropic line with a representative $v=(a,b,c)$, $c\ne0$, equals $\langle(a/c,b/c,1)\rangle$ with $(a/c,b/c,1)$ isotropic; so some $A\in N\cap U$ sends $e_3$ into it, giving $A\,L_0=\langle v\rangle$.

**Lines with zero third coordinate.** If $c=0$, isotropy forces $2\operatorname{Re}(\bar a\cdot 0)-|b|^2=-|b|^2=0$, so $b=0$ and the line is $\langle e_1\rangle$. The real permutation $S=\begin{pmatrix}0&0&1\\0&1&0\\1&0&0\end{pmatrix}$ swaps the indices $1,3$; since $H$ is symmetric under this swap, $S^*HS=H$, so $S\in U$, and $S\,e_3=e_1$, giving $S\,L_0=\langle e_1\rangle$.

Every isotropic line falls into one of these two cases, so $U\cdot L_0=\mathcal L$: $U$ acts transitively. $\qquad\blacksquare$

---

## Question 3

### (a) Minimal polynomial, well-definedness

The **minimal polynomial** $m_T$ is the monic polynomial of least degree with $m_T(T)=0$.

*Existence:* $\operatorname{End}(V)$ has dimension $n^2$ ($n=\dim V$), so $I,T,\dots,T^{n^2}$ are linearly dependent, giving a nonzero annihilating polynomial; scaling to monic and taking least degree gives a candidate. *Uniqueness:* if $m_1,m_2$ are both monic of least degree with $m_i(T)=0$, then $m_1-m_2$ annihilates $T$ and has smaller degree, so it must be $0$. Equivalently, $\{p\in F[x]:p(T)=0\}$ is a nonzero ideal of the principal ideal domain $F[x]$, generated by a unique monic polynomial, namely $m_T$. $\qquad\blacksquare$

### (b)(i) $V=W_f\oplus W_g$ (Primary Decomposition, two-factor case)

Since $f,g$ are distinct monic irreducibles, $f^a$ and $g^b$ are coprime, so by Bézout there are $s,t\in F[x]$ with
$$s f^a+t g^b=1.\tag{$\dagger$}$$
Put $W_f=\ker f(T)^a$, $W_g=\ker g(T)^b$ (both $T$-invariant, as $f(T)^a$ and $g(T)^b$ commute with $T$). Evaluating $(\dagger)$ at $T$ and applying to $v\in V$:
$$v=\underbrace{t(T)g(T)^b\,v}_{\in\,W_f}+\underbrace{s(T)f(T)^a\,v}_{\in\,W_g},$$
because $f(T)^a\big(t(T)g(T)^b v\big)=t(T)m_T(T)v=0$ and likewise for the other term. So $V=W_f+W_g$. If $v\in W_f\cap W_g$ then $(\dagger)$ gives $v=t(T)g(T)^b v+s(T)f(T)^a v=0+0=0$. Hence $V=W_f\oplus W_g$.

For the minimal polynomials: $f(T)^a$ kills $W_f$, so $m_{T|W_f}\mid f^a$, forcing $m_{T|W_f}=f^c$ with $c\le a$; similarly $m_{T|W_g}=g^d$, $d\le b$. On the direct sum the minimal polynomial of $T$ is $\operatorname{lcm}(f^c,g^d)=f^c g^d$ (coprime factors). But this equals $m_T=f^a g^b$, so $c=a$, $d=b$. Thus $m_{T|W_f}=f^a$ and $m_{T|W_g}=g^b$. $\qquad\blacksquare$

### (b)(ii) The induced map on $V/\operatorname{im}f(T)$ and its minimal polynomial

$\operatorname{im}f(T)$ is $T$-invariant, since $T\big(f(T)v\big)=f(T)(Tv)\in\operatorname{im}f(T)$. By the induced-map lemma, $\overline T(v+\operatorname{im}f(T))=Tv+\operatorname{im}f(T)$ is a well-defined linear map on the quotient.

Using $V=W_f\oplus W_g$: on $W_g$ the minimal polynomial is $g^b$, coprime to $f$, so $f(T)|_{W_g}$ is invertible and $f(T)W_g=W_g$; on $W_f$, $f(T)$ is "nilpotent" ($f(T)^a|_{W_f}=0$). Hence
$$\operatorname{im}f(T)=f(T)W_f\oplus W_g,\qquad V/\operatorname{im}f(T)\;\cong\;W_f/f(T)W_f,$$
and $\overline T$ corresponds to the map induced by $S:=T|_{W_f}$ on $W_f/f(S)W_f$. Now $f(S)$ sends $W_f$ into $f(S)W_f$, i.e. into $0$ modulo $f(S)W_f$, so $f(\overline T)=0$ on the quotient. Thus $m_{\overline T}\mid f$. Since $f$ is irreducible and the quotient $W_f/f(S)W_f$ is nonzero ($f(S)$ is not surjective on $W_f$, being non-invertible), $m_{\overline T}\ne 1$. Therefore
$$\boxed{\,m_{\overline T}(x)=f(x).}$$
*(Sanity check: a single Jordan block $J_a(\lambda)$ with $f=x-\lambda$ has $f(S)$ the shift, $W_f/\operatorname{im}f(S)$ one-dimensional with $\overline T=\lambda$, minimal polynomial $x-\lambda=f$.)*

### (c) Characteristic $p>0$

### (c)(i) A matrix in $M_p(F)$ with minimal polynomial $x^p-1$

In characteristic $p$, $x^p-1=(x-1)^p$. The $p\times p$ cyclic permutation (companion) matrix
$$A=\begin{pmatrix}0&0&\cdots&0&1\\1&0&\cdots&0&0\\0&1&\cdots&0&0\\ \vdots& &\ddots& &\vdots\\0&0&\cdots&1&0\end{pmatrix}$$
satisfies $A^p=I$, so its minimal polynomial divides $x^p-1$; being a companion matrix it is cyclic, so its minimal polynomial equals its characteristic polynomial $x^p-1$. Hence $m_A(x)=x^p-1\ (=(x-1)^p)$. *(Equivalently take the single Jordan block $J_p(1)=I+N$ with $N$ the nilpotent shift: $(A-I)^p=N^p=0$, $(A-I)^{p-1}\ne0$, so $m_A=(x-1)^p=x^p-1$.)*

### (c)(ii) $T^{p^k}$ is diagonalisable over $\overline F$ for some $k\ge1$

Recall (the hint): an irreducible $f$ is **separable** — has no repeated root in $\overline F$ — iff $f'\ne0$, because a repeated root of $f$ is a common root of $f$ and $f'$, and $\gcd(f,f')\mid f$ is nontrivial only if $f'=0$ (as $\deg f'<\deg f$ and $f$ irreducible).

Set $m_0=m_T$. By hypothesis $m_0'\equiv0$. Over characteristic $p$, a polynomial has zero derivative iff every exponent appearing is a multiple of $p$, i.e. $m_0(x)=m_1(x^p)$ for some $m_1\in F[x]$. Moreover $m_1$ is irreducible: a factorisation $m_1=uv$ would give $m_0(x)=u(x^p)v(x^p)$, contradicting irreducibility of $m_0$. If $m_1'\equiv0$ as well, repeat: $m_1(x)=m_2(x^p)$ with $m_2$ irreducible, and so on. Since $\deg m_{i+1}=\tfrac1p\deg m_i$ strictly decreases, the process stops at some $k\ge1$ with
$$m_T(x)=m_k\!\left(x^{p^k}\right),\qquad m_k\ \text{irreducible with}\ m_k'\ne0.$$
By the hint, $m_k$ is separable, hence squarefree (its roots in $\overline F$ are distinct).

Now $m_T(T)=0$ reads $m_k\!\big(T^{p^k}\big)=0$, so the minimal polynomial of $S:=T^{p^k}$ divides the squarefree polynomial $m_k$, and is therefore itself squarefree with distinct roots in $\overline F$ — i.e. a product of distinct linear factors over $\overline F$. By the diagonalisability criterion, $S=T^{p^k}$ is diagonalisable over $\overline F$, with $k\ge1$. $\qquad\blacksquare$
