Created: 2025-02-07 10:41

---
Protokół Container - sprawdza czy coś może to zawierać. Czy można użyć "in" na tego typie danych.

Rozwiązania:
1
```python
def __contains__(self, item: Hashable) -> bool:  
    return item in self._items

```
2
```python
def __contains__(self, item: Hashable) -> bool: 
	for item_ in self._items:  
	    if item_ == item:  
	        return True  
	return False
```
3
```python
def __contains__(self, item: Hashable) -> bool: 
	return self._items.__contains__(item)
```


---
Metadata:

Status: #pending
Tags: #protokols

