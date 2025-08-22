# 7.10 EMF & Internal Resistance

## Terminal Voltage
$$V_{terminal} = \mathcal{E} - Ir$$

- $$V_{terminal} \hat{=} \text{terminal voltage (V)}$$
- $$\mathcal{E} \hat{=} \text{emf (electromotive force) (V)}$$
- $$I \hat{=} \text{current}$$
- $$r \hat{=} \text{internal resistance } (\Omega)$$

**Battery Diagram**
- A battery contains an EMF source and an internal resistance.
- e.g. EMF = 1.5V, Voltage drop across internal resistance = 0.2V
- The resulting terminal voltage is 1.3V.

## Investigating Internal Resistance

$$V_{terminal} = \mathcal{E} - Ir$$
$$V_{terminal} = -r \cdot I + \mathcal{E}$$
(This corresponds to the linear equation $$y = mx + b$$)

**Circuit Diagram**
A circuit is set up with:
- A battery with EMF $$\mathcal{E}$$ and internal resistance $$r$$.
- A voltmeter (V) connected in parallel to the battery to measure terminal voltage.
- An ammeter (A) connected in series.
- A variable resistor in the external circuit.

**Graph of $$V_{terminal}$$ vs $$I$$**
- The y-axis represents $$V_{terminal}$$.
- The x-axis represents $$I$$.
- The graph is a straight line with a negative slope.
- The y-intercept is $$y_0 = \mathcal{E}$$.
- The slope is $$m = -r$$.

## Electro Motive Force - Definition
emf $$\hat{=}$$ The work done per unit charge
as $$ \mathcal{E} = \frac{\text{work done by non-electrostatic forces}}{\text{charge moved}} = \frac{\text{Work on charges}}{Q} $$
$$ \mathcal{E} = \frac{W}{Q} $$

---

1.  $$V_{tor.} = \mathcal{E} - Ir$$
    $$V_{tor} - \mathcal{E} = -Ir$$
    $$r = \frac{\mathcal{E} - V_{tor}}{I} = \frac{6-5.8}{0.4} = 0.55\Omega$$

2.  $$I = \frac{V}{R} = \frac{1.3}{5} = 0.26A$$
    $$r = \frac{\mathcal{E} - V_{terminal}}{I} = \frac{1.5-1.3}{0.26} = 0.77\Omega$$

3.  a) At high currents the internal resistance becomes very noticeable due to $$V=IR$$. When the current is very high the voltage drop over the internal resistance will be large. $$\rightarrow$$ pd across motor maybe be low.
    b) They must be in parallel with the starter motor as the motor draws a lot of current. Therefore the current passing through the lights will momentarily decrease. $$\rightarrow$$ Same might apply for series circuit with lower pd across lights, therefore mention power.

4.  **Graph Analysis**
    - From graph intercept: $$\mathcal{E} \approx 1.6V$$
    - *Note: Line of best fit should be drawn more accurately*
    - Slope: $$m = -\frac{9}{11}$$
    - Resistance: $$r = -(-\frac{9}{11}) = 0.82\Omega$$