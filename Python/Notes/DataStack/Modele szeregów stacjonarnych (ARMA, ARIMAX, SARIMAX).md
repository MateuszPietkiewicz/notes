Created: 2025-04-02 19:42

---

# Model ARMA

```python
ar_coef = [1, -0.5]
ma_coef = [1, 0.2]
```


$$
y_t = 0.5y_{t-1} + 0.2\varepsilon_{t-1} + \varepsilon_t
$$


ARMA(p, q)
p - ma AR, 
q - ma MA

# Model ARIMA
- usuwa ten model automatycznie trend szeregu

ARIMA(p , d, q)

# Model ARIMAX

Autoregressive Integrated Moving Average with Exogenous Variables


# Model SARIMAX

Seasonal ARIMAX
- SARIMAX(p, d, q, P, D, Q, s)
  

---
Metadata:

Status: #pending
Tags: #ARMA #ARIMAX #SARIMAX
