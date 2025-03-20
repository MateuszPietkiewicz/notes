Created: 2025-03-20 20:31

---

Importowanie pandasa i aliasowanie:

```python
import pandas as pd
```

Importowanie danych:



```python
import io

buffer = io.StringIO('''
product,quantity,price
apple,10,0.5
banana,5,0.3
apple,4,0.5
banana,7,0.3
orange,8,0.7
'''.lstrip())


df = pd.read_csv(buffer)
df
```

Wynik:

|     | product | quantity | price |
| --- | ------- | -------- | ----- |
| 0   | apple   | 10       | 0.5   |
| 1   | banana  | 5        | 0.3   |
| 2   | apple   | 4        | 0.5   |
| 3   | banana  | 7        | 0.3   |
| 4   | orange  | 8        | 0.7   |


---
Metadata:

Status: #pending
Tags: #pandas
