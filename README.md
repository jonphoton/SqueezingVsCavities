# Squeezing vs. Cavities for Atom Detection: A Loss-Limited Equivalence

## Summary

When detecting a single atom via its interaction with light, both optical cavities and squeezed light enhance the measurement.  Perhaps surprisingly, they yield **exactly the same detection error per scattered photon** when limited by the same single-pass optical loss.  This is not a coincidence -- it reflects a deep equivalence in loss-limited quantum metrology.

## Setup: Dispersive Atom Detection

Consider a single atom probed by a paraxial beam of waist $w$, detuned by $\Delta$ from an atomic transition with linewidth $\Gamma$ and resonant cross section $\sigma_0 \sim \lambda^2$.

Each probe photon produces:

- **Dispersive phase shift:**
$$\phi \sim \frac{\sigma_0}{A}\frac{\Gamma}{2\Delta} \sim \frac{\lambda^2}{w^2}\frac{\Gamma}{\Delta}$$

- **Scattering probability (damage):**
$$\epsilon \sim \frac{\sigma_0}{A}\left(\frac{\Gamma}{2\Delta}\right)^2 \sim \frac{\lambda^2}{w^2}\left(\frac{\Gamma}{\Delta}\right)^2$$

where $A \sim w^2$ is the mode area.

## The Key Ratio: Information per Scattered Photon

The detection error for distinguishing atom-present from atom-absent scales as:

$$P_\mathrm{err} \sim \exp\!\left(-\frac{\phi^2}{\epsilon}\, N_\mathrm{sc}\right)$$

where $N_\mathrm{sc}$ is the total number of photons scattered by the atom.

**Why this form?**  For $N$ probe photons in a coherent state, the signal-to-noise ratio is $\mathrm{SNR}^2 = N\phi^2$.  The total scattering is $N_\mathrm{sc} = N\epsilon$.  Eliminating $N$:

$$\mathrm{SNR}^2 = \frac{\phi^2}{\epsilon}\,N_\mathrm{sc}$$

The ratio $\phi^2/\epsilon$ is the **information gained per scattered photon** -- the fundamental figure of merit.  Computing it:

$$\boxed{\frac{\phi^2}{\epsilon} \sim \frac{\lambda^2}{w^2}}$$

The detuning cancels entirely.  The information per scattered photon depends only on geometry: the ratio of the atomic cross section to the mode area.  This is the **free-space cooperativity** $C_\mathrm{fs}$.

## Cavity Enhancement

In an optical cavity with mirror transmission $T$:

- Each intracavity photon makes $\sim 1/T$ round trips
- Accumulated phase: $\Phi = \phi/T$ per input photon
- Accumulated scattering: $E = \epsilon/T$ per input photon
- $\mathrm{SNR}^2 = N(\phi/T)^2 = N\phi^2/T^2$
- $N_\mathrm{sc} = N\epsilon/T$, so $N = N_\mathrm{sc}\,T/\epsilon$
- $\mathrm{SNR}^2 = N_\mathrm{sc}\,\dfrac{\phi^2}{\epsilon}\,\dfrac{1}{T}$

The cavity provides an enhancement factor $L_\mathrm{cav} = 1/T$.  But intracavity loss bounds how small $T$ can usefully be -- once loss per round trip exceeds $T$, photons are absorbed instead of recycled.  So:

$$L_\mathrm{cav} \sim \frac{1}{\text{round-trip loss}}$$

## Squeezing Enhancement

With squeezed-vacuum input (squeezing parameter $r$), the phase measurement sensitivity improves:

$$\Delta\phi \sim \frac{e^{-r}}{\sqrt{N}}$$

This gives $\mathrm{SNR}^2 = N\phi^2 e^{2r}$, so:

$$\mathrm{SNR}^2 = N_\mathrm{sc}\,\frac{\phi^2}{\epsilon}\,e^{2r}$$

The squeezing enhancement is $L_\mathrm{sq} = e^{2r}$.  But optical loss destroys squeezing.  With transmission $\eta = 1 - \ell$, the squeezed quadrature variance becomes:

$$V_\mathrm{sq} = \eta\, e^{-2r} + (1-\eta)$$

For large $r$, this floors at $(1 - \eta) = \ell$.  The effective enhancement saturates:

$$L_\mathrm{sq} = \frac{1}{V_\mathrm{sq}} \;\xrightarrow{r\to\infty}\; \frac{1}{\ell}$$

## The Equivalence

Both strategies produce the same detection error:

$$P_\mathrm{err} \sim \exp\!\left(-\frac{\lambda^2}{w^2}\,\frac{1}{\mathcal{L}}\,N_\mathrm{sc}\right)$$

where $\mathcal{L}$ is the single-pass loss through the interaction region, which:

| | Mechanism | Enhancement | Loss-limited by |
|---|---|---|---|
| **Cavity** | Repeated photon--atom interaction | $1/T$ | Round-trip loss $\to L \sim 1/\mathcal{L}$ |
| **Squeezing** | Reduced phase noise via quantum correlations | $e^{2r}$ | Vacuum injection from loss $\to L \sim 1/\mathcal{L}$ |

Under the identification $T \leftrightarrow \ell$, the two strategies become **quantitatively identical** in information gained per scattered photon.

## Physical Interpretation

This equivalence is not accidental.  Both strategies solve the same problem -- extracting more information per probe photon -- subject to the same constraint: **loss randomizes the quantum state of the light**.

- In a cavity, loss destroys stored photons, limiting the effective number of passes.
- For squeezing, loss injects vacuum noise, destroying the quantum correlations that reduced measurement noise.

In both cases, the maximum usable enhancement is:

$$L_\mathrm{max} \sim \frac{1}{\text{single-pass loss}}$$

Both are implementations of the same underlying resource: **loss-limited phase sensitivity**.

## Generalization Beyond Dispersive Measurements

This result is not specific to dispersive (off-resonant) detection.  On resonance, the same scaling emerges.

The fundamental quantities are:

- **Signal amplitude** coupled into the detected mode: $s \sim \sigma_0/A \sim \lambda^2/w^2$
- **Scattering probability**: $\epsilon \sim \sigma_0/A \sim \lambda^2/w^2$

The ratio:

$$\frac{s^2}{\epsilon} \sim \frac{(\lambda^2/w^2)^2}{\lambda^2/w^2} = \frac{\lambda^2}{w^2}$$

is the same whether the signal is a phase shift (dispersive), extinction, or reflection contrast (resonant).

This follows from a general principle: the atom is a dipole scatterer with cross section $\sigma \sim \lambda^2$.  Of all the light it scatters into $4\pi$ steradians, only a fraction $\sim \lambda^2/w^2$ overlaps with the detected paraxial mode.  This **branching ratio** between coherent (useful) and incoherent (damaging) scattering is set by geometry alone.  Neither cavities nor squeezing can change it -- they only multiply the number of times you exploit it.

## When the Equivalence Breaks Down

The equivalence $T \leftrightarrow \ell$ requires that both losses refer to the **same physical channel**: the single-pass loss through the atom--light interaction region.  The strategies can differ when:

- **Loss mechanisms are spatially separated**: e.g., high-efficiency propagation but lossy detection favors squeezing; low intracavity loss but poor mode-matching favors a cavity.
- **Multi-mode or structured probes**: squeezing in multiple spatial modes can exploit information that a single-mode cavity cannot.
- **Detection-limited setups**: if the dominant noise is detector dark counts rather than shot noise, squeezing and cavities respond differently.

## Connection to the Literature

This equivalence is a physically transparent corollary of **decoherence-limited quantum metrology**:

- The general principle that loss sets universal bounds on quantum-enhanced sensing is established in quantum metrology reviews (Giovannetti, Lloyd, Maccone; Demkowicz-Dobrzanski et al.).
- The specific result that all quantum resources become equivalent under loss -- i.e., that Heisenberg scaling collapses back to shot-noise scaling with a prefactor set by loss alone -- is a central result of the field.
- The connection to cavity QED cooperativity ($C = g^2/\kappa\gamma \sim \sigma_0 \mathcal{F}/A$, with free-space limit $C_\mathrm{fs} \sim \sigma_0/A$) places this in a well-studied framework.

Key references:
- Korobko et al., "Quantum expander for gravitational-wave observatories," *Light: Science & Applications* (2019) -- loss inside the sensor as the fundamental limit
- Maccone & Giovannetti, reviews on squeezing metrology and loss-limited quantum sensing
- Demkowicz-Dobrzanski, Kolodynski, Guta, "The elusive Heisenberg limit in quantum-enhanced metrology," *Nature Communications* (2012) -- channel-based bounds showing all quantum strategies collapse under loss

## Summary

$$\boxed{P_\mathrm{err} \sim \exp\!\left(-\frac{\lambda^2}{w^2} \cdot \frac{1}{\mathcal{L}} \cdot N_\mathrm{sc}\right)}$$

The number of scattered photons required for a given detection error is set by two factors:

1. **Geometry** ($\lambda^2/w^2$): the free-space cooperativity, or equivalently, the mode overlap between the atomic dipole radiation and the probe beam.  This is the same for all linear optical measurements (dispersive or resonant).

2. **Loss** ($1/\mathcal{L}$): the maximum enhancement achievable by any quantum or classical strategy (cavity buildup, squeezing, or otherwise), limited by single-pass optical loss through the interaction region.

Squeezed light and optical cavities are two implementations of the same resource.  When limited by the same loss, they are quantitatively identical.
