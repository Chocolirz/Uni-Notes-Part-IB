# IB Math Supervision Quick Notes
Ruize Li, rl737@cam.ac.uk

Jesus College, University of Cambridge

Supervisor: Mr Bob Dillon

# Lent Term
## Supervision Jan 23 2025
### Q: Complex eigenvalues
Related to 2006 Paper 1 Q4. 

When we have a matrix $B$ that satisfies
$$
\begin{split}
B_{ij}v_j&=v_i-(b\times v)_i \\
B_{ij}(b\times v)_j&=(b\times v)_i + \vert b\vert^2 v_i
\end{split}
$$
Suppose we have somehow shown that $v$ and $(b\times v)$ can be eigenvectors of $B$ and we want to find the eigenvalues. If we construct, in the $\hat b$-$(\hat b\times\hat v)$ plane,
$$
\hat b\times\hat v=\mathrm i\hat v;\qquad \mathrm i(\hat b\times\hat v)=-\mathrm i\hat v=\mathrm i^3\hat v,
$$
we get eigenvalues $1-\mathrm i\vert b\vert$ for both $v$ and $(b\times v)$. But if we construct the rotation in another way,
$$
\hat b\times\hat v=-\mathrm i\hat v;\qquad \mathrm i(\hat b\times\hat v)=\hat v,
$$
which is also valid, we would get another set of eigenvalues $1+\mathrm i\vert b\vert$ for both $v$ and $(b\times v)$. Should we keep both sets and write $\lambda=\lambda_{\pm}=1\pm \mathrm i\vert b\vert$? Or, should we only keep one set for a specific choice of rotation direction?

Keep both - There’s a complex conjugate pair of $v$, one for each eigenvalue. 

Also, the determinant is a cubic function. So once we found a complex eigenvalue, the other must be its complex conjugate. 
### Q: Grad
Is it okay to write $\nabla\Phi$ as $\mathrm d\Phi/\mathrm d\vec r$ for a scalar field $\Phi$? It seems that in this way it’s easy to show that
$$
\nabla\Phi=\sum_i \frac{1}{h_i}\frac{\partial\Phi}{\partial q_i}\hat e_i;\qquad h_i=\left\vert\frac{\partial\vec r}{\partial q_i}\right\vert,\quad \hat e_i=\frac{1}{h_i}\frac{\partial \vec r}{\partial q_i}. 
$$
Method: write $\mathrm d\Phi$ as …

### Series solutions
Michaelmas 快结束的时候 check for some 达朗贝尔


### Sheet 4 Q8 singular points at infinity!!!

Useful way to check jump relations and nearest pole: each prime on $y$ gives a jump and every power of $p(x)$ give another jump. But it is not related to the number of linearly independent solutions we have. For example,
$$
y^{\prime\prime}-xy=0
$$
has third order jumps $a_{n+3}=h(a_n)$, but only have two linearly independent solutions. And
$$
y^{\prime\prime}-(\lambda-x)y=0
$$
has a third-order relation
$$
a_{n+3}=h(a_{n+2},a_{n})
$$

### Q9 related to quantum mechanics
$w$ is a function of $\xi$ therefore we need chain rule to transform $\Psi$ into it. 
The final part gives a nicer recurrent relationship. 

Consider the condition of $\Psi$ to be not normalisable. 

### Q10
About an irregular singular point, one of the solutions might not be series solutions. That’s the point where we need to use the $W$ matrix. 

## Supervision Jan 30 2025
### Intro
This week’s lectures were all on the Sturm-Liouville form of differential operators. Self-adjoint (Hermitian) operators have a lot of well-behaved properties, which could be used in physics and theoretical chemistry. Sturm-Liouville theory is a theory for operators with “coefficients” as real functions. But we will soon show that it is not necessarily the case. 

### Definition of Hermitian conjugate
The Hermitian conjugate is defined through dot products
$$
\langle u\vert \mathcal Lv\rangle=\langle \mathcal L^\dagger u\vert v\rangle.
$$
In matrix conditions, it happens to be $M^\dagger=(M^*)^T=(M^T)^*$. 

### First-order self-adjoint operators
Consider an operator $\mathcal L=\rho(x)\frac{\mathrm d}{\mathrm dx}$, then
$$
\begin{split}
\langle u\vert\mathcal Lv\rangle&=\int_a^b u^*\rho\frac{\mathrm dv}{\mathrm dx}\ \mathrm dx=u^*\rho v\vert_{a}^b-\int_a^b v\ \mathrm d(u^*\rho) \\
&=u^*\rho v\vert_a^b - \int_a^b \left[u^*\frac{\mathrm d\rho}{\mathrm dx}+\rho\frac{\mathrm du^*}{\mathrm dx}\right]v\ \mathrm dx \\
&=u^*\rho v\vert_a^b - \int_a^b \left[\left(\frac{\mathrm d\rho^*}{\mathrm dx}+\rho^*\frac{\mathrm d}{\mathrm dx}\right)u\right]^*v\ \mathrm dx \\
&=[\cdots]_a^b+\langle \mathcal L^\dagger u\vert v\rangle
\end{split}
$$
Here, if $\mathcal L=\mathcal L^\dagger$, $\rho$ must be a constant, and must be purely imaginary. That brings us to the frequently-seen operators in quantum mechanics:
$$
\hat p=-\mathrm i\hbar\nabla;\quad \hat H=\mathrm i\hbar\frac{\partial}{\partial t};\quad \hat L_z=-\mathrm i\hbar\frac{\partial}{\partial \phi}.
$$
This also means S-L form is not the only form that is self-adjoint. Also, the functions in the operator do not need to be purely real. 

### Sturm-Liouville Theory - Development
For a general form of second-order differential operator,
$$
\tilde{\mathcal L}=\alpha(x)\frac{\mathrm d^2}{\mathrm dx^2}+\beta(x)\frac{\mathrm d}{\mathrm dx}+\gamma(x),
$$
we want it to be self-adjoint. To write it in S-L form, we need to multiply it by a weight function $w$. 
$$
\begin{split}
w\alpha y’’+w\beta y’+w\gamma y&=w\mathcal Ly; \\
-\frac{\mathrm d}{\mathrm dx}\left[\rho\frac{\mathrm d}{\mathrm dx}y\right]+\sigma y&=\tilde{\mathcal L}y.
\end{split}
$$
It is easy to see that $w\alpha=-\rho$ and $w\beta=-\rho’$. We well show that $\rho$ and $\sigma$ are real soon. Therefore
$$
\frac{\mathrm d\rho}{\rho}=\frac{\beta}{\alpha}\ \mathrm dx\qquad w=-\frac{\rho}{\alpha}=-\frac{1}{\alpha}\exp\left(\int_a^b\frac{\beta}{\alpha}\ \mathrm dx\right).
$$
Remember that we want $\mathcal L$ to be Hermitian, now we must show that $\tilde{\mathcal L}$ is indeed Hermitian by finding its eigenvalues and eigenfunctions. 
$$
\begin{split}
\tilde{\mathcal L}\phi_n&=w\lambda_n\phi_n \\
\langle\phi_n\vert\tilde{\mathcal L}\phi_m\rangle&=\int_a^b\phi_n^*\lambda_mw\phi_m\ \mathrm dx
\end{split}
$$
We want that
$$
\langle\phi_n\vert\tilde{\mathcal L}\phi_m\rangle=\langle\tilde{\mathcal L}\phi_n\vert\phi_m\rangle=\lambda_m\int_a^b \phi_n^*w\phi_m\ \mathrm dx
$$
so we write out the second inner product:
$$
\int_a^b\left(\lambda_nw\phi_n\right)^*\phi_m\ \mathrm dx=\lambda_n^*\int_a^b\phi_n^*w^*\phi_m\ \mathrm dx.
$$
Now we assert that $w=w^*$, i.e., $w$ is a **real** function. Then, we subtract the two inner products to get
$$
0=(\lambda_m-\lambda_n^*)\int_a^b\phi_n^*w\phi_m\ \mathrm dx\doteq(\lambda_m-\lambda_m^*)\int_a^b w\vert\phi_m\vert^2\ \mathrm dx.
$$
When $m\ne n$, the integral is zero, which means eigenfunctions are orthogonal. But when $m=n$, either $(\lambda_m-\lambda_m^*)$ or the intergal is zero. Well, can the integral be zero? It might be if $w$ changes sign! We need to assert that $w$ does not change sign, which makes everything real and (positive) definite. 

There’s another problem, consider the form of $w$, 
$$
w(x)=-\frac{1}{\alpha}\exp\left(\int_a^b \frac{\beta}{\alpha}\ \mathrm dx\right),
$$
what constrains must we make to $\alpha$ and $\beta$ to make $w$ (positive) definite? For example, $w$ may change sign if $\beta$ is constant and $\alpha$ is proportional to $x$. In this case $w$ will have the form
$$
w\propto \exp(\ln x)=x,
$$
which indeed would change sign if $0\in (a, b)$. Same things would happen if $\beta$ and $\alpha$ are polynomials. Writing in the standard form
$$
y’’+p(x)y’+q(x)y=f(x),
$$
we see that $w$ may change sign if our domain contains singular points of $p(x)$. 

### Sturm-Liouville Theory - Core
$$
\begin{split}
\mathcal L&=-\frac{\mathrm d}{\mathrm dx}\left[\rho\frac{\mathrm d}{\mathrm dx}\right]+\sigma \\
\langle u\vert\mathcal Lv\rangle&=\int-u^*\frac{\mathrm d}{\mathrm dx}\left[\rho\frac{\mathrm dv}{\mathrm dx}\right]+u^*\sigma v\ \mathrm dx \\
&=[-\rho u^*v’]+\int\left(\frac{\mathrm du^*}{\mathrm dx}\rho\right)\frac{\mathrm dv}{\mathrm dx}+u^*\sigma v\ \mathrm dx \\
&=[-\rho u^*v’+\rho u^{*\prime}v]+\int-\frac{\mathrm d}{\mathrm dx}\left(\rho\frac{\mathrm du^*}{\mathrm dx}\right)v+u^*\sigma v\ \mathrm dx \\
&=[\rho(u^{*\prime}v-u^*v^\prime)]+\int\left\{\left[-\frac{\mathrm d}{\mathrm dx}\left(\rho^*\frac{\mathrm d}{\mathrm dx}\right)+\sigma^*\right]u\right\}^*v\ \mathrm dx
\end{split}
$$
From this it is easy to see that $\rho$ and $\sigma$ must be real for $\mathcal L$ to equal $\mathcal L^\dagger$. 

**Conclusion**: Following our convention, in the S-L form, $\rho$ and $\sigma$ must both be real, and the weight function $w$ must not change sign in the range $x\in [a,b]$. 
### Solving differential equations
Just like what we did to Green’s functions, we compare with matrices:
$$
\begin{split}
M\vec x&=\vec b \\
\vec x&=M^{-1}\vec b \\
\text{if}\quad M&=M^\dagger \\
\text{with}\quad M\hat e_i&=\lambda_i \hat e_i \\
\text{Then}\quad \hat e_j^\dagger \hat e_i&=\delta_{ij} \\
\Rightarrow\quad \vec b&=\sum_i \alpha_i \hat e_i \\
&=\sum_i (\hat e_i^\dagger \vec b)\hat e_i \\
\Rightarrow\quad \vec x&=M^{-1}\sum_i\alpha_i\hat e_i \\
&=\sum_i\frac{\hat e_i}{\lambda_i}\alpha_i \\
&=\left[\sum_i\frac{\hat e_i\hat e_i^\dagger}{\lambda_i}\right]\vec b \\
\Rightarrow\quad M^{-1}&=\sum_i\frac{\hat e_i\hat e_i^\dagger}{\lambda_i}
\end{split}
$$
Similarly, we have our (weighted) method to find Green’s function:
$$
\begin{split}
\mathcal Ly&=f \\
y&=\mathcal L^{-1}f \\
\text{If}\quad \mathcal L&=\mathcal L^\dagger \\
\text{with}\quad \mathcal L\phi_n&=w\lambda_n\phi_n \\
\text{Then}\quad \langle\phi_n\vert\phi_m\rangle_w&=\delta_{nm} \\
\Rightarrow\quad f(x)&=\sum_nw(x)\phi_n(x)\beta_n \\
&=\sum_nw(x)\phi_n(x)\langle\phi_n\vert f\rangle\quad\text{Note\ that\ this\ is\ not\ weighted!} \\
\Rightarrow\quad y&=\mathcal L^{-1}\sum_nw(x)\phi_n(x)\beta_n \\
&=\sum_n\frac{\phi_n(x)\beta_n}{\lambda_n} \\
&=\sum_n\frac{\phi_n(x)}{\lambda_n}\int_\xi\phi_n^*(\xi)f(\xi)\ \mathrm d\xi \\
&=\int_\xi f(\xi)\left[\sum_n\frac{\phi_n(x)\phi_n^*(\xi)}{\lambda_n}\right]\ \mathrm d\xi \\
\Rightarrow G(x,\xi)&=\sum_n\frac{\phi_n(x)\phi_n^*(\xi)}{\lambda_n}
\end{split}
$$
## Supervision Feb 6 2025