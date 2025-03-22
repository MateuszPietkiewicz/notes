Created: 2025-03-20 20:49

---

|     | product | quantity | price |
| --- | ------- | -------- | ----- |
| 0   | apple   | 10       | 0.5   |
| 1   | banana  | 5        | 0.3   |
| 2   | apple   | 4        | 0.5   |
| 3   | banana  | 7        | 0.3   |
| 4   | orange  | 8        | 0.7   |



```python
df = pd.read_csv(buffer)
df.dtypes #podaje typy kolumn
df.shape #podaje wymiary dataframe
```

Nowa kolumna:
```python
 df["revenue"] = df["quantity"] * df["price"] # tworzy nowa kolumne w tabelce o nazwie revenue z pomnożonymi tymi wartościami
```


Grupowanie:
pogrupowanie po produktach z życiem agregacji dodawania w kolumnie revename
```python
df.groupby("product")["revenue"].sum()

product
apple     7.0
banana    3.6
orange    5.6
Name: revenue, dtype: float64

# Przedstawi najdroższy produkt:
df.groupby("product")["revenue"].sum().idxmax()
'apple'

# Przedstawi najdroższy produkt i jego wartość:
product_revenues_ = df.groupby("product")["revenue"].sum()

print(f"{product_revenues_.idxmax()}, {product_revenues_[product_revenues_.idxmax()]}")

apple, 7.0

# Przdstawia ilośc danych produktów:
print(f"Frequency: {df.groupby('product')['product'].count()}")

Frequency: product
apple     2
banana    2
orange    1
Name: product, dtype: int64

#Przedstawia zliczenie ilości wszytkich produktów:
df['product'].count()

np.int64(5)
```

---
Metadata:

Status: #pending
Tags: #pandas
