Created: 2025-03-27 21:42

---
## 1. pip 

pip install numpy
pip freeze > requirements.txt - Zapisywanie zależności
pip install -r requirements.txt - Instalacja z pliku

### Plusy

- ✅ bardzo proste i powszechnie używane
    
- ✅ działa wszędzie
    

### Minusy

- ❌ brak automatycznego środowiska
    
- ❌ trudne zarządzanie wersjami
    
- ❌ nieporządek w większych projektach
## 2. poetry

### Inicjalizacja projektu

`poetry init # lub nowy projekt poetry new my_project`

### Dodawanie biblioteki

`poetry add numpy`

### Uruchamianie kodu

`poetry shell # lub poetry run python script.py`

### Pliki projektu

- `pyproject.toml` — główny plik konfiguracyjny
    
- `poetry.lock` — dokładne wersje zależności
    

### Plusy

- ✅ automatyczne środowisko wirtualne
    
- ✅ spójne wersje (lockfile)
    
- ✅ wsparcie dla `pyproject.toml`
    

### Minusy

- ❌ wolniejsze niż pip
    
- ❌ czasem problemy z zależnościami

## 3. uv

> `uv` łączy funkcjonalność `pip`, `poetry`, `virtualenv` i innych w jednym szybkim narzędziu.

### Inicjalizacja projektu


`uv init`

To tworzy:

- `.venv/` — środowisko
    
- `pyproject.toml`
    
- `uv.lock`
    

### Dodawanie biblioteki


`uv add numpy`

### Uruchamianie


`uv run python script.py`

### Zarządzanie środowiskiem


`uv venv exec bash uv pip list`

### Plusy

- ✅ mega szybkie instalacje (nawet 10–100x szybciej)
    
- ✅ automatyczne środowisko
    
- ✅ kompatybilność z `pyproject.toml`
    

### Minusy

- ❌ nowość (jeszcze mało popularne)
    
- ❌ wymaga instalacji z zewnętrznego skryptu


## 📊 Podsumowanie

|Narzędzie|Zależności|Środowisko|Zalety|Wady|
|---|---|---|---|---|
|pip|requirements.txt|❌ ręczne|proste, powszechne|brak środowiska, trudność w utrzymaniu|
|poetry|pyproject.toml|✅ tak|kompletne zarządzanie projektem|wolniejsze, czasem błędy|
|uv|pyproject.toml|✅ tak|ultra szybkie, nowoczesne|nowość, mniejsze community|

---
Metadata:

Status: #pending
Tags: #uv #poetry #pip
