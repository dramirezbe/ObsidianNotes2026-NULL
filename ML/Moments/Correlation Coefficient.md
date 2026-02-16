The Correlation Coefficient is a "normalized" version of covariance. While covariance can be any number (depending on the units of your sensors), correlation is always scaled between **-1 and 1**.

### The Formula

$$\rho_{X,Y} = \frac{Cov(X,Y)}{\sqrt{Var(X)Var(Y)}}$$

Or, using standard deviations ($\sigma$):

$$\rho_{X,Y} = \frac{\sigma_{XY}}{\sigma_X \sigma_Y}$$

---

### Why do we divide by the square root of variances?

Think of this as **Standardization**:

1. **Covariance ($Cov$):** Depends on the units. If you measure temperature in Celsius vs. Fahrenheit, the covariance value changes even though the data is the same.
    
2. **Product of Standard Deviations ($\sigma_X \sigma_Y$):** This represents the "maximum possible" spread of the data.
    
3. **The Division:** By dividing the shared variance by the individual variances, you strip away the units and the scale. You are left with a pure ratio of how much the variables move together versus how much they move individually.
    

---

### Interpretation Table

|**Value**|**Meaning**|**Sensor Example**|
|---|---|---|
|**+1.0**|Perfect Positive Linear|Two identical sensors measuring the same signal.|
|**+0.7**|Strong Positive|CPU Load and CPU Temperature.|
|**0.0**|No Linear Relationship|Random thermal noise vs. a 60Hz power line hum.|
|**-0.7**|Strong Negative|Battery Voltage vs. Current Draw (Voltage drops as load increases).|
|**-1.0**|Perfect Negative|An inverter circuit (output is exactly the inverse of input).|

---

### Key Properties

- **Dimensionless:** It has no units (unlike Covariance).
    
- **Scale Invariant:** If you multiply all your sensor readings by 1000 (e.g., converting Volts to milliVolts), the **Correlation stays exactly the same**, while the Covariance would change.
    
- **Linearity:** It only measures _linear_ relationships. If $Y = X^2$, the correlation might be low even though they are perfectly related.

> [!NOTE]
> 
> In Python (`numpy.corrcoef`), this is the value you get. It is essentially the "cosine of the angle" between two data vectors in high-dimensional space.
