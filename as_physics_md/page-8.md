# 3.6 Stress, Strain, Young Modulus

## Stress
- **Tensile Stress:** force due to tension/extension
- **Compressive Stress:** force due to pressure/compression

Stress is calculated as the force acting within an object over its perpendicular cross-section.

$$
\sigma = \frac{F}{A}
$$
- $\sigma \equiv$ stress (Pa)
- $F \equiv$ force acting within the object* (N)
- $A \equiv$ cross-sectional area of object ($m^2$)

***
<-- F --- [BOX] --- -F -->
***
*The force acting inside the object is the reaction force to the one acting outside. At all points within the object it's equal.

***

## Strain
- **Tensile strain:** deformation caused by stretching
- **Compressive strain:** deformation caused by compression lol

Strain describes the ratio of extension to original length:
$$
\varepsilon = \frac{\Delta l}{l_i}
$$
- $\varepsilon \equiv$ strain (none)
- $\Delta l ; \Delta x \equiv$ extension (m)
- $l_i ; x_i \equiv$ initial length (m)

Strain is often represented as a percentage, e.g.
$\varepsilon = -0.25 \Rightarrow$ The object has a compressive strain of 25%.

***

## Young Modulus
The Young modulus describes the stiffness constant of a material. Its value is independent of an object's shape or size, as it generalizes those attributes.

$$
E = \frac{\sigma}{\varepsilon} = \frac{Fl_i}{A\Delta l}
$$
- $E \equiv$ Young Modulus (Pa)
- $\sigma \equiv$ stress (Pa)
- $\varepsilon \equiv$ strain (none)

> [!NOTE] elastic deformation only

**Difference of k and E:**
- k relates to the stiffness of a particular object
- E describes the stiffness of a material, regardless of its shape

The Young modulus (E) actually measures the work done along the object, over the potential energy gained per volume extended.
$$
E = \frac{\sigma}{\varepsilon} = \frac{Fl_i}{A\Delta l} = \frac{F \cdot d}{V} = \frac{W}{V}
$$

***
*From a Stress (y-axis) vs. Strain (x-axis) graph:*
- Gradient: $m=E$
- Area under graph: $A=PE_{elastic}$

*From a mass (y-axis) vs. extension (x-axis) graph:*
$$
E = \frac{Fl_i}{A \Delta l} = \frac{m}{\Delta l} \cdot \frac{g l_i}{A}
$$
$$
E = \text{gradient} \cdot \frac{g l_i}{A}
$$