Created: 2025-02-25 20:48

---



```shell
# odpala wszytkie testy
pytest

# pojedynczy test suite
 pytest tests/test_card.py

# błędy z diffem
pytest -vv

# pojedyncza metoda w klasie
pytest <path>/<module>.py::TestClass::test_method

#pojedyncza klasa
pytest <path>/<module>.py::TestClass

#pojedyncza funkcja
pytest <path>/<module>.py::test_function

#wszystkie test suits w package
pytest <path>/<path>

# wszytkie które pasują do wyrażenia
pytest -k pattern

# wszytkie po markerze
pytest -m marker_name

#bez traceback z podsumowaniem na końcu
pytest -v --tb=no
```

---
Metadata:

Status: #pending
Tags: #pytest #cli
