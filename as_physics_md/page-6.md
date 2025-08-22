# 3.4 Terminal Velocity

## Terminal Velocity
When the weight of an object falling through a fluid cancels with the drag and upthrust, it falls with terminal velocity.
- **V_term only describes vertical motion!**

**Condition:**
$$ W = F_{upthrust} + F_{drag} \quad \text{or} \quad F_{net} = 0 $$

## Stoke's Law
$$ F_D = 6 \pi r \eta v $$
- r = radius
- η = coefficient of viscosity
- v = velocity

calculates drag force on a sphere at low speeds
$$ F_{drag} \propto r $$
and
$$ F_{drag} \propto v $$

## Calculate terminal velocity
$$ W = upthrust + drag $$
$$ mg = \text{weight of displaced fluid} + \text{Stoke's Force} $$
$$ m_{sphere} \cdot g = \frac{4}{3} \pi r^3 \rho v_{term} $$
...
$$ v_{term} = \frac{2r^2 g (\rho_{sphere}-\rho_{fluid})}{9 \eta} $$
- $v_{term} \equiv$ terminal velocity
$$ v_{term} \propto r^2 $$

- Predictions of any kind are tough for turbulent flow, which is usually caused by
    - fast moving objects
    - irregular shapes
    - large objects
- Though larger objects generally fall faster (if they're massive)

## Check understanding:
$$ F_{net} = 0 $$
$$ F_G = F_B + F_D $$
$$ mg = \frac{4}{3} \pi r^3 \rho_f g + 6 \pi r \eta v $$
$$ \rho_s \frac{4}{3} \pi r^3 g = \frac{4}{3} \pi r^3 \rho_f g + 6 \pi r \eta v $$
$$ \rho_s \frac{4}{3} \pi r^2 g - \frac{4}{3} \pi r^2 \rho_f g = 6 \eta v $$
$$ \frac{4}{3} \pi r^2 g (\rho_s - \rho_f) = 6 \pi \eta v $$
$$ \frac{2}{9} r^2 g (\rho_s - \rho_f) \frac{1}{\eta} = v $$
$$ v = \frac{2r^2g(\rho_s-\rho_f)}{9\eta} $$

On the side:
$$ F_B = V \cdot \rho \cdot g \quad F_B = \frac{4}{3} \pi r^3 \cdot \rho \cdot g $$
$$ V = \frac{4}{3} \pi r^3 $$
$$ F_D = 6 \pi r \eta v $$
$$ \rho = \frac{m}{V} \implies m = \rho \cdot V $$
$$ m = \rho \frac{4}{3} \pi r^3 $$

---
## Exercise

1.  $F_D = ?$ $r=0.001m$ $v=0.001 ms^{-1}$ $\eta = 100 Pa \cdot s$
    $$ F_D = 6 \pi r \eta v $$
    $$ F_D = 6 \pi \cdot 0.001 \cdot 100 \cdot 0.001 \approx 1.88 \times 10^{-3} N \quad \checkmark $$

2.  The cat is shaped irregularly, while also falling very fast, so the flow will be turbulent. Turbulent flow is chaotic, therefore hard to predict. (Stokes Law doesn't apply) ✓

3.  a) $r=2m$ $v_{term}=?$ $\eta=1.7 \times 10^{-5} Pa \cdot s$ $\rho_s=7850 kg m^{-3}$ $\rho_f=1.2 kg m^{-3}$
    $$ v = \frac{2 \cdot r^2 g (\rho_s-\rho_f)}{9\eta} = \frac{2 \cdot 2^2 \cdot 10 (7850-1.2)}{9 \cdot 1.7 \times 10^{-5}} $$
    $$ v = 4.1 \times 10^9 ms^{-1} \quad (\checkmark) \text{use 9.81 for g} $$
    The ball just traveled dimensions XD

    b) $r=2m$ $\eta=10^{-3} Pa \cdot s$ $\rho_s=7850$ $\rho_f=1000$
    $$ v = \frac{2 \cdot 2^2 \cdot 10 (7850-1000)}{9 \cdot 10^{-3}} \approx 6.1 \times 10^7 ms^{-1} $$
    (must be) $(\checkmark) \text{use 9.81 for g}$

    c) Flow is laminar, which it isn't, also too fast speeds and too large objects (✓)

4.  $\sim 45 ms^{-1}$ (✓) explain... even if not asked for it lol

5.  a) i) as temperature increases, density decreases ✓
        ii) same ✓

    b) $F_B = V \rho g$
    where a decrease in 'ρ' due to temperature would result in a smaller force. Note that V is increasing though. ✓

    c) It becomes less viscous (roughly halved) ✓ $v_{term}$ is ...

    d) It's linear, as $v_{term}$ is proportional to $r^2$ ~~inversely proportional~~. The decrease in viscosity outweighs the decrease in density. ✓
    $$ v_{term} = \frac{2gr^2(\rho_s-\rho_f)}{9\eta} $$

    e) Its viscosity is way too low for accurate measurements. ✓

---
## Exam Practice

1.  B ✓

2.  $r=0.025m$ $\rho=2500 kg m^{-3}$
    $$ \rho = \frac{m}{V} \implies m = \rho \cdot V $$
    $$ m = 2500 \cdot \frac{4}{3} \pi \cdot 0.025^3 \approx 0.19 kg \quad \text{so C} \quad \checkmark $$

3.  C ✓

4.  B ✓

5.  $2.88 N - 0.58 \approx 2.25 N$ so C ✓

6.  a) i) [Image of laminar flow around an object becoming turbulent behind it] ✓
    
    ii) Laminar flow describes flow that occurs in layers (laminae) that move at different speeds. At any point in the fluid the velocity stays constant. ✓
    Turbulent flow describes flow where the velocity at any given point changes continuously, it's chaotic and hard to predict. ✓ Contains eddies (extra). layers mix/cross (extra).

    b) i) with lower viscosity it should flow faster -> higher velocity ✓
    
    ii) Viscosity of liquids decreases and viscosity of gasses increases with temperature. I expect the overall viscosity to drop, as the blood mainly consists of water. Therefore velocity should increase. ✓

7.  The oil would spread out more as an increase in temperature causes a lower viscosity of the oil which in return results in lower surface tension. ✓ (higher flow rate)

8.  a) i) Laminar flow is shown by the continuous streamlines infront and on the sides of the ball. All points within those streamlines have a constant velocity. ✓
    Turbulent flow is chaotic and consists of many spinning eddies. This is shown by the randomly spinning arrows behind the ball. ✓

    ii) At the top air is being dragged towards the opposing laminar flow, causing a constant turbulence in that area. ✓

    b) If air is being dragged upwards, that means the ball must be dragged downwards. This can be explained by Newton's third law of motion: every action force has a reaction force. ✓

    c) i) $\Delta x = vt$
    $$ 2.7 = 31 t $$
    $$ t = \frac{27}{310} $$
    $$ \Delta y = v_i t + \frac{1}{2} a t^2 = \frac{1}{2} \cdot (-10) \cdot (\frac{27}{310})^2 $$
    $$ \Delta y = -0.0379 m \approx -0.04 m \quad \checkmark $$

    ii) [Image of a right-angled triangle with height 0.15m and base 2.7m]
    $$ \frac{x}{0.15} = \frac{2.7}{1.35} $$
    $$ \frac{x}{0.15} = 2 $$
    $$ x = 0.3 m $$
    The ball with no spin would have to be hit from a height of around 30cm. If the ball spinns (backwards) it experiences an additional force and moves down faster. The initial height can be less. ✓
    (Image of a spinning ball with an arrow indicating motion)

9.  a) i) [Image of a free body diagram of a sphere in a fluid. $F_G$ points down. $F_{Bouyant}$ and $F_{Drag}$ point up.] ✓
    
    ii) That's because the forces acting on it reach an equilibrium: Drag increases with speed until Upthrust + Drag equal the weight of the object. ✓
    
    iii) $F_g = F_{Bouyant} + F_{Drag}$ ✓
    (Note: come up ~ sth smarter)

    b) i) $F_B = \rho \cdot V \cdot g$ (Note: it's not a sphere)
    $$ F_B = 1000 \cdot \frac{4}{3} \pi (1.6 \times 10^{-3})^3 \cdot 10 \approx 1.7 \times 10^{-4} \approx 2 \times 10^{-4} N $$
    (calculation crossed out)
    $$ v_{term} = \frac{2r^2g(\rho_s-\rho_f)}{9\eta} = \frac{2 \cdot (1.6 \times 10^{-3})^2 \cdot 10 (2.7 \times 10^3 - 10^3)}{9 \cdot 1.2 \times 10^{-3}} $$
    (calculation crossed out)
    $$ v_{term} \approx 8.06 ms^{-1} $$

    c) The terminal velocity is proportional to the square of the radius, meaning that the larger particles sink faster. ✓✓✓

10. When the stone is dropped it accelerates until the drag has increased to a point where drag + Bouyant force cancel with the weight, so that $F_{net}=0$. ✓✓✓
When the temperature increases the drag decreases, meaning the equilibrium will be reached at higher speeds in summer. ✓✓
Higher temperature -> lower viscosity in liquid -> less friction -> less drag for same speed.