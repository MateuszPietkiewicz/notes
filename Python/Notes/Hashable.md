Created: 2025-02-10 18:15

---

W Pythonie obiekty są "hashowalne" (hashable), jeśli ich wartość skrótu (hash) pozostaje stała przez całe ich istnienie. Hashowanie umożliwia szybkie wyszukiwanie i przechowywanie obiektów w strukturach danych takich jak:

- **set** (zbiór),
    
- **dict** (słownik, gdzie klucze muszą być hashowalne).
    

Obiekt jest hashowalny, jeśli spełnia dwa warunki:

1. Posiada metodę `__hash__()`, która zwraca stałą wartość skrótu.
    
2. Jest niezmienny, co oznacza, że jego wartość nie może się zmienić po utworzeniu.
    

## Protokół Hashable i metoda **hash**

Python dostarcza abstrakcyjny protokół `Hashable`, który określa, czy dany obiekt może być użyty jako klucz w słowniku lub element zbioru. Klasy mogą dostarczać własną implementację metody `__hash__()` oraz opcjonalnie `__eq__()` dla poprawnego porównywania.

```python
def __hash__(self) -> int:  
    return hash(self._items)
```

---
Metadata:

Status: #pending
Tags: #protocols 
