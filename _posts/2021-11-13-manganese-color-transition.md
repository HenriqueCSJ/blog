---
title: "Why is manganese(II) coloured although the transition should be spin-forbidden?"
mathjax: true
categories:
  - Quantum Mechanics
  - Notekeeping
tags:
  - spin-orbit coupling
  - laporte rule
  - transition state
  - spin admixture
  - manganese(II)
---

### Selection rules

The intensity of the transition from a state $\mathrm{i}$ to a state $\mathrm{f}$ is governed by the transition dipole moment $\mu_{\mathrm{fi}}$ (strictly, it is proportional to $|\mu_{\mathrm{fi}}|^2$):

$$
\iint \Psi_\mathrm{f}^*\hat{\mu}\Psi_\mathrm{i}\,\mathrm{d}\tau \,\mathrm{d}\omega \tag{1}
$$

where $\mathrm{d}\tau$ is the usual volume element (representing integration over spatial coordinates) and $\omega$ is an additional spin coordinate (since the states $\Psi$ also specify the spin). For an electronic transition, $\hat{\mu}$ is the electric dipole moment operator, and only depends on the spatial coordinates $x$, $y$, and $z$. (I've also ignored the vibrational component i.e. the Franck-Condon factor since it's not really relevant for the purposes of this answer.)

Normally in determining selection rules, we are more interested in whether the integral in $(1)$ is zero or not. If the integral is zero, the transition is said to be forbidden. The usual way to determine whether it is zero is by using symmetry: if the *integrand* is antisymmetric under any symmetry operation, then the *integral* is zero. (It is exactly analogous to the integral of an odd function $f(x)$ over a symmetric region; for example, $\int_{-a}^a \sin x \,\mathrm{d}x = 0$.)

If we assume that both the initial and final states can be separated into spin and spatial components, then we get:

$$
\iint (\psi_\mathrm{f}^\mathrm{spin}\psi_\mathrm{f}^\mathrm{space})\hat{\mu}(\psi_\mathrm{i}^\mathrm{spin}\psi_\mathrm{i}^\mathrm{space})\,\mathrm{d}\tau\,\mathrm{d}\omega
$$

(I also dropped the complex conjugates - they aren't important.) Since $\hat{\mu}$ does not operate on the spin coordinate, we can separate this multiple integral:

$$
\left(\int \psi_\mathrm{f}^\mathrm{spin} \psi_\mathrm{i}^\mathrm{spin} \,\mathrm{d}\omega\right) \left(\int \psi_\mathrm{f}^\mathrm{space} \hat{\mu} \psi_\mathrm{i}^\mathrm{space} \,\mathrm{d}\tau\right)
$$

The first integral is nonzero if $\Delta S = 0$. The quantum number $S$ is related to the eigenvalue of a hermitian operator (the actual eigenvalue is $S(S+1)\hbar^2$), and eigenfunctions of a hermitian operator corresponding to different eigenvalues are necessarily orthogonal, making the integral identically zero if $\Delta S \neq 0$. This is the spin selection rule.

The second integral is nonzero if $\psi_\mathrm{f}^\mathrm{space}$ and $\psi_\mathrm{i}^\mathrm{space}$ have a different character under the inversion operation, i.e. one is gerade and another is ungerade. This is because $\hat{\mu}$ itself is ungerade, so for the integrand to be gerade, we need $\psi_\mathrm{f}^\mathrm{space}\psi_\mathrm{i}^\mathrm{space}$ to be ungerade ($\mathrm{u \otimes u = g}$). In turn this means that $\psi_\mathrm{f}^\mathrm{space}$ and $\psi_\mathrm{i}^\mathrm{space}$ must have different symmetry. This is the Laporte selection rule. It can be relaxed when the geometry is not perfectly octahedral, or tetrahedral for that matter, since inversion is no longer a symmetry operation. However, I digress.

---

### Spin-orbit coupling

The problems arise because the total states are not separable into spin and spatial components. This occurs because both electron spin, as well as orbital angular momentum, are both angular momenta. They therefore interact with each other, and this is the spin-orbit coupling spoken of. Mathematically, it is treated as a perturbation to the Hamiltonian; the result is that the transition dipole moment cannot be separated into two integrals and this leads to the invalidation of the selection rules.

When considering spin-orbit coupling, the term symbols such as $^3\!F$, $^1\!D$, which imply a simultaneous eigenstate of the total spin operator $\hat{S}$ and the total orbital angular momentum operator $\hat{L}$ are no longer meaningful since both angular momenta are coupled to each other (by $\vec{j} = \vec{l} + \vec{s}$) and behave as one "combined" source of angular momentum. The quantities $S$ and $L$ are called "nearly good" quantum numbers: they are no longer strictly conserved, but the "contamination" of different quantum numbers is relatively small. Mathematically we could express this as an admixture of different spin states into the original wavefunction:

$$
^3\!F_J = c(^3\!F) + c_1(^1\!F) + \cdots
$$

where $^3\!F_J$ denotes a state with spin-orbit coupling (not an eigenstate of $\hat{S}$ and $\hat{L}$), and $(^3\!F)$ denotes the original $^3\!F$ state before spin-orbit coupling is considered (which is a true eigenstate of $\hat{S}$ and $\hat{L}$). If $c_i \neq 0$, then one obtains a non-zero transition dipole moment between "states" of nominally different $S$.

The fact that the selection rules are still a thing is solely because spin-orbit coupling is a small effect ($c_i$ close to 0), so the compounds behave "almost" as if they obey the selection rules. More properly, the transition dipole moment between states of different $S$ is small, and therefore the d-d bands in $\mathrm{d^5}$ spectra are extremely weak. The magnitude of spin-orbit coupling, however, does vary with $Z^4$ ($Z$ being the atomic number). Therefore, while spin-orbit coupling is rather small in the 3d series, it becomes an extremely important mechanism by which the spin selection rule in the the 4d and 5d congeners, as well as the f-block elements, is relaxed.

---

To continue with the answer from @orthocresol. The breaking of formally ‘ forbidden’ transitions is very common indeed, possibly the best example is in the observation of phosphorescence from almost any aromatic or dye molecule.

Absorption in these molecules is generally a spin allowed transition, (single to singlet), however, triplet states, from which phosphorescence is observed, can only be produced by a spin forbidden process, (singlet to triplet inter system crossing) and just as in the case of phosphorescence this is a spin forbidden process which becomes allowed due to spin-orbit coupling. In the case of the manganese ions and in other transition metals the forbidden transition is in absorption.

The treatment is the same in all cases and starts with allowing the two states to interact via some operator. In the case of photons (absorption / emission) it is an electric dipole operator, i.e. dipole moment operator. Labelling the operator as $ H_0$, the rate of the transition from one state to another is

$$
W_{if} \approx \int \Psi_f H_0 \Psi_i d\tau = \int \psi_f\sigma_f H_0 \psi_i \sigma_i d\tau
$$

where $\sigma$ represents the spin wavefunction and $\psi$ the spatial one for initial (*i*) and final (*f*) states. As the operator does not depend on spin the integral can be separated into two parts as described in other answers

$$
\int \psi_f\sigma_f H_0 \psi_i \sigma_i d\tau = \int \psi_f H_0 \psi _i d\tau\int\sigma _f \sigma_i d\tau = 0
$$

and the final result is zero because the spin wavefunctions are orthogonal making the last integral is zero between states with different spin, i.e. $\Delta S \ne\ 0$. This is what we expect from states between which a spin changing transition is attempted.

To progress we next suppose that it is possible to mix a little of the final state wavefunction into the initial one and thus generate a new state with wavefunction $\psi_m$ then

$$
\psi_m=\psi_f + b\psi_i
$$

where *b* is some mixing constant we can determine later on.

Now replacing the wavefunction for the final state ($\psi _f$) with this one ($\psi_m$) and repeating the calculation above and separating out terms as before, as orthogonal spin terms are zero, also as before, this leads to

$$
W_{if} \approx \int \psi_m H_0 \psi_i d\tau = b\int \psi_i \sigma_i H_0 \psi_i \sigma _i d\tau = b\int \psi_i  H_0 \psi_i  d\tau\int\sigma _i\sigma_id\tau
$$

in which case neither of the integrals is zero but evaluates to a number. This equation shows that there is a finite rate for the process with operator $H_0$, for example the electric dipole operator.

The constant *b* remains to be understood and it is derived using perturbation theory and turns out to have the form

$$
b=\frac{\int\psi _f \Omega \psi _i d\tau}{E_f-E_i}
$$

where $\Omega$ is the spin-orbit operator. Thus the rate for the process finally becomes

$$
w \approx \frac{\int\psi _f \Omega \psi _i d\tau}{E_f-E_i}
$$

and we can use symmetry to decide if this integral is zero or is finite.

In the case in point, the spin-orbit coupling the operator depends on the mass of the atoms involved and the product of orbital and spin angular momentum. This is why spin-orbit coupling is also called a ‘heavy atom effect’ when applied to emission processes. In general, however, any effects are enhanced in atoms with larger atomic numbers compared to those earlier in the periodic table, simply because $\Omega $ is larger in value. It is clear also that if the two states are close in energy the effect is also increased relative to atoms /molecules where the states are further separated in energy.

The second mechanism by which a 'forbidden' transition can become somewhat allowed is by 'Herzberg-Teller' coupling also called 'intensity stealing'. The standard example is in benzene where the $S_0 \rightarrow S_1$ transition is forbidden but is observed as a weak absorbtion due to a vibrational normal mode altering the symmetry of the electronic excited state so that it now has the correct symmetry to couple with a second and higher allowed electronic transition, and thus 'steal' intensity. The formalism is essentially the same as described. The terms that are important are thus (a) the presence of a normal mode of the correct symmetry (b) a second and allowed transition, preferably close by in energy and (c) an electronic coupling term between the allowed transition and the forbidden transition whose symmetry is altered by the vibrational normal mode.