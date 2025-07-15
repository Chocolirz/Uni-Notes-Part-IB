# IB Math Supervision Quick Notes
Ruize Li, rl737@cam.ac.uk

Jesus College, University of Cambridge

Supervisor: Mr Bob Dillon

# Michaelmas Term
## Supervision Oct 10 2024
### Sheet 0 Q1
Eigen-something, such as eigenvalue
$$Mx=\lambda x,$$
in quantum mechanics are really important. Matrices links vectors to vectors. Similarly, Fourier series links vectors and functions, build functions using basis functions. 

Differentiating operators turns functions into functions. Such as the Schrödinger equation. Divergence measures the flow of a field, and curl measures the circulating change in a plane. 

Matrices, derivatives, etc. They are all relations between functions, they "do not exist". Considering the Fourier series, if $h$ is a small value,
$$
f(a+h)=\left[1+h\frac{\mathrm d}{\mathrm dx}+\frac{1}{2!}\left(h\frac{d}{dx}\right)^2+\cdots\right]f(a)=\mathrm e^{h\frac{\partial}{\partial x}}f(a).
$$
That's what exponential operators are like. It shifts the functions to another place. Similarly, for two variables,
$$
f(x+h,y+k)=\mathrm e^{h\frac{\partial }{\partial x}}\mathrm e^{k\frac{\partial}{\partial y}}f(x,y).
$$
However, be aware that $\mathrm e^{a}\mathrm e^{b}\ne \mathrm e^{a+b}$ if $a$ and $b$ does not commute. 

That may help understanding the force on dipole is $\vec F=\vec p\cdot\nabla\vec E=\vert p\vert\hat p\cdot\nabla \vec E$ . The $\hat p\cdot\nabla$ is asking how rapidly the field changes in the direction of a dipole (directional derivative). 

### Sheet 0 Q2
$$
\frac{\mathrm d}{\mathrm dk}I(k)=\frac{\mathrm d}{\mathrm dk}\int_{a(k)}^{b(k)} f(x,k)\ \mathrm dx
$$
$$
\frac{\mathrm d}{\mathrm dk}I(k)=f(b,k)\frac{\mathrm db}{\mathrm dk}-f(a,k)\frac{\mathrm da}{\mathrm dk}+\int_{a(k)}^{b(k)} \frac{\partial }{\partial k}f(x,k)\ \mathrm dx.
$$
Visualise it by drawing diagrams. 

### Sheet 0 Q3
To solve
$$
x^2\frac{\mathrm d^2y}{\mathrm dx^2}+3x\frac{\mathrm dy}{\mathrm dx}-15y=0,
$$
guessing $y=x^\lambda$, and substitute into the equation, we can get $\lambda=3$ or $-5$, and the general solution is simply $y=Ax^3+B/x^5$. The method is okay for this particular equation, but what if $\lambda_1=\lambda_2$?

To actually solve the equation, the substitution should be $x=\mathrm e^{t}$. In this way, $\mathrm d/\mathrm dx$ are replaced by $\mathrm e^{-t}\ \mathrm d/\mathrm dt$ . 
$$
\left(\mathrm e^t\right)^2\left(e^{-t}\frac{\mathrm d}{\mathrm dt}\right)\left(\mathrm e^{-t}\frac{\mathrm d}{\mathrm dt}\right)y+\alpha\mathrm e^t\left(e^{-t}\frac{\mathrm d}{\mathrm dt}\right)y-\beta y=0.
$$
Expand the first term,
$$
\mathrm e^t\left[\mathrm e^{-t}\frac{\mathrm d^2y}{\mathrm d t^2}-\mathrm e^{-t}\frac{\mathrm dy}{\mathrm dt}\right]+\alpha\frac{\mathrm dy}{\mathrm dt}-\beta y=0.
$$
Then replace $y$ by $x^\lambda=\mathrm e^{\lambda t}$. In each term, $\mathrm e^t$ and $\mathrm e^{-t}$ come together and vanishes. We are left with
$$
\lambda^2+(\alpha-1)\lambda-\beta=0.
$$
If $\lambda_1=\lambda_2$, think about what we have done for damped oscillators. We wrote $y=(A+Bt)\mathrm e^{\lambda t}$. In this case the solution should be in the same form. Therefore it is obvious that the trick is to add a $\ln x$ term. 
$$
y=(A+B\ln x)x^\lambda.
$$
That's how we solve this kind of problems. 
## Supervision Oct 17 2024
Fourier domain is about expressing the same thing in a different basis (basis functions).
### Sheet 0 Q4
Express the extended $f(x)=x(\pi-x)$ in Fourier series. By symmetry (the function is an odd function), all cosine terms vanish. The extended function should be
$$
h(x)=B_0+\sum_{n=1}^{\infty}B_n\sin(nx).
$$
Obviously $B_0=0$, and
$$
B_n=\frac{1}{\pi}\int_{-\pi}^\pi x(\pi-x)\sin(nx)\ \mathrm dx=\frac{2}{\pi}\int_{0}^{\pi}x(\pi-x)\sin(nx)\ \mathrm dx.
$$
Since
$$
\int_0^\pi x\sin(nx)\ \mathrm dx=-\frac{1}{n^2}\int_0^{n\pi}u\ \mathrm d\cos u,\quad u=nx,
$$
and
$$
\begin{split}
\int_0^\pi x^2\sin(nx)\ \mathrm dx&=\frac{1}{n^3}\int_0^{n\pi}u^2\ \mathrm d\cos u \\
&=-\frac{1}{n^3}u^2\cos u\Big\vert_0^{n\pi}+\frac{2}{n^3}\int_0^{n\pi}u\ \mathrm d \sin u,
\end{split}
$$
we get
$$
B_n=\frac{4}{\pi n^3}(1-(-1)^n).
$$
Then everything else is obvious. 

### Sheet 0 Q5
Understand what it means by "**a function of two variables**". The correct answer should be something like
$$
\begin{split}
f(r,\theta)&=r \\
f(r,\theta,\phi)&=r \\
f(r,\theta,z)&=r+z 
\end{split}
$$

### Sheet 0 Q6
Prove by plugging in the given expression of $\hat e_3$. 
$$
\begin{split}
\hat e_2\times\hat e_3&=\hat e_2\times(\hat e_1\times\hat e_2) \\
&=(\hat e_2\cdot\hat e_1)\hat e_2-(\hat e_2\cdot\hat e_2)\hat e_1 \\
&=-\hat e_1
\end{split}
$$
Similarly,
$$
\begin{split}
\hat e_3\times\hat e_1&=(\hat e_1\times\hat e_2)\times\hat e_1 \\
&=(\hat e_1\cdot\hat e_1)\hat e_2-(\hat e_1\cdot\hat e_2)\hat e_1 \\
&=\hat e_2
\end{split}
$$
And the problem is solved. 

### Sheet 0 Q7
Should'n be a problem, just remember what is meant by div and curl. Plus, Div and Curl are both doing something that ignores the mean flow, and tries to see what is happening in addition to that. 

### Sheet 0 Q8
Nothing

### Sheet 0 Q9
Use the Levi-Civita symbol 
$$
\epsilon_{ijk}\epsilon_{ilm}=\delta_{jl}\delta_{km}-\delta_{jm}\delta_{kl}.
$$
to do $\vec a\times(\vec b\times\vec c)$:
$$
\begin{split}
[\vec a\times(\vec b\times\vec c)]_i&=\epsilon_{ijk}a_j(\vec b\times\vec c)_k \\
&=\epsilon_{ijk}a_j\epsilon_{klm}b_lc_m \\
&=\epsilon_{ijk}\epsilon_{klm}a_jb_lc_m \\
&=\epsilon_{kij}\epsilon_{klm}a_jb_lc_m \\
&=(\delta_{il}\delta_{jm}-\delta_{jl}\delta_{im})a_jb_lc_m \\
&=a_jb_ic_j-a_jb_jc_i \\
&=[(\vec a\cdot\vec c)\vec b-(\vec a\cdot\vec b)\vec c]_i.
\end{split}
$$
If we replace $\vec a$ by $\nabla$, things are a bit different.
$$
\begin{split}
[\nabla\times(\vec a\times\vec b)]_i&=(\delta_{il}\delta_{jm}-\delta_{jl}\delta_{im})\nabla_ja_lb_m \\
&=\nabla_ja_ic_j-\nabla_ja_jc_i \\
&=[(\nabla\cdot\vec c)\vec a+(\vec c\cdot\nabla)\vec a-(\nabla\cdot\vec a)\vec c-(\vec a\cdot\nabla)\vec c]_i. \\
\end{split}
$$
Think about $\nabla\vec a$, which is a matrix (acturally tensor). When dotted with another vector, it is simply done by simple linear algebra. Therefore,
$$
\begin{split}
\nabla\times\vec v&=\nabla\times(\vec\omega\times\vec r) \\
&=(\nabla\cdot\vec r)\vec\omega+(\vec r\cdot\nabla)\vec \omega-(\nabla\cdot\vec \omega)\vec r-(\vec\omega\cdot\nabla)\vec r \\
&=3\vec \omega+0-0-\vec \omega \\
&=2\vec\omega.
\end{split}
$$
In which we have used the fact that $\nabla\cdot r=3$ and $(\vec \omega\cdot\nabla)\vec r=\vec \omega\cdot(\nabla\vec r)=\vec \omega$. 
### Sheet 0 Q10
The most important thing is to realise $\nabla\cdot(\nabla\times \vec A)=0$. 

Proof:
$$
\begin{split}
[\nabla\cdot(\nabla\times\vec A)]_i&=\nabla_i(\nabla\times\vec A)_i \\
&=\nabla_i\epsilon_{ijk}\nabla_j A_k \\
&=\epsilon_{ijk}\nabla_i\nabla_j A_k \\
&=0,
\end{split}
$$
because 
$$
\frac{\partial^2}{\partial x\partial y}A_z=\frac{\partial^2}{\partial y\partial x}A_z.
$$

### Extra things
Going from Fourier series to Fourier transform, what we did is just rotate the basis by 45 degrees in complex plane,
$$
(\cos\theta,\sin\theta)\rightarrow\frac{1}{\sqrt{2}}(\cos\theta+\mathrm i\sin\theta,\cos\theta-\mathrm i\sin\theta)=\frac{1}{\sqrt 2}\left(\mathrm e^{\mathrm i\theta},\mathrm e^{-\mathrm i\theta}\right)
$$
and turn the sum into an integral by taking the limit
$$
L\rightarrow 0\quad\Leftrightarrow\quad\frac{2\pi}{L}\rightarrow\infty.
$$

Another definition of the Kronecker delta is $\sum_j\delta_{ij}a_j=a_i$. Turning into an integral, we get the definition of the Dirac delta function,
$$
\int_{-\infty}^{\infty}f(x)\delta(x-x_0)\ \mathrm d x=f(x_0).
$$
Convolution, in a very similar form, can be built by writing $g(x-y)$ as a linear superposition of delta functions. For example, In materials science, the crystal is convolution of motif. 

Compare with the inverse Fourier transform, we can see that we are expressing the same thing using different sets of basis. 
$$
\begin{split}
f(x)&=\int_{-\infty}^{\infty}h(u)g(x-u)\ \mathrm du; \\
f(x)&=\int_{-\infty}^{\infty}\tilde f(k)\left(\mathrm e^{-\mathrm ikx}\right)^*\ \mathrm dk.
\end{split}
$$

### Applications
Since $\mathrm e^{\mathrm i\phi}$ is always used as a phase shift term, we can easily understand why fraction forms are Fourier transforms of the aperture (seen by distant observers), and relate this with the reciprocal lattice in materials science. 

Also, to deal with the time-delay effect caused by boundary conditions (signals in different frequencies bounce at different angles and therefore drift at different speeds), the most useful way is to recover the original signal using convolutions. 

Finally, think about the boundary conditions in the Fourier, $x\rightarrow\infty$, $f(x)\rightarrow 0$. Due to this limitation, Fourier transform only gives us a solution to the ODE with certain boundary conditions. However, Laplace transform leads us to a finite boundary condition at infinity, which is therefore more helpful in certain cases. 

Complex impedance are the Fourier components. 

## Supervision Oct 24 2024
### Sheet 1 Q4
About symmetry, every function can be split into the even bit and the odd bit,
$$
f(x)=f_o(x)+f_e(x),
$$
and the Fourier transform becomes
$$
\begin{split}
\tilde f(k)&=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}f(x)\mathrm e^{\mathrm i kx}\ \mathrm dx \\
&=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}f_e(x)\cos(kx)\ \mathrm dx-\mathrm i\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}f_o(x)\sin(kx)\ \mathrm dx.
\end{split}
$$
This means, Fourier transform keeps even and real functions as even and real, and inverses odd and real functions to odd and minus imaginary. 

### Sheet 1 Q1
Questions can be done easier by choosing wisely between the two ways of integration, either integrate with $\exp(-\mathrm ikx)$ or split into even and odd functions using symmetries. 

### Sheet 1 Q2
Parseval's Theorem (one reminder):
$$
\int_{-\infty}^{\infty}\vert f(x)\vert^2\ \mathrm dx=\int_{-\infty}^{\infty}\vert\tilde f(k)\vert^2\ \mathrm dx.
$$

### Sheet 1 Q3
Indeed, $G(x)$ can be written, using the step functions $H(x)$, as
$$
\begin{split}
G(x)&=\int_{-\infty}^{\infty}g(x-\xi)g(\xi)\ \mathrm d\xi \\
&=\int_{-\infty}^{\infty}\left[H(x-\xi+\alpha)-H(x-\xi-\alpha)\right]\left[H(\xi+\alpha)-H(\xi-\alpha)\right]\ \mathrm d\xi \\
&=\begin{cases}
2\alpha-\vert x\vert \quad {\rm if\ }\vert x\vert\le 2\alpha \\
0\quad\quad\quad\quad {\rm otherwise}
\end{cases}
\end{split}
$$
Or, more clearly, write it piecewise!!!
$$
\begin{split}
G(x)&=\int_{-\infty}^{-\alpha}g(x-\xi)\times 0\ \mathrm d\xi+\int_{-\alpha}^{\alpha}g(x-\xi)\ \mathrm d\xi+\int_{\alpha}^{\infty}g(x-\xi)\times 0\ \mathrm d\xi \\
&=\int_{-\alpha}^{\alpha}g(x-\xi)\ \mathrm d\xi 
\end{split}
$$
Then we need to discuss the relations between $-\alpha$, $x-\xi$, and $\alpha$ because different relations will lead to different values of the integral. The result should be the same. 

How to explicitly show that $G$ and $g$ satisfies the convolution theorem? Since $G(x)$ is an even function, multiply by $\cos(kx)$ and integrate over all $x$, we can find (from integration by parts) that
$$
\tilde G(k)=\sqrt{2\pi}[\tilde g(k)]^2.
$$

### Sheet 1 Q5
Every time we use
$$
\mathcal F\left[\frac{\mathrm df}{\mathrm dx}\right]=\mathrm ik\mathcal F[f(x)],
$$
say to examiners that we have assumed $f(x)$ has the well-behaved boundary conditions: $f(x)\rightarrow 0$ as $\vert x\vert\rightarrow 0$. The reason is:
$$
\begin{split}
\int_{-\infty}^{\infty}\frac{\mathrm df}{\mathrm dx}\mathrm e^{-\mathrm ikx}\ \mathrm dx&=\int_{-\infty}^{\infty}\mathrm e^{-\mathrm ikx}\ \mathrm df \\
&=\left[f\mathrm e^{-\mathrm ikx}\right]_{-\infty}^{\infty}-\int_{-\infty}^{\infty}f(x)\ \mathrm d\mathrm e^{-\mathrm ikx} \\
&=\mathrm ik\int_{-\infty}^{\infty}f(x)\mathrm e^{-\mathrm ikx}\ \mathrm dx
\end{split}
$$

In real life, the wave functions have a more strict boundary conditions, because they are normalised, so that
$$
\int_{-\infty}^{\infty}\vert\psi(x)\vert^2\ \mathrm dx\quad {\rm is\ finite.}
$$

When we were dealing with complex impedance, what we are doing is to solve
$$
\left(L\frac{\mathrm d}{\mathrm dt}+R+\frac{1}{C}\int_t\mathrm d t\right)I=V,
$$
in the Fourier domain, it suddenly becomes
$$
\left(\mathrm i\omega L+R+\frac{1}{\mathrm i\omega C}\right)\tilde I=\tilde V.
$$
For $I$ and $V$ with only one frequency, we have no problem doing the inverse transform and say
$$
I=\frac{V}{\mathrm i\omega L+R+\frac{1}{\mathrm i\omega C}},
$$
but if the frequency is a spectrum, the inverse transform is not that easy. 

### Sheet 1 Q6
Never write $x_i^2$ in suffix notations, write $x_i x_i$ instead - Do NOT mislead yourself! For example in Majorana theory we will often see $\sigma^2$, but it is a single (the second) Pauli matrix, instead of something squared. 

Part (d):
$$
\begin{split}
\epsilon_{kij}A_{ij}&=\epsilon_{kij}\epsilon_{ijm}a_m \\
&=\epsilon_{ijk}\epsilon_{ijm}a_m \\
&=(\delta_{jj}\delta_{km}-\delta_{jk}\delta_{jm})a_m \\
&=2\delta_{km}a_m \\
&=2a_k.
\end{split}
$$
Part (e): If $s_{ij}=s_{ji}$, 
$$
\epsilon_{ijk}s_{ij}=-\epsilon_{jik}s_{ji}=-\epsilon_{ijk}s_{ij}.
$$
If $\epsilon_{ijk}s_{ij}=0$, then 
$$
\epsilon_{klm}\epsilon_{ijk}s_{ij}=(\delta_{li}\delta_{mj}-\delta_{lj}\delta_{mi})s_{ij}=s_{lm}-s_{ml}=s_{ij}-s_{ji}=0
$$
By now the prove is complete. 

Part (f):
$$
\begin{split}
N_{ij}M_{jk}&=(\delta_{ij}-\epsilon_{ijm}n_m+n_in_j)(\delta_{jk}+\epsilon_{jkl}n_l) \\
&=\delta_{ij}\delta_{jk}+\delta_{ij}\epsilon_{jkl}n_l-\epsilon_{ijm}n_m\delta_{jk}-\epsilon_{ijm}\epsilon_{jkl}n_mn_l+n_in_j\delta_{jk}+\epsilon_{jkl}n_in_jn_l \\
&=\delta_{ik}+\epsilon_{ikl}n_l-\epsilon_{ikm}n_m-(\delta_{mk}\delta_{il}-\delta_{ml}\delta_{ik})n_mn_l+n_in_k+n_i\epsilon_{klj}n_ln_j \\
&=\delta_{ik}-n_in_k+n_ln_l\delta_{ik}+n_in_k+n_i(\vec n\times\vec n)_k \\
&=2\delta_{ik}
\end{split}
$$

### Experimental methods Q2
The phase images are created by the following process:
+ We measured a phase difference of $\pi/8$, 
+ Is it really $\pi/8$? Can it be $(2n+1/8)\pi$? Yes!
+ Therefore we have a series of spectrums in the same shape. 
+ Also, physical quantities must be real in the time domain, which means its Fourier domain is a even function.
+ That's where the mirror image comes from - the array of mirror images. 

### Experimental methods Q3(d)
The first op-amp is a oscillator whose input is sign wave and output is square wave - this is a digitiser used in computers, for example, $-15\ {\rm V}$ for $0$ and $15\ {\rm V}$ for $1$. 

The second one filters out DC current, but not perfectly if negative feedback is applied. It is an integrator in the Fourier domain, but only at higher frequencies. It is analogue instead of digital, which means, computers built from it has high error. 

### On vector calculus
Definition of div and curl is done by integrals, not $\nabla\cdot$ and $\nabla\times$. These operations are mappings of mappings. (This was discussed in detail during the next supervision.)

## Supervision Oct 31 2024
### Sheet 1 Q7
Nothing to worry about, note that when constructing the closed surface, mention the convention that $\mathrm d\vec S$ points outwards form the surface. 

### Sheet 1 Q8
Given that $\vec F=\vec ap$, where $\vec a$ is an arbitrary vector, it is easy to show that
$$
\begin{split}
\int_V(\nabla\cdot\vec F)\ \mathrm dV&=\int_{\partial V}\vec F\cdot\mathrm d\vec S \\
\int_V(\nabla\cdot\vec ap)\ \mathrm dV&=\int_{\partial V}\vec ap\cdot\mathrm d\vec S \\
\int_V(\nabla p\cdot\vec a)\ \mathrm dV+\int_V(p\nabla\cdot\vec a)\ \mathrm dV&=\int_{\partial V}\vec ap\cdot\mathrm d\vec S
\end{split}
$$
If $\vec a$ is a vector field that is divergence free, the second term at the LHS vanishes,
$$
\int_V\vec a\cdot(\nabla p)\ \mathrm dV=\oint_{\partial V}p\vec a\cdot\mathrm d\vec S,
$$
and conclude that
$$
\int_{\rm whatever} \vec a\cdot(\nabla p\ \mathrm dV-p\ \mathrm d\vec S) = 0.
$$
From this we can claim that
$$
\int_V\nabla p\ \mathrm dV=\oint_{\partial V}p\ \mathrm d\vec S
$$
because $\vec a$ is an arbitrary vector, not anything else. This is the scalar form of the divergence theorem. 

### Sheet 1 Q9
The reason of getting $0$ from one method and $\mu_0 I$ from the other is that the function is not differentiable everywhere in the disk. What we are doing when integrating over the edge of the disk is unconsciously diving into the disk and excluding the pole at the centre. 

To figure out if the (arbitrary $n$-dimensional) volume contains poles, think about if we can shrink an arbitrary closed surface to zero without leaving the domain (volume). 

Recall the [little circle and big circle](https://en.wikipedia.org/wiki/Zeros_and_poles) theorems in complex analysis. 

### Sheet 1 Q10
A frame-free definition of grad is
$$
\mathrm df=\mathrm d\vec l\cdot\nabla f.
$$
That's from factorisation
$$
\begin{split}
\mathrm df&=\frac{\partial f}{\partial x}\mathrm dx+\frac{\partial f}{\partial y}\mathrm y \\
&=\left(\hat e_x\mathrm dx+\hat e_y\mathrm dy\right)\left(\hat e_x\frac{\partial f}{\partial x}+\hat e_y\frac{\partial f}{\partial y}\right) \\
&=\mathrm d\vec l\cdot\nabla f.
\end{split}
$$
Similarly, in polar coordinates, the factorisation turns to
$$
\mathrm df=\left(\hat e_r\mathrm dr+r\hat e_\theta\mathrm d\theta\right)\left(\frac{\partial f}{\partial r}\hat e_r+\frac{1}{r}\frac{\partial f}{\partial \theta}\hat e_\theta\right),
$$
the extra $r$ term is there to make the first term $\mathrm dl$. In this way the geometric scale factor of $\theta$ and $\phi$ terms in polar coordinates can be explained. 

Doing the same thing to divergence, remember that it is defined to make divergence theorem work,
$$
{\rm div}\ \vec F=\lim_{\Delta V\rightarrow 0}\frac{1}{\Delta V}\oint_{\partial V}\vec F\cdot\mathrm d\vec S.
$$
Suppose we have a "small cube" in some coordinate system with dimensions $h_i\mathrm dq_i$, the integral over the surface should be
$$
\begin{split}
{\rm div}\ \vec F&=\frac{1}{\Delta V}\oint_{\partial V}\vec F\cdot\mathrm d\vec S=\frac{\partial F_jh_ih_k}{\partial q_j}\mathrm dq_i\mathrm dq_j\times\frac{1}{h_i\mathrm dq_ih_j\mathrm dq_jh_k\mathrm dq_k} \\
&=\frac{1}{h_ih_jh_k}\frac{\partial F_ih_jh_k}{\partial q_i}.
\end{split}
$$

Similarly, curl is defined to make the Stokes's theorem work. 
$$
{\rm curl}\ \vec F=\lim_{\Delta S\rightarrow 0}\frac{\hat n}{\Delta S}\oint_{\partial S}\vec F\cdot\mathrm d\vec l.
$$
Suppose we have a small "square" in some coordinate system with dimensions $h_i\mathrm dq_i$, the integral over the boundary is
$$
\begin{split}
{\rm curl}\ \vec F&=\frac{\hat n}{\Delta S}\oint_{\partial S}\vec F\cdot\mathrm d\vec l=\frac{\hat e_k}{h_ih_j}\left(\frac{\partial F_jh_j}{\partial q_i}-\frac{\partial F_ih_i}{\partial q_j}\right) \\
&=\frac{1}{h_ih_jh_k}\begin{vmatrix}
h_i\hat e_i & h_j\hat e_j & h_k\hat e_k \\
\frac{\partial}{\partial q_i} & \frac{\partial}{\partial q_j} & \frac{\partial}{\partial q_k} \\
h_iF_i & h_jF_j & h_kF_k 
\end{vmatrix}
\end{split}
$$

The second part, just remember that
$$
\nabla^2\vec F=\nabla\cdot(\nabla\cdot \vec F)-\nabla\times(\nabla\times\vec F)
$$
holds frame-free. 

### Sheet 1 Q11
Something to be treated carefully. When writing out $\nabla^4\Psi$, we have
$$
\nabla^2(\nabla^2\Psi)=\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial}{\partial r}\left(\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)\right)\right)=0.
$$
Of course we can set $\Phi=\nabla^2\Psi$ and solve two Laplace equations, but it is not the easiest way. The easiest way to solve this questions is doing part by part, for example, multiply each side by $r$, we get
$$
\frac{\partial}{\partial r}\left(r\frac{\partial}{\partial r}\left(\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)\right)\right)=0.
$$
Then it is obvious that
$$
r\frac{\partial}{\partial r}\left(\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)\right)={\rm const},
$$
and
$$
\begin{split}
\frac{\partial}{\partial r}\left(\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)\right)&=\frac{A}{r}; \\
\frac{1}{r}\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)&=A\ln(r)+B; \\
\frac{\partial}{\partial r}\left(r\frac{\partial\Psi}{\partial r}\right)&=Ar\ln(r)+Br; \\
r\frac{\partial\Psi}{\partial r}&=Ar^2\ln(r)+Br^2+C; \\
\frac{\partial\Psi}{\partial r}&=Ar\ln(r)+Br+\frac{C}{r}; \\
\Psi&=Ar^2\ln(r)+Br^2+C\ln(r)+D.
\end{split}
$$
After this we plug in the boundary conditions. This is the easiest way of dealing with multiple $\nabla$s. 

### Sheet 1 Q12
The plane of constant $\phi$ is a **HALF** plane rotating around the $z$ axis. Remember to check that the three tangent vectors are linearly independent. 

Recall the [conformal map](https://en.wikipedia.org/wiki/Conformal_map). 

### On Green's functions
In linear algebra we have this:
$$
\begin{split}
b &= Mx \\
x&=M^{-1}b \\
x_i&=M^{-1}_{ij}b_j \\
MM^{-1}&=I \\
M_{ij}M^{-1}_{jk}&=\delta_{ik}.
\end{split}
$$
For functions and differential equations, it is the same:
$$
\begin{split}
\mathcal Ly&=f \\
y&=\mathcal L^{-1}f \\
y(x)&=\int_{\xi}\mathcal L^{-1}(x,\xi)f(\xi)\ \mathrm d\xi \\
{\rm set}\quad G(x,\xi)&=\mathcal L^{-1}(x,\xi) \\
\mathcal LG&=I \\
\mathcal LG(x,\xi) &=\delta(x-\xi).
\end{split}
$$
$\mathcal L$ can be any linear differential operators, such as 
$$
\mathcal L=\frac{\mathrm d^2}{\mathrm dx^2}-2\frac{\mathrm d}{\mathrm dx}+3.
$$
Therefore the Green function is simply the inverse derivative factor. It is linked to convolution because when you convolve with Green function in the Fourier domain, you are multiplying a delta function in the real domain. Convolution is the continuous form of matrix multiplication. 

Difference between matrix equations and differential equations is the boundary equations. $y = 0$ leads to $G = 0$, $y' = 0$ leads to $G' = 0$, why that?

## Supervision Nov 7 2024
### Sheet 2 Q1
Just note that $(r^\prime,\theta^\prime,\phi^\prime)$ is not a spherical polar coordinate system. So everything comes from the fact that $(x,y,z)$ is a Cartesian system. 

### Sheet 2 Q2
This is the inverse transform of Sheet 1 Q12. 

Note that the hyperboloids are only of one sheet instead of two sheets. (Half of the whole hyperboloids.) 

### Sheet 2 Q4
For part (b), to write it clearly, you must split the integral into two subdomains to make the substitution reversible. This is because of the absolute value $\vert x\vert$. 

### Sheet 2 Q5
Very interesting question, worth going through all the maths. 

When solving equations, denote the indefinite integral using only one index such as $\int_x$. Use boundary conditions of $z$ to find out the constants, then move to $y$. 

Since $y^{\prime\prime}+py^\prime+qy=f(x)$, if $f=z^\prime-az$, $z$ can be written as $z=y^\prime-by$, therefore
$$
z^\prime = y^{\prime\prime}-by^\prime,
$$
and $b-a=p$, $ab=-q$, so it is easy to write
$$
\begin{split}
a&=\frac{1}{2}\left(-p\mp\sqrt{p^2-4q}\right); \\
b&=\frac{1}{2}\left(-p\pm\sqrt{p^2-4q}\right).
\end{split}
$$
For the equation $z^\prime-az=f(x)$, the integrating factor is $\mathrm e^{-ax}$, 
$$
z=\mathrm e^{ax}\int_{x^\prime}f(x^\prime)\mathrm e^{-ax^\prime}\ \mathrm dx^\prime.
$$
We must now plug in initial conditions to solve the explicit $z$. Since $y(0)=y^\prime(0)=0$, we know that $z(0)=0$. Therefore the integral changes to
$$
z=\mathrm e^{ax}\int_{0}^{x}f(x^\prime)\mathrm e^{-ax^\prime}\ \mathrm dx^\prime.
$$

Use the same method (integration factor) to $y$, we get
$$
y = \mathrm e^{bx}\int_0^x\int_0^\eta f(\xi)\mathrm e^{-a\xi}\mathrm e^{(a-b)\eta}\ \mathrm d\xi\mathrm d\eta,
$$
where the integral from $0$ to $\eta$ was because $y(0)=0$. 

Draw the domain in the $(\eta, \xi)$ space and then change the order of integration. This is faster than doing integrate by parts. In the end we get
$$
y=\frac{1}{a-b}\int_0^x f(\xi)\left[\mathrm e^{a(x-\xi)}-\mathrm e^{b(x-\xi)}\right]\ \mathrm d\xi.
$$

Interpret the result: we have found the Green's function:
$$
G=\begin{cases}
\frac{1}{a-b}\left[\mathrm e^{a(x-\xi)}-\mathrm e^{b(x-\xi)}\right]\quad 0\le u\le x; \\
0\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\quad\ \ x\le u.
\end{cases}
$$
However, it is not always so easy to find Green's functions, we still need other methods that use Green's functions' properties. 

### Sheet 2 Q6
$y$ and $y^\prime$ is continuous because if they are not, $y^{\prime\prime}$ would be undefined. The discontinuity comes only from $y^{\prime\prime}$. 

### Sheet 2 Q7
The lecturer told us that wherever $y$ is known, $G$ is known to be zero; wherever $y^\prime$ is known, $G^\prime$ is known to be zero. Also, from $\mathcal LG=\delta(x-\xi)$ gives us 
$$
\begin{split}
G(\xi_-,\xi)&=G(\xi_+,\xi); \\
G^\prime(\xi_-,\xi)&=G^\prime(\xi_+,\xi)-1.
\end{split}
$$

However, this is only for second-order linear differential equations. 

For $n$-th order, $\mathcal Ly=f(x)$, 
$$
\mathcal D=\sum_{i=0}^n \left[p_i(x)\frac{\mathrm d^i}{\mathrm dx^i}\right],
$$
then $y$ must be $C^{(n-1)}$, otherwise $y^{(n)}$ would be undefined. Again, from $\mathcal LG=\delta(x-\xi)$, $G$ and its derivatives are continuous up to $G^{(n-2)}$, and $G^{(n-1)}$ has the unitary jump at $x=\xi$. The example is given in Q8(4) in the next supervision. 

About the "unitary" jump, it is only unitary if $p_n(x)=1$. But in practical applications, $p_n(x)$ can be any function of $x$, and the jump would become $1/p_n(\xi)$ at $x=\xi$. 

### On Method of Images
Electric potential satisfies the Poisson equation
$$
\nabla\cdot\vec E = \nabla^2\phi=\frac{\rho}{\epsilon_0}.
$$
We begin with the divergence theorem,
$$
	\int_V\nabla\cdot\vec A\ \mathrm dV = \int_{\partial V}\vec A\cdot\mathrm d\vec S.
$$
Let $\vec A=\phi\nabla\psi-\psi\nabla\phi$ and plug into the equation, 
$$
\int_V(\phi\nabla^2\psi-\psi\nabla^2\phi)\ \mathrm dV = \int_{\partial V}(\phi\nabla\psi-\psi\nabla\phi)\cdot\mathrm d\vec S,
$$
and regard $\nabla^2$ as the linear differential operator. The Green's function satisfies
$$
\nabla^2G(x,\xi)=\delta(x-\xi).
$$
Let $\psi=G$ in Green's second identity,
$$
\begin{split}
&\int_V\left[\phi(\vec{x^\prime})\delta(\vec x-\vec{x^\prime})-G(\vec x,\vec{x^\prime})\nabla^{\prime2}\phi(\vec{x^\prime})\right]\ \mathrm d^3\vec{x^\prime} \\
=& \int_{\partial V}\left[\phi(\vec{x^\prime})\nabla^\prime G(\vec x,\vec{x^\prime})-G(\vec x,\vec{x^\prime})\nabla^\prime\phi(\vec{x^\prime})\right]\cdot\mathrm d\vec S.
\end{split}
$$
Since the electric potential can be expressed by the integral $\int_V\phi(\vec{x^\prime})\delta(\vec x-\vec{x^\prime})\ \mathrm d^3\vec{x^\prime}$, $\phi(\vec x)$ can be written as
$$
\begin{split}
\phi(\vec x)=&-\int_VG(\vec x,\vec{x^\prime})\rho(\vec{x^\prime})\ \mathrm d^3\vec{x^\prime} \\
&+\int_{\partial V}\left[\phi(\vec{x^\prime})\nabla^\prime G(\vec x,\vec{x^\prime})-G(\vec x,\vec{x^\prime})\nabla^\prime\phi(\vec{x^\prime})\right]\cdot\mathrm d\vec S.
\end{split}
$$
This form expresses the well-known property of harmonic functions, that if the value or normal derivative is known on a bounding surface, then the value of the function inside the volume is known everywhere. 

## Supervision Nov 14 2024
This week's questions are all long and tedious. Parts of Q8 are all examples of solving linear ODE with Green's functions. 
### Sheet 2 Q8(1)
Solve 
$$
y^{\prime\prime}-y=x^2,\quad y(0)=y(1)=0
$$
using Green's function. 

Use $\sinh$ and $\cosh$ and express the Green's function as:
$$
G=\begin{cases}
A\sinh(x)+B\cosh(x)\quad 0\le x\le \xi\le 1 \\
C\sinh(x-1)+D\cosh(x-1)\quad 0\le\xi\le x\le 1
\end{cases}
$$
is more useful. Apply the boundary conditions, it is clear that
$$
B = D = 0.
$$
At $x=\xi$, $G$ must be continuous,
$$
A\sinh(\xi)=C\sinh(\xi-1),
$$
and $G^\prime$ has the unitary jump,
$$
C\cosh(\xi-1)-A\cos(\xi)=1.
$$
This gives us the complete Green's function (use trig identity when appropriate):
$$
G=\begin{cases}
\frac{\sinh (x)\sinh(\xi-1)}{\sinh (1)}\quad 0\le x\le \xi\le 1 \\
\frac{\sinh(\xi)\sinh(x-1)}{\sinh(1)}\quad 0\le\xi\le x\le 1
\end{cases}.
$$
Therefore the solution to the equation is
$$
\begin{split}
y(x)&=\int_0^x \xi^2\frac{\sinh(\xi)\sinh(x-1)}{\sinh(1)}\ \mathrm d\xi+\int_x^1 \xi^2\frac{\sinh(x)\sinh(\xi-1)}{\sinh(1)}\ \mathrm d\xi \\
&=\frac{3\sinh(x)+2\sinh(1-x)}{\sinh(1)}-2-x^2.
\end{split}
$$

### Q8(2)
Solve 
$$
y^{\prime\prime}+\omega^2 y=x,\quad y^\prime(0)=y(\pi/\omega)=0
$$
using Green's function. 

It is easy to write out the form of Green's function:
$$
G = \begin{cases}
A\sin\omega x+B\cos\omega x\quad 0\le x\le \xi\le \pi/\omega \\
C\sin\omega x+D\cos\omega x\quad 0\le \xi\le x\le \pi/\omega 
\end{cases}
$$
Apply the boundary conditions, it is easy to see that
$$
A = D = 0.
$$
At $x=\xi$, $G$ must be continuous, and $G^\prime$ has the unitary jump,
$$
\begin{split}
B\cos\omega\xi - C\sin\omega\xi &=0; \\
C\cos\omega\xi + B\sin\omega\xi &=\omega.
\end{split}
$$
The final form of $G$ is therefore
$$
G=\begin{cases}
\frac{1}{\omega}\sin\omega\xi\cos\omega x\quad 0\le x\le \xi \le \pi/\omega \\
\frac{1}{\omega}\sin\omega x\cos\omega\xi\quad 0\le\xi\le x\le \pi/\omega
\end{cases}.
$$
And $y$ is easily
$$
\begin{split}
y(x) &= \int_0^x\frac{\xi}{\omega}\cos\omega\xi\sin\omega x\ \mathrm d\xi+\int_x^{\pi/\omega}\frac{\xi}{\omega}\sin\omega\xi\cos\omega x\ \mathrm d\xi \\
&=\frac{1}{\omega^3}\left(\omega x-\pi\cos\omega x-\sin\omega x\right)
\end{split}
$$

### Q8(3)
Solve 
$$
y^{\prime\prime}+\alpha y^{\prime}=\mathrm e^{-\beta x},\quad x>0,\quad y(0)=y^\prime(0)=0
$$
using Green's function. 

The general solution to the homogeneous equations is $y=A\mathrm e^{-\alpha x}+B$, therefore
$$
G=\begin{cases}
A\mathrm e^{-\alpha x}+B\quad 0\le x\le \xi \\
C\mathrm e^{-\alpha x}+D\quad 0\le\xi\le x
\end{cases}.
$$
Apply boundary conditions and we get
$$
A\mathrm e^{-\alpha}+B=0,\quad -\alpha A\mathrm e^{-\alpha}+B=0,
$$
therefore $A=B=0$. Since Green's function is continuous at $x=\xi$ and $G^\prime$ has the unitary jump, we get
$$
C\mathrm e^{-\alpha\xi}+D=0,\quad -\alpha C\mathrm e^{-\alpha\xi}=1,
$$
which gives
$$
C=-\frac{\mathrm e^{\alpha\xi}}{\alpha},\quad D=\frac{1}{\alpha}.
$$
The Green's function is therefore
$$
G=\begin{cases}
0\quad 0\le x\le\xi \\
-\frac{1}{\alpha}\left[\mathrm e^{-\alpha(x-\xi)}-1\right]\quad 0\le\xi\le x
\end{cases}
$$
and the solution is
$$
\begin{split}
y(x)&=\int_0^x-\frac{\mathrm e^{-\beta \xi}}{\alpha}\left[\mathrm e^{-\alpha(x-\xi)}-1\right]\ \mathrm d\xi \\
&=\frac{\alpha\left(1-\mathrm e^{-\beta x}\right)-\beta\left(1-\mathrm e^{-\alpha x}\right)}{\alpha\beta(\alpha-\beta)}.
\end{split}
$$

### Q8(4)
Solve 
$$
\frac{\mathrm d^4y}{\mathrm dx^4}=f(x),\quad y(0)=y^\prime(0)=y^{\prime\prime}(0)=y^{\prime\prime\prime}(0)=0
$$
using Green's function. 

It is easy to find out that
$$
G=\begin{cases}
Ax^3+Bx^2+Cx+D \quad 0\le x\le \xi \\
Ex^3+Fx^2+Gx+H \quad 0\le \xi\le x 
\end{cases}.
$$
Note that we used another notation $G$ for a coefficient, but it should not cause any confusion. 

Apply the boundary conditions,
$$
\begin{split}
G(0)&=D=0; \\
G^\prime(0)&=C=0; \\
G^{\prime\prime}(0)&=2B =0; \\
G^{\prime\prime\prime}(0)&=6A=0, \\
\end{split}
$$
and apply the continuous condition of Green's function,
$$
\begin{split}
G(\xi)&=E\xi^3+F\xi^2+G\xi+H=0; \\
G^\prime(\xi)&=3E\xi^2+2F\xi+G=0; \\
G^{\prime\prime}(\xi)&=6E\xi+2F=0; \\
G^{\prime\prime\prime}(\xi)&=6E=1,
\end{split}
$$
we can easily get
$$
E=\frac{1}{6},\ F=-\frac{1}{2}\xi,\ G=\frac{1}{2}\xi^2,\ H=-\frac{1}{6}\xi^3.
$$
The final expression of $G$ is therefore
$$
G=\begin{cases}
0\quad 0\le x\le \xi \\
\frac{(x-\xi)^3}{3!}\quad 0\le \xi\le x
\end{cases}.
$$
And the final solution is
$$
y(x)=\int_0^x f(\xi)\frac{(x-\xi)^3}{3!}\ \mathrm d\xi.
$$

### Sheet 2 Q9 First Half
Find $y(x,t)$ if
$$
\frac{\partial^2 y}{\partial t^2}+2\mu\frac{\partial y}{\partial t}=c^2\frac{\partial^2 y}{\partial x^2},
$$
and $\mu=\pi c/L$, $y(x,0)=d\sin(\pi x/L)$ and $\dot y(x,0)=0$. 

Use the traditional way of separating variables, try $y=XT$, plug in and we get
$$
X\ddot T+2\mu x\dot T=c^2 X^{\prime\prime}T,\quad \frac{\ddot T+2\mu\dot T}{T}=c^2\frac{X^{\prime\prime}}{X}=c^2\alpha.
$$
$\alpha\in\mathbb C$ is an arbitrary complex number because $X$ and $T$ are totally independent. For the equation $X^{\prime\prime}=\alpha X$, try $x=\mathrm e^{\lambda x}$, obviously,
$$
X=\begin{cases}
A\mathrm e^{\sqrt\alpha x}+B\mathrm e^{-\sqrt\alpha x},\quad \alpha\ne 0 \\
ax+b,\quad \alpha=0
\end{cases}.
$$
Suppose this $X$ is $\mathcal X(x,\alpha)$, and we have a similar $T=\mathcal T(t,\alpha)$, the solution should be
$$
y(x,t)=\iint\mathcal X(x,\alpha)\mathcal T(t,\alpha)\ \mathrm d^2\alpha.
$$
To apply the boundary conditions, note that
$$
y(0,t)=\iint\mathcal X(0,\alpha)\mathcal T(t,\alpha)\ \mathrm d^2\alpha=0, 
$$
for any $t$, this must hold, therefore we are confident to say that $\mathcal X(0,\alpha)=0$. For the same reason, it is okay to say $\mathcal X(L,\alpha)=0$. 

If $\alpha=0$, it is easy to show (with the boundary conditions above) that $a=b=0$. When $\alpha\ne 0$, it is easy to show that $A+B=0$, and, $\alpha$ must be purely imaginary and equal to $(\mathrm in\pi/L)$. Combining the results so far, we could write
$$
y(x,t)=\sum_n A_n\sin\left(\frac{n\pi x}{L}\right)\mathcal T\left(t,-\frac{n^2\pi^2}{L^2}\right). 
$$
From here we see that for two zero boundaries, the solution must be trigs with certain wave numbers. 

The only thing left is to determine $\mathcal T$. 

$\mathcal T$ satisfies
$$
\ddot{\mathcal T}+2\mu\dot{\mathcal T}+n^2\mu^2\mathcal T=0,
$$
try $\mathcal T=\mathrm e^{\lambda t}$ and we have $\lambda=\mu(-1\pm\sqrt{1-n^2})$, and
$$
\mathcal T(t,n)=\begin{cases}
(A_1+B_1 t)\mathrm e^{-\mu t},\quad n=1 \\
\left(A_n\cos\omega_n t+B_n\sin\omega_n t\right)\mathrm e^{-\mu t},\quad n>1
\end{cases},\quad \omega_n=\mu\sqrt{n^2-1}.
$$
Therefore 
$$
\begin{split}
y(x,t)=&(A_1+B_1 t)\mathrm e^{-\mu t}\sin\left(\frac{\pi x}{L}\right)+ \\
&+\sum_{n=2}^\infty \left(A_n\cos\omega_n t+B_n\sin\omega_n t\right)\mathrm e^{-\mu t}\sin\left(\frac{n\pi x}{L}\right).
\end{split}
$$
Plug in the initial conditions $y(x,0)=d\sin(\pi x/L)$ and $\dot y(x,0)=0$, by orthogonal functions it is clear that all $n\ge 2$ terms vanish, and the answer is simply
$$
y=\left(1+\frac{\pi ct}{L}\right)\exp\left(-\frac{\pi ct}{L}\right)d\sin\left(\frac{\pi x}{L}\right).
$$

### Q9 Second Half
For the second part, as long as the coefficients are constants, the technique of finding the particular integral in ODEs still works. 

The equation has become
$$
\frac{\partial^2 y}{\partial t^2}+2\mu\frac{\partial y}{\partial t}=c^2\frac{\partial^2 y}{\partial x^2}+\frac{F}{\rho}\sin\left(\frac{\pi x}{L}\right)\cos\left(\frac{\pi ct}{L}\right).
$$
It is easy to see that, the $\partial_t^2 y$ term and $\partial_x^2 y$ term cancel out. The particular integral is easily written out as
$$
y(x,t)=\frac{FL^2}{2\rho\pi^2 c^2}\sin\left(\frac{\pi x}{L}\right)\sin\left(\frac{\pi ct}{L}\right).
$$

The next step, we need to add this to the GENERAL solution and re-impose the boundary conditions. That's partly why we need the general solutions in the first place. 

For this solution, $A_n=B_n=0$ for any $n\ge 2$ still holds, and the boundary conditions and one of the initial condition ($y(x,0)=d\sin(\pi x/L)$) is automatically satisfied. But the initial condition for velocity $\dot y(x,0)=0$ needs to be re-imposed. 
$$
\begin{split}
\dot y(x,0)&=\frac{\partial }{\partial t}\left[(d+B_1 t)\mathrm e^{-\mu t}\sin\left(\frac{\pi x}{L}\right)+\frac{FL^2}{2\rho\pi^2 c^2}\sin\left(\frac{\pi x}{L}\right)\sin\left(\frac{\pi ct}{L}\right)\right] \\
&=B_1\sin\left(\frac{\pi x}{L}\right)-\frac{\pi cd}{L}\sin\left(\frac{\pi x}{L}\right)+\frac{FL}{2\rho\pi c}\sin\left(\frac{\pi x}{L}\right) \\
&=0,
\end{split}
$$
therefore 
$$
B_1=\frac{\pi cd}{L}-\frac{FL^2}{2\rho\pi^2 c^2}\frac{\pi c}{L}.
$$
The final solution is (writing the first term as the homogeneous solution)
$$
\begin{split}
y(x,t)=&\left(1+\frac{\pi ct}{L}\right)\exp\left(-\frac{\pi ct}{L}\right)d\sin\left(\frac{\pi x}{L}\right)+ \\
&+\frac{FL^2}{2\rho\pi^2 c^2}\sin\left(\frac{\pi x}{L}\right)\left[\sin\left(\frac{\pi ct}{L}\right)-\frac{\pi c}{L}\exp\left(-\frac{\pi ct}{L}\right)\right].
\end{split}
$$

### Sheet 2 Q10
Solve $\nabla^2\Phi=0$ in the region $x\in[0,a]$, $y\in[0,b]$, $z\in[0,c]$, with $\Phi=1$ on $z=0$ and $\Phi=0$ on other surfaces. 

By simple separation of variable, we have $\Phi=XYZ$, $X$ and $Y$ obey homogenous boundary conditions, so we should deal with them and find their solutions first. 
$$
\frac{X^{\prime\prime}}{X}+\frac{Y^{\prime\prime}}{Y}+\frac{Z^{\prime\prime}}{Z}=0.
$$
Similar to Q9, it is easy to show that 
$$
X\propto \sin\left(\frac{n\pi x}{a}\right);\quad Y\propto\sin\left(\frac{m\pi y}{b}\right),
$$
therefore 
$$
\frac{Z^{\prime\prime}}{Z}=\frac{n^2\pi^2}{a^2}+\frac{m^2\pi^2}{b^2}=k^2>0,
$$
which means that (note that $\Phi(x,y,z=c)=0$)
$$
Z\propto\sinh[k(z-c)].
$$
Write out the general form of $\Phi$, 
$$
\Phi(x,y,z)=\sum_n\sum_m A_{mn}\sinh[k(z-c)]\sin\left(\frac{n\pi x}{a}\right)\sin\left(\frac{m\pi y}{b}\right).
$$
Now we want to apply the only remaining boundary condition, $\Phi(x,y,0)=1$. Express $\Phi(x,y,0)$ first:
$$
\Phi(x,y,0)=\sum_n\sum_m B_{mn}\sin\left(\frac{n\pi x}{a}\right)\sin\left(\frac{m\pi y}{b}\right)=1,
$$
where $B_{mn}=-A_{mn}\sinh(kc)$. 

Multiply each side by $\sin(p\pi x/a)$ and integrate. Do the same thing for $y$. 

From the LHS, we get
$$
\begin{split}
&\int_0^a\int_0^b\Phi(x,y,0)\sin\left(\frac{p\pi x}{a}\right)\sin\left(\frac{q\pi x}{b}\right)\ \mathrm dy\mathrm dx \\
=&\sum_n\sum_m B_{mn}\frac{a}{2}\delta_{np}\frac{b}{2}\delta_{mq} \\
=&\frac{ab}{4}B_{pq}.
\end{split}
$$
And from the RHS, we have
$$
\int_0^a\sin\left(\frac{p\pi x}{L}\right)\ \mathrm dx\int_0^b \sin\left(\frac{q\pi y}{b}\right)\ \mathrm dy=\begin{cases}
\frac{4ab}{pq\pi^2},\quad {\rm if\ }p,q{\rm \ both\ odd} \\
0,\quad {\rm otherwise}
\end{cases}.
$$
The two results should equal, therefore
$$
B_{mn}=-A_{mn}\sin(kc)=\frac{16}{mn\pi^2},\quad m,n{\rm\ both\ odd}.
$$
Rewrite $m$ and $n$ by the representation for odd numbers, $(2m-1)$ and $(2n-1)$. Now the solution is complete:
$$
\Phi(x,y,z)=\frac{16}{\pi^2}\sum_{n=1}^\infty\sum_{m=1}^\infty \frac{\sin\left[\frac{(2m-1)\pi x}{a}\right]\sin\left[\frac{(2n-1)\pi y}{b}\right]\sinh[k(c-z)]}{(2m-1)(2n-1)\sinh(kc)}.
$$

### Sheet 2 Q11
A fairly easy question. Solve
$$
\frac{\partial\theta}{\partial t}=\nu\frac{\partial^2 \theta}{\partial x^2},\quad \left(\frac{\partial \theta}{\partial x}\right)_{x=0,L}=0,\quad \theta(x,0)=2\theta_0\cos^2\left(\frac{\pi x}{L}\right).
$$

Suppose $\theta=XT+C$ because we only have homogenous boundary conditions for $\theta^\prime$, we have
$$
\frac{\dot T}{T}=\nu\frac{X^{\prime\prime}}{X}=-k,
$$
and we simply have 
$$
\begin{split}
T&=A\exp(-kt); \\
X&=B\cos\left(\sqrt{\frac{k}{\nu}}x+\phi\right).
\end{split}
$$
The general form of $\theta$ is
$$
\theta=\sum_k A_k\exp(-kt)\cos\left(\sqrt{\frac{k}{\nu}}x+\phi\right)+C,
$$
and the general form of $\theta^{\prime}$ is
$$
\theta^{\prime}=\sum_k \sqrt{\frac{k}{\nu}}\cdot A_k\exp(-kt)\sin\left(\sqrt{\frac{k}{\nu}}x+\phi\right).
$$
Apply the boundary conditions $\theta^\prime=0$ at $x=0$ and $L$, we have
$$
\sqrt{\frac{k}{\nu}}=\frac{n\pi}{L},\quad \phi=0.
$$
Therefore, plug in the initial condition, we get
$$
\theta(x,0)=C+\sum_n A_n\cos\left(\frac{n\pi x}{L}\right)=2\theta_0\cos^2\left(\frac{\pi x}{L}\right)
$$
It is easy to see (or using orthogonal conditions for functions) that
$$
C=\theta_0,\quad A_2=\theta_0,\quad A_n=0 {\rm\ for\ }n\ne 2.
$$
Therefore
$$
\theta(x,t)=\theta_0+\theta_0\cos\left(\frac{2\pi x}{L}\right)\exp\left(-\frac{4\pi^2\nu}{L^2}t\right). 
$$

## Supervision Nov 21 2024
### On dot products
Re-define dot product to return a scalar (number that doesn't change when changing perspective) instead of a number. For example, energy is a number because it depends on the reference frame. Now the dot product is
$$
\vec a\cdot\vec b = a_i^* b_i.
$$
To fully generalise dot product (to make a scalar out of vectors), we need to introduce a metric and write
$$
\vec a\cdot\vec b = g_{\mu\nu}a_\mu b_\nu.
$$
For more details, see differential geometry notes. 

From here it is helpful to be cautious of the order we are writing things, as tensors are not always commute. For example, if we define $\psi=\mathrm e^{\mathrm i\alpha} u$, the product of $\psi$ and $\psi^\dagger$ can only be written as
$$
\psi^\dagger\psi=u^\dagger \mathrm e^{-\mathrm i\alpha}\mathrm e^{\mathrm i\alpha}u=u^\dagger u.
$$
But not the other way around. 
### On Hermitian matrices
Eigenvalues are real, and eigenvectors for distinct eigenvalues are orthogonal. That means we can generate a (linearly independent and) orthogonal set of eigenvectors. 

### Sheet 3 Q2
Prove by induction: 

Base case with $\vec e_1$ and $\vec e_2$. If we choose $\vec e_1=u_1$ and 
$$
\vec e_2=\vec u_1-\frac{\vec e_1\cdot\vec u_1}{\vec e_1\cdot\vec e_1}\vec e_1
$$
it is easy to verify that
$$
\vec e_1\cdot\vec e_2=\vec e_1\cdot\vec u_1-\frac{\vec e_1\cdot\vec u_1}{\vec e_1\cdot\vec e_1}\vec e_1\cdot\vec e_1 = 0.
$$

Next, we take the induction step from $\vec e_n$ to $\vec e_{n+1}$. Suppose $\vec e_i,\ i\in[1,n+1]$ are defined by
$$
\vec e_i=u_i-\sum_{j=1}^{i-1}\frac{\vec e_j\cdot\vec u_i}{\vec e_j\cdot\vec e_j}\vec e_j,
$$
and for $i\in[1,n]$ the vectors are orthogonal to each other, it is easy to verify that for any $p\in[1,n]$, 
$$
\begin{split}
\vec e_{p}\cdot\vec e_{n+1}&=\vec e_{p}\cdot\vec u_{n+1}-\sum_{j=1}^{n}\frac{\vec e_j\cdot\vec u_{n+1}}{\vec e_j\cdot\vec e_j}\vec e_{p}\cdot\vec e_j \\
&=\vec e_p\cdot\vec u_{n+1}-\frac{\vec e_p\cdot\vec u_{n+1}}{\vec e_p\cdot\vec e_p}\vec e_p\cdot\vec e_p \\
&=0.
\end{split}
$$

Note that, here we are not normalising the basis for computing convenience. For example, $(\sqrt 2)^2$ in computers is something like ```2.0000000034``` depends on data type (```float64``` for example)

### Sheet 3 Q3
The proof is easy to complete, take $P_i=(A-\lambda_i I)$ where $\lambda_i$ is the $i$-th eigenvalue of the matrix $A$. Suppose the eigenvectors are linearly dependent, which means the following equation holds:
$$
Q=\sum_{i=1}^N\alpha_ie_i=0.
$$
For $i\in[1,n]$,
$$
\begin{split}
\left(\prod_{i\ne j}P_i\right)Q=\left[\prod_{i\ne j}(\lambda_j-\lambda_i)\right]Q&=0, \\
\Rightarrow\quad \left[\prod_{i\ne j}(\lambda_j-\lambda_i)\right]\alpha_je_j&=0.
\end{split}
$$
Since all eigenvalues are distinct (no degeneracy), the only possibility here is $\alpha_j=0$. 

### Sheet 3 Q4
Useful when calculating generalised Pauli matrices. 

Construct unitary matrix: take a number of perpendicular vectors of unit length and combine them. 


### Sheet 3 Q5
Hermitian conjugate is defined by $\langle a\vert Ab\rangle=\langle aA^\dagger\vert b\rangle$. It just turns out to be the conjugate of transpose. 

### Sheet 3 Q7
Rotate matrices in the same way the **preserves the relative angle** of vectors in order to preserve the scalar produced by dotting vectors. Therefore if $x^\prime = Rx$, $M^{\prime}$ for $x^\prime$ is $RMR^{-1}$. 

Another way to prove this, start by $(Mx)^\prime=M^{\prime}x^\prime$, we have:
$$
\begin{split}
RMx&=M^\prime Rx \\
RMR^{-1}&=M^\prime RR^{-1}=M^\prime I=M^\prime.
\end{split}
$$

Diagonalisation is changing the perspective that rotates the axis to match the eigenvalues. 

### Sheet 3 Q8
This is a simplified form of infinitesimal continuous Lorentz transformation in QFT. An infinitesimal Lorentz transformation can then be written as
$$
\Phi\rightarrow (1-\mathrm i\vec\theta\cdot\vec L-\mathrm i\vec\beta\cdot\vec K)\Phi.
$$
If $U$ is defined by an infinitesimal boost plus an infinitesimal rotation, then a rotation and a backward boost, the result is clearly unitary. 

### Further
Prove (by definition) that Hermitian matrices have real eigenvalues and anti-Hermitian matrices have purely imaginary eigenvalues. (Trivial.)

Prove that taking the Hermitian conjugate and taking the inverse are commutative actions. (Also trivial.)

### Sheet 3 Q9
We need to use the Hermitian conjugate because we have re-defined dot product! 

Rotation characterised by complex eigenvalues takes place in a plane spanned by the two eigenvector corresponding to the eigenvalue pairs. 

## Supervision Nov 28 2024
### About zeros, singularity, and poles
A zero is of order $n$ if
$$
0=f(z_0)=f^\prime(z_0)=\cdots,\ {\rm but\ }f^{(n)}(z_0)\ne 0.
$$
If $f(z)$ is analytic in an annulus $a < |z - z_0| < b$ for some $a$, $b$ (regardless of whether $f$ is analytic at $z_0$ itself) then $f$ has a unique Laurent expansion
$$
f(z)=\sum_{n=-\infty}^{\infty}a_n(z-z_0)^n.
$$
Essential singularity: If there is no integer $N$ such that $a_n=0$ for all $n<-N$, i.e., if however far $n$ goes towards $-\infty$ there are always some non-zero $a_n$'s, then $f$ is said to have an essential isolated singularity at $z_0$. For example, consider how $\mathrm e^{1/r}$, $r\in\mathbb C$ behave when $r$ approaches to zero ([Picard theorem](https://en.wikipedia.org/wiki/Picard_theorem)). 

If $a_n = 0$ for all $n < -N$ (where $N\in\mathbb N_+$ is a specific number) but $a_{-N} \ne 0$, then $f$ is said to have a pole of order $N$. 

It is important to be able to calculate the coefficient $a_{-1}$ of the Laurent expansion of a function $f(z)$ about a pole at $z_0$. This coefficient is called the residue of the pole, which we shall denote by ${\rm res}_{\substack{z=z_0}} f(z)$.
$$
a_{-1} = \lim_{z\rightarrow z_0}\left[\frac{1}{(N-1)!}\frac{\mathrm d^N}{\mathrm dz^{N-1}}\left((z-z_0)^N f(z)\right)\right].
$$
These knowledge will further be discussed when we encounter ODE again. 
### Sheet 3 Q10
Time-independent perturbation theory to the first order. 

The Hermitian matrix can be thought as our Hamiltonian and the eigenvalues are distinct energy of different eigenstates. The potential (as perturbation) is added to the original Hamiltonian as
$$
H=H_0+\lambda V
$$
where $\lambda$ is normally a small quantity. The Hamiltonian of a certain $\lambda$ acting on its own eigenstates becomes
$$
(H_0+\lambda V)\vert n\rangle = E_n^{(\lambda)}\vert n\rangle,
$$
where, to the first order, 
$$
\vert n\rangle = \vert n^{(0)}\rangle+\lambda\vert n^{(1)}\rangle.
$$
Suppose the energy shift for the $n$-th level is $\Delta_n=E_n-E_n^{(0)}$, we have
$$
\Delta_n = \langle n^{(0)}\vert\lambda V\vert n\rangle = \lambda\langle n^{(0)}\vert V\vert n\rangle.
$$
Therefore if we write
$$
\Delta_n = \lambda \Delta_n^{(1)},
$$
it is obvious to get $\Delta_n^{(0)} = 0$ and $\Delta_n^{(1)}=\langle n^{(0)}\vert V\vert n^{(0)}\rangle$. 

Consider two levels, $n$ and $k$, and note that $\langle k^{(0)}\vert n^{(0)}\rangle  = 0$, we have
$$
\begin{split}
\langle k^{(0)}\vert (H_0+\lambda V)\vert n\rangle&=\langle k^{(0)}\vert (E_n^{(0)}+\lambda\Delta_n^{(1)})(\vert n^{(0)}\rangle+\lambda\vert n^{(1)}\rangle \\
\lambda\langle k^{(0)}\vert V\vert n^{(0)}\rangle+\lambda\langle k^{(0)}\vert H_0\vert n^{(1)}\rangle&=\lambda E_n^{(0)}\langle k^{(0)}\vert n^{(1)}\rangle+\lambda\Delta_n^{(1)}\langle k^{(0)}\vert n^{(0)}\rangle\\
\langle k^{(0)}\vert V\vert n^{(0)}\rangle+ E_k^{(0)}\langle k^{(0)}\vert n^{(1)}\rangle&= E_n^{(0)}\langle k^{(0)}\vert n^{(1)}\rangle \\
\langle k^{(0)}\vert n^{(1)}\rangle &= \frac{\langle k^{(0)}\vert V\vert n^{(0)}\rangle}{E_n^{(0)}-E_k^{(0)}} \\
\vert k^{(0)}\rangle\langle k^{(0)}\vert n^{(1)}\rangle &= \frac{\vert k^{(0)}\rangle\langle k^{(0)}\vert V\vert n^{(0)}\rangle}{E_n^{(0)}-E_k^{(0)}} \\
\vert n^{(1)}\rangle &=\frac{\langle k^{(0)}\vert V\vert n^{(0)}\rangle}{E_n^{(0)}-E_k^{(0)}}\vert k^{(0)}\rangle. 
\end{split}
$$
No change in first order in the normal direction. 

For the complete analysis of perturbation theory (time-dependent and time-independent), refer to quantum mechanics notes. 

### Sheet 3 Q11
By finding the eigenvectors and the related quadratic surfaces, we are finding the contour surfaces for a random potential. 

Consider a well-behaved potential $V$ that can be expressed as
$$
\begin{split}
V =& V_0+\Delta x\frac{\partial V}{\partial x}+\Delta y\frac{\partial V}{\partial y}+ \\
&+\frac{(\Delta x)^2}{2!}\frac{\partial^2 V}{\partial x^2}+\frac{(\Delta y)^2}{2!}\frac{\partial^2 V}{\partial y^2}+\frac{2\Delta x\Delta y}{2!}\frac{\partial^2 V}{\partial x\partial y}.
\end{split}
$$
At its minimum/maximum/saddle points, $\partial V/\partial x = \partial V/\partial y = 0$, therefore the second-order perturbation terms can be expressed using the Hessian matrix as
$$
\Delta V = \frac{1}{2}\begin{pmatrix}
\Delta x & \Delta y
\end{pmatrix}
\begin{pmatrix}
\frac{\partial^2 V}{\partial x^2} & \frac{\partial^2 V}{\partial x\partial y} \\
\frac{\partial^2 V}{\partial x\partial y} & \frac{\partial^2 V}{\partial y^2}
\end{pmatrix}
\begin{pmatrix}
\Delta x \\
\Delta y
\end{pmatrix}.
$$
Of course, we can diagonalise the Hessian matrix by applying unitary operators constructed from its eigenvectors. 
$$
\Delta V = \frac{1}{2}\Delta x^\dagger H\Delta x = \frac{1}{2}(\Delta x^\dagger U^\dagger) (UHU^\dagger) (U\Delta x).
$$
The diagonalised matrix's non-zero elements are just the corresponding eigenvalues, $U^\dagger HU = {\rm diag}(\lambda_i)$. Therefore
$$
\Delta V = \frac{1}{2}\sum_i\lambda_i(U\Delta x_i)^2.
$$
In classical mechanics, each $\lambda$ is proportional to the angular frequency squared of that [normal mode](https://en.wikipedia.org/wiki/Normal_mode), and $(U\Delta x_i)$ is the related [generalised coordinate](https://en.wikipedia.org/wiki/Generalized_coordinates). 

In physical examples, the related quadratic planes are ellipsoids, and it is very interesting to consider them even in phase space. Landau's book gives some examples about this. 

### Sheet 4 Q2
There is a cleverer way to tackle part 2. 
$$
\ln(1-z)=-\sum_{n=1}^{\infty}\frac{z^n}{n}.
$$
Close to $\mathrm i$, suppose $z = \mathrm i+w$, $w\in\mathbb C$. 
$$
\begin{split}
\ln(1-(\mathrm i+w)) &= \ln(1-\mathrm i-w) \\
&=\ln\left((1-\mathrm i)\left(1-\frac{w}{1-\mathrm i}\right)\right) \\
&=\ln(1-\mathrm i)+\ln\left(1-\frac{w}{1-\mathrm i}\right).
\end{split}
$$
The second term:
$$
\ln\left(1-\frac{w}{1-\mathrm i}\right)=-\sum_{n=1}^{\infty}\left(\frac{w}{1-\mathrm i}\right)^n\frac{1}{n},
$$
apply the ratio test, it is easy to see that $R_w = \sqrt 2$. 

The radius of convergence is always the distance to the nearest pole in the complex plane. 

### Sheet 4 Q3
Cauchy-Riemann condition: if the function is differentiable, the derivative from any linearly independent direction must be the same at any point. If we choose the directions to be along the real and imaginary axes, we have
$$
\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y};\quad \frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x}.
$$
In another (and more useful) way, (since $z=x+\mathrm iy$ and $z^*$ is linearly independent) we can write the condition as
$$
\frac{\partial f}{\partial z^*}\Bigg\vert_z=0
$$
Therefore there must be no $z^*$ in analytic functions. 

This explains things like: $x^2-y^2-2\mathrm ixy$ always comes together for $z^2$, $\sin(x)\cosh(y)$ always comes together for $z$, etc. The tricky part is, if we get $x^2+y^2$ or $x-\mathrm iy$, it means we have something like $z^*/zz^*$, so there's effectively no $z^*$ in it. 

In the exams, it is often better to guess the complete function (up to a constant) and then show that it satisfies the given C-R condition using derivatives. This is much efficient than doing the integrals. 
### Sheet 4 Q4
Note the essential singularities. 
## Supervision Dec 5 2024
### Sheet 4 Q6 and others
All the questions follow the same route, therefore we shall discuss the general case here. 

The exact proof of the expansion? God knows! But "it can be shown that" any function $y(x)$ can be expressed as the following expansion:
$$
y = \sum_{n=0}^{\infty}a_n(x-x_0)^{n+\sigma},
$$
if $y$ is not infinity at $x_0$. Here $\sigma$ is a constant number from $-1$ to $+1$ that needs to be determined. 

When solving the ODE
$$
y^{\prime\prime}+p(x)y^{\prime}+q(x)y=f(x),
$$
we can write $y$ as the expansion, and calculate every $a_n$ using orthogonality. First write out $y$ and its derivatives,
$$
\begin{split}
y &= \sum_{n=0}^{\infty}a_n(x-x_0)^{n+\sigma}; \\
y^{\prime} &= \sum_{n=0}^{\infty}a_{n+1}(n+\sigma+1)(x-x_0)^{n+\sigma}; \\
y^{\prime\prime} &= \sum_{n=0}^{\infty}a_{n+2}(n+\sigma+1)(n+\sigma+2)(x-x_0)^{n+\sigma}.
\end{split}
$$
Note that we have re-indexed every line to make sure everything is a sum of $(x-x_0)^{n+\sigma}$ from $n=0$ to $\infty$. Since $p$ and $q$ are analytical functions of $x$, we can write them as
$$
p(x)=\sum_{n=0}^\infty p_nx^{n+\sigma};\quad q(x)=\sum_{n=0}^\infty q_nx^{n+\sigma}.
$$
Now we need to combine all sums together, note that for $r=n+m$,
$$
\sum_{n=0}^\infty\sum_{m=0}^{\infty} = \sum_{r=0}^{\infty}\sum_{m=0}^r. 
$$
Therefore,
$$
\sum_{r=0}^{\infty}\left((r+\sigma+2)(r+\sigma+1)a_{r+2}+\sum_{m=0}^r\left((m+\sigma+1)a_{m+1}p_{r-m}+a_m q_{r-m}\right)\right)x^{r+\sigma}=f_rx^{r+\sigma},
$$
where $\sum_r f_r x^{r+\sigma}=f(x)$. Now by orthogonality we can simply say that
$$
a_{r+2}=\frac{1}{(r+\sigma+2)(r+\sigma+1)}\left(f_r-\sum_{m=0}^{r}\left((m+1)a_{m+1}p_{r-m}+ a_m q_{r-m}\right)\right)
$$
for all $r\ge 0$. 

The above solution only gives us $a_n$ of $n\ge 2$, but not $a_0$ and $a_1$. We have to clarify that, without ortho generality, they are not zero. Therefore we still need boundary conditions to determine them. 

Also, note that by finding all $a_n$s, it only gives one solution, we need to find the other linearly independent one to obtain the general solution. 
### Finding the other solution
That's why we need to use the $W=y_1y_2^\prime-y_1^\prime y_2$ determinant. 
$$
\frac{\mathrm dW}{W}=-p\ \mathrm dx
$$
In this way we can find the other solution. 
$$
y_2(x)= y_1(x)\int^x\frac{W(\eta)}{y_1^2(\eta)}\ \mathrm d\eta=y_1(x)\int^x\frac{\kappa}{y_1^2(\eta)}\exp\left(-\int^\eta p(\zeta)\ \mathrm d\zeta\right)\ \mathrm d\eta,
$$
where $\kappa$ is a constant (a change in lower limit of integration can be absorbed by a rescaling of $\kappa$). 

Note that, if $y_1$ is expressed as power series, then $y_2$ must also be power series (expand $y_1$ in the equation above). The only way $y_2$ fails to be a power series is the $\ln$ term from the integration, which gives 
$$
y_2=y_1\ln x+{\rm the\ power\ series\ from\ integration}.
$$
### Other comments
The radius of convergence should be "No smaller than" the distance to the nearest pole here because we're finding the radius of $y$ but the poles are in $p$ and $q$. 

2006 paper Q6A and 8A (can't remember exactly) are examples of this. 

Regular singular points: a singular point $z=z_0$ is regular if $(z-z_0)p(z)$ and $(z-z_0)^2q(z)$ are both analytic at $z=z_0$. Fuchs's theorem tells us there's at least one solution of the form
$$
y=z^\sigma\sum_{n=0}^\infty a_nz^n,\quad a_0\ne 0,\ \sigma\in\mathbb C.
$$
We can move straightaway to the $W$ determinant after determining all $a_n$. Frobenius's method is used to find the series solutions about a regular singular point. 