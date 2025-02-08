
### 1. Co to jest protokół Iterable?

Protokół `Iterable` w Pythonie pozwala na iterowanie po kolekcjach danych, takich jak listy, krotki, słowniki czy zbiory. Obiekt, który implementuje ten protokół, może być używany w pętlach `for` oraz w funkcjach takich jak `map()`, `filter()` czy `sorted()`.

### 2. Jak działa protokół Iterable?

Obiekt jest **iterowalny (iterable)**, jeśli implementuje metodę `__iter__()`, która zwraca iterator, czyli obiekt implementujący metodę `__next__()`.

### 3. Tworzenie klasy iterowalnej

Aby stworzyć własny obiekt iterowalny, należy zaimplementować metodę `__iter__()` oraz iterator z metodą `__next__()`

```python
def __iter__(self) -> Iterator[SupportsRichComparison]:  
    return iter(self._items)
```
lub 
```python
def __iter__(self) -> Iterator[SupportsRichComparison]:  
	for item in self._items:  
	    yield item
```
### 4. Funkcja `iter()` i `next()`

Funkcja `iter(obj)` zwraca iterator z obiektu iterowalnego, a `next(iterator)` pobiera kolejną wartość:

```
lista = [1, 2, 3]
iterator = iter(lista)
print(next(iterator))  # 1
print(next(iterator))  # 2
print(next(iterator))  # 3
```

### 5. Generatory jako iteratory

Generatory to specjalne iteratory tworzone za pomocą słowa kluczowego `yield`:

```
def generator():
    yield 1
    yield 2
    yield 3

for liczba in generator():
    print(liczba)
```

 ###  **Podsumowanie:**

✅ Obiekt iterowalny musi implementować `__iter__()` 
✅ Iterator musi mieć metodę `__next__()` 
✅ Można używać w pętlach `for`, `map()`, `filter()`, `sorted()` 
✅ Generatory to wygodny sposób tworzenia iteratorów



|Cecha|Iterable|Iterator|
|---|---|---|
|**Definicja**|Obiekt, który można iterować|Obiekt zwracający kolejne elementy|
|**Metody**|`__iter__()`|`__iter__()`, `__next__()`|
|**Pętla `for`**|Tak|Tak|
|**Tworzy iterator**|Tak (`__iter__()`)|Sam nim jest (`__iter__()` zwraca `self`)|
|**Przykłady**|`list`, `tuple`, `str`, `range()`|Obiekt zwracany przez `iter()`|

📌 **Każdy `Iterator` jest `Iterable`, ale nie każde `Iterable` jest `Iterator`em!**  
Przykładowo, lista (`list`) jest iterowalna (`Iterable`), ale sama w sobie **nie jest iteratorem** – trzeba wywołać `iter(lista)`, aby otrzymać iterator.