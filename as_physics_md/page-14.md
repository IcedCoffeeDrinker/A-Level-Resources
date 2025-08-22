# 4.3 Uncertainty & Errors

## Errors in Experimentation
*   Error = difference between recorded value and the actually underlying value
*   uncertainty = the range of possible error around a measured value (e.g. ±5)
*   Human Error = when the human makes a mistake

## Random and Systematic Error
### Random Errors
-   show no pattern
    -   values scattered randomly around true value
-   Random errors cancel (are reduced) when repeating measurements
    -   drawing a best-fit line works too
-   For A-levels repeat an experiment 3-5 times.
-   Can be reduced by using instruments with better precision and higher resolution

### Systematic Error
-   values are consistently scewed
-   no pattern, can be recognized
-   all measurements will be to high or to low
-   Often show up as 'zero error'
    -   values are all off by a fixed value.
    -   where the value should be zero, it's not
    -   Fix: subtract/add the offset to each value
-   Values can also be off by a fraction (e.g. x 106%)
    -   just multiply each value by a correcting factor
    -   this is only possible if the instrument can be tested against actually known values

## Precision & Accuracy
### Precision:
-   for one measurement: how many significant digits recorded
    -   resolution = smallest difference in value possible
-   for multiple measurements: how scattered measurements are
    -   how large is the random error

### Accuracy:
-   how far the (mean) measurements are from the underlying (true) value
    -   systemic error = scew of all values

*(Diagram showing a normal distribution curve. The x-axis is 'value', the y-axis is 'number of results'. 'Precision' is indicated by the narrowness of the curve. 'Accuracy' is indicated by the distance of the curve's center from the 'actual value'.)*

-   measured ↑ actual value
    -   (Diagram of points scattered widely around a central point) not precise, not accurate
    -   (Diagram of points clustered tightly but far from the central point) precise, not accurate
    -   (Diagram of points clustered tightly around the central point) precise and accurate
    -   (Diagram of points scattered widely but centered on the actual value) not precise, accurate

## Timing Errors
### Human reaction time:
-   Measurement delays are inconsistent
    -   start delay will be different from stop delay
-   Fix: Record multiple cycles (e.g. pendulum) and devide time by cycles

### Automatic Systems:
-   delay is small
-   start-stop delay is more consistant

## Parallax Errors
-   caused by a change in viewing angle
    -   when an object moves e.g. when on a spring
-   Fix: Put e.g. ruler closer to the object

## Meniscus Errors
-   caused by surface tension pulling up liquid on walls
    -   creates a miniscus on all sides
-   Fix: measure slightly below the miniscous

## A-Level Instruments & Resolutions
| Instrument | Resolution (accuracy) |
| :--- | :--- |
| • Metre rule | 1mm |
| • Standard Masses | 1g |
| • Ammeters & Voltmeters | Significant figures displayed |
| • Thermometers | 1°C |
| • Micrometer | 0.01mm |
| • Vernier callipers | 0.1mm |
| • Measuring Cylinders and beakers | Smallest measuring devision (depends) |

## Expressing Uncertainties
For test results: Always indicate the uncertainty of results
**Rule:** $$Uncertainty = \pm \frac{\text{least significant figure}}{2}$$
**Example** 3410mm : 2 SF
-   decimal place so least significant figure = 10mm
-   $$10 \div 2 = 5mm$$
-   $$3410mm \pm 5mm$$

**Rule #2:** Never quote a number to more significant figures then known

## Calculate with Uncertainties
### Multiplication and Division:
*   combined uncertainty = sum of percentage uncertainties
*   The final uncertainty is given with the same number of significant figures as the initial uncertainty with least s.f.

**Example:** $$3.75 \pm 0.005 \ \cdot \ 5.6 \pm 0.05$$
percentage uncertainties: $$\frac{0.005}{3.75} \approx 0.13\% \approx 0.1\% \ (1sf)$$
$$\frac{0.05}{5.6} \approx 0.89\% \approx 0.9\% \ (1sf)$$
combined uncertainty = $$0.1\% + 0.9\% = 1.0\% \approx 1\% \ (1sf)$$
*(because initial uncertainties had 1sf)*

### Addition & Subtraction:
**Rule:** Take the worst uncertainly
**Example:** $$1m \pm 0.03m + 5.4m \pm 0.5m = 6m \pm 0.5m$$

## Estimated Figure
*   You are allowed to estimate one magnitude of 10 lower than the resolution of an instrument
    **Example:** (ruler diagram) l=3.6cm where .6 is the estimated figure
*   Estimated figures do count as significant figures

## Systematic Uncertainty for Instruments
*   Usually instruments have a systemic error of 1x their smallest unit of measurement for their entire length
    **Example:** Meter Stick with milimeter marks:
    systemic error = ±1mm for 1m measurements
*   **!** This is added to the random uncertainty

## Calculate Error for Repeated Measurements
**Rule:** $$Error = \frac{\text{max_measured} - \text{min_measured}}{2}$$
**Example:** Measurements:
4.9, 5.2, 5.1, 5.0
$$error = \frac{5.2 - 4.9}{2} = 0.15$$
$$mean = (4.9+5.2+5.1+5.0) \div 4 \approx 5.05 \pm 0.15$$
$$\approx 5.1 \pm 0.15$$

## Percentage Uncertainty in Gradients
*(Diagrams showing data points with a 'line of best fit' and a 'worst acceptable line of best fit'. Calculations for uncertainty are shown.)*
Example 1: $$\frac{|-0.1|}{0.5} \times 100 = 20\%$$
Example 2: $$\frac{0.05}{0.5} \times 100 = 10\%$$
$$ \% \ \text{uncertainty in gradient} = \left| \frac{m_{best} - m_{worst}}{m_{best}} \right| \times 100 $$

## Human vs. Experimental Error
### Human error:
*   errors in measurements due to human mistakes
    -   e.g. reading a value wrong
    -   using the wrong unit

### Experimental error:
*   either systematic or random error
    -   caused by measurement instruments and setup of the apparatus

## Repeatable vs Reliable
### Repeatable:
*   An experiment is repeatable if it gives similar values when repeated under the same conditions
    -   related to random error

### Reliable:
*   An experiment is reliable when it consistently produces accurate results (values that are close to the true value) and has low scatter
    -   related to systemic error and random error.

---

## Correction on Uncertainty
Assume all measurements have an uncertainly equal to the smallest SF of the instrument
e.g. ruler: $$10.3 \pm 0.1cm$$ (1mm)

## Double Readings
=> When reading from an instrument twice, the uncertainty will be twice the smallest unit of the instrument
E.g. when taking two readings from the ruler, uncertainty = ±2mm

## Formatting Uncertainties
value ± uncertainty unit
$$3.5 \pm 0.2cm$$

## Addition & Subtraction
=> Add the absolute uncertainties
$$8.5 \pm 0.2cm - 5.1 \pm 0.1cm = 3.4 \pm 0.3cm$$

## Multiplication and Division
=> Add percentage uncertainties
$$100 \pm 1cm \times 5 \pm 0.5cm$$
$$= 100cm (1\%) \times 5cm(10\%) = 500(11\%)$$

## Exponents
=> Multiply percentage uncertainty by exponent
$$\pi(3 \pm 0.1cm)^2 = \pi(3cm(3\%))^2 = \pi \ 3cm(6\%)$$