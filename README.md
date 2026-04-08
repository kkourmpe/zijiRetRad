# zijiRetRad
XSPEC table model for blackbody and reflection spectra produced by disk self-irradiation and higher-order reflection in a corona-less scenario in X-ray binaries

# zijiRetRad XSPEC Model

**zijiRetRad** is an additive table model for XSPEC, based on the `ziji` code.  
It simulates the X-ray **reflection** and **blackbody emission** of a corona-less black hole accretion disk system.

---

## Physical Description

The model assumes that disk illumination occurs purely through:

- Self-irradiation of the accretion disk  
- Higher-order (iterative) reflections  

This setup is particularly relevant for systems without a corona.

![Model geometry](figures/model.png)

---

## Model Components

The package contains three XSPEC table models:

- `zijiRetRad_bb.fits` — blackbody component  
- `zijiRetRad_ref.fits` — reflection component  
- `zijiRetRad_tot.fits` — total spectrum  

---

## Model Parameters

The model includes **five physical parameters**:

1. Electron density: $n_{\rm e}$
2. Spin parameter: $a_*$
3. Black hole mass: $M_{\rm BH}$
4. Mass accretion rate: $\dot{M}_{\rm BH}$
5. Inclination angle: $i$

---

## Normalization

The source distance is encoded in the XSPEC normalization:

$$
\mathcal{N} = 0.229 \frac{M^2}{D^2}
$$

- $M$ in solar masses ($M_\odot$)  
- $D$ in kpc  

---

## Parameter Grid

| Parameter | Values |
|----------|--------|
| Electron density ($\mathrm{cm^{-3}}$) | $10^{18}$ – $10^{22}$ |
| Spin $a_*$ | 0.8146 – 0.9982 |
| Mass ($M_\odot$) | 10 |
| Accretion rate ($10^{18}$ g/s) | 0.14 – 2.1 |
| Inclination ($^\circ$) | 30 – 75 |

See full grid details in the paper.

---

## Usage in XSPEC

```bash
XSPEC> model atable{zijiRetRad_tot}
