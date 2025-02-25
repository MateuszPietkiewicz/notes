Created: 2025-02-25 19:49

---
1. Test runner(potrafi odpalać testy z innych bibliotek, świetna integracja z CI/CD)
2. Nie ma assertion library

### Szybki start:

1. Instalacja `uv add "pytest==8.3.4" --dev`
2. Konfiguracja (opcjonalnie, robi sie w `pyproject.toml`) - automatycznie szuka folderu test i plików co zaczyna sie od `test_`
3. Napisac test case np. `test_file_name.py`
4. W terminalu napisać `pytest`

Przykładowy [[TestCase]]:


```python
def inc(x):
    return x + 1

def test_answer():
    assert inc(3) == 5
```

### Słowniczek:
1. [[TestCase]] - sprawdzenie pojedynczej rzeczy
2. [[TestSuite]] - zestaw logicznie połączonych test case (w pytest robi się za pomocą python module lub python class) (oddzielamy plikami)
3. [[TestPlan]] - strategia testowania, zbiór test suite i test case
4. Assert - sprawdzenie warunku, jeżeli false to fail



### [[Pytest CLI]]


---
Metadata:

Status: #pending
Tags: #pytest
