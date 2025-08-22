# 3.1 Fluids, Density & Upthrust

## Fluids
- A fluid is a substance that deforms continuously when forces are applied to it, i.e. when it's subject to shearing forces.
- When a fluid is at rest then there are no shearing forces acting on it.
- Fluids can be gas, liquid or granular solid substances (e.g. sand)

---

## Shear(ing) Forces
- Shear forces emerge when two forces act in opposite directions but on different planes.
- Shear forces occur parallel to surface and inbetween layers of fluids that move at different speeds.
- usually causes deformation

**Compression**
(Diagram showing a rectangle with forces F1 and F2 pushing inwards from opposite sides)

**Tension**
(Diagram showing a rectangle with forces F1 and F2 pulling outwards from opposite sides)

**Shear**
(Diagram showing a rectangle being deformed into a parallelogram by forces F1 and F2 acting on the top and bottom surfaces in opposite directions)

---

## Density
$$p = \frac{m}{V}$$
$p$ = density (kg m⁻³)
$m$ = mass (kg)
$V$ = volume (m³)

**Basically:**
- How close are the particles packed?
- How heavy are the particles?

### Practical Conversion:
1 g cm⁻³ = 1000 kg m⁻³

---

## Upthrust
- The upwards force an object experiences when submerged in water.
- Defined by Archimedes' Principle:
Upthrust = weight of Water displaced
$$W = V \cdot p \cdot g$$
where $Vp=m$

$V$ = volume (m³)
$p$ = density of fluid (kg m⁻³)
$g$ = gravitational constant
$W$ = weight of liquid displaced (N)

## Floating
- An object floats when it has displaced its own weight in water.

---

## Hydrometer
- measures the density of a liquid
- (Diagram of a hydrometer, a weighted glass tube with markings, floating in a liquid. Scale shows "High" at the top and "Low" at the bottom.)
	- a weighted glass tube with readings at the side, indicating the weight of the liquid.
	- when it sinks deeper, it has to displace more liquid, meaning that the liquid is less dense
	- it floats when the water displaced matches the weight of the tube
- (Diagram showing a close-up of the meniscus) take this reading, be aware of surface tension
- The test tube in which the hydrometer is submerged has to be wide enough so that surface tension to the walls doesn't influence the measurement.

---

## Sphere Volume & Area
*I noticed I forgot*
$$V = \frac{4}{3}\pi r^3$$
$$A = 4\pi r^2$$

---

## Laminar Flow & Turbulent Flow

### Laminar/Streamline Flow:
- occurs at lower speeds
- changes to turbulent flow when reaching a certain speed
	- this value is determined by the properties of the fluid and the shape of the surroundings
- 'laminar' means layered, laminare = layers

#### Pipe example:
(Diagram of layered flow in a pipe)
- Arrows pointing to the center layers: least friction = fast
- Arrows pointing to the outer layers: more friction = slow
- Bracket indicating the layers: layered flow = laminar flow

- layers of laminar flow are called streamlines or laminae
	- velocity is constant for each layer over time

### Turbulent Flow:
- velocity continuously changes, it's chaotic
- it consists of swirling eddies
	- eddies are rotating patches of fluid

(Diagram comparing turbulent and laminar flow profiles in a pipe)
- **Turbulent Flow:** Flat velocity profile, labeled $\bar{v}$. $\bar{v}$ = average velocity over time.
- **Laminar Flow:** Parabolic velocity profile, labeled $\bar{v}$. Flow profile is a parabola. Arrow pointing to the wall indicates "no-slip condition: velocity at wall is always zero!".

---

## Newtonian Fluids
- can be described with Newton's formulae for fluid dynamics

---

## Viscosity
- Viscosity causes friction within a fluid
- Coefficient of viscosity: $\eta$
- Rate of flow (pipe) is inversely proportional to the fluid's viscosity
- increased temperature
	- decreases viscosity for liquids
	- increases viscosity for gasses

---

## Reynold's Number
*partially required*

calculate if a fluid is turbulent or laminar

$$Re = \frac{\rho u L}{\mu}$$
$Re$ = Reynold's Number (none)
$\rho$ = fluid density (kg m⁻³)
$u$ = velocity (ms⁻¹)
$L$ = characteristic length (m)
$\mu$ = dynamic viscosity (Pa·s)

**simplified:**
$$Re = \frac{uL}{v}$$
$Re$ = Reynold's Number
$u$ = velocity
$L$ = characteristic length
$v$ = kinematic viscosity where $v=\frac{\mu}{\rho}$ (m²s⁻¹)

(Diagrams showing characteristic length 'L' for a sphere, an airfoil, and a flat plate perpendicular to flow.)

### Theory:
$$Re = \frac{\rho u L}{\mu} = \frac{\text{inertial forces}}{\text{viscous forces}}$$
- Inertial forces -> causes fluid to move
- Viscous forces -> causes friction due to viscosity

- Depending on which forces dominate, the flow will be turbulent, transitional, or laminar.

(Diagram showing a scale of Reynold's Number Range)
laminar flow <-> transitional flow <-> turbulent flow
- Arrow pointing to the boundary between laminar and transitional: *Re = 2000
- Arrow pointing to the boundary between transitional and turbulent: *Re = 4000

*For flow through a pipe

---

## Calculate Pressure Drop in Pipe
*not required*

### Darcy-Weisbach Equation:
$$\Delta p = f \frac{\rho v_{avg}^2}{2} \frac{L}{D}$$
$\Delta p$ = change in pressure (Pa)
$f$ = darcy friction factor (none)
$L$ = pipe segment length (m)
$\rho$ = fluid density (kg m⁻³)
$v_{avg}$ = mean fluid velocity
$D$ = pipe diameter

**calculate 'f' for laminar flow:**
$$f = \frac{64}{Re}$$

**calculate 'f' for turbulent flow:**
don't even try (use Colebrook equation)

---

## Viscous Force (viscous drag)
*partially required*

calculate the force experienced by an object dragged over a fluid

**model:**
(Diagram of a plate being pulled with force $F_{pull}$ over a fluid layer, with viscous force $F_v$ opposing the motion. The fluid has a velocity gradient.)
$$F_v = \eta A \frac{v}{d}$$
$F_v$ = Viscous Force (N)
*$\eta$ = coefficient of viscosity (Pa·s)
$A$ = area of contact
$v$ = velocity/speed (ms⁻¹)
$d$ = depth of the fluid

* '$\eta$' sometimes measured in 'Poise'
$1 Pa \cdot s = 10 \text{ Poise}$

---

## Volume Flowing through Pipe
*not required*

- how much volume passes a crosssection of a pipe over time

### Poiseuille's Law:
$$\frac{V}{t} = \frac{\Delta p \pi R^4}{8 \eta L}$$
$V$ = volume (m³)
$t$ = time (s)
$\Delta p$ = difference in pressure (Pa)
$R$ = diameter of tube (m)
$\eta$ = coefficient of viscosity (none)
$L$ = total tube length (m)

laminar flow only