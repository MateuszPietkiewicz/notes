Created: 2025-03-29 13:23



# Model AR

$$
X_t = c + \phi_1 X_{t-1} + \phi_2 X_{t-2} + \dots + \phi_p X_{t-p} + \varepsilon_t
$$

## AR(1)
$$
X_{t} = \phi_1 X_{t-1} + \varepsilon_t
$$


gdzie:
 - $X_t$ – wartość szeregu w czasie $t$,
- $c$ -stała (intercept),
- $\phi_1$, $\dots$, $\phi_p$ – współczynniki autoregresji,
- $\varepsilon_t$ – biały szum (zakłócenia losowe), zazwyczaj $\varepsilon_t \sim WN(0, \sigma^2)$.

# Model MA


$$
X_t = \mu + \varepsilon_t + \theta_1 \varepsilon_{t-1} + \theta_2 \varepsilon_{t-2} + \dots + \theta_q \varepsilon_{t-q}
$$

### MA(1)

$$
X_t = \mu + \varepsilon_t + \theta_1 \varepsilon_{t-1} 
$$

gdzie:
- $X_t$ – wartość szeregu w czasie $t$,
- $\mu$ – średnia wartości szeregu,
- $\theta_1, \dots, \theta_q$ – współczynniki średniej ruchomej,
- $\varepsilon_t$ – zakłócenia (biały szum).
  

---
Metadata:

Status: #pending
Tags: #AR #MA
