Created: 2025-02-26 19:41

---


```bash
# lista plus opis wszytkich fixtures dostępnych w danej instalacji pytest
pytest --fixtures
# pokazanie co się kiedy odpala
pytest --setup-show

# pokazuje testcase i fixtures jakie używają z dokumentacją i lokalizacją
pytest --fixtures-per-test


```



```python
import pytest  
  
@pytest.fixture()  
def some_data():  
    '''Return answer to ultimate question'''  
    return 42  
  
def test_dome_data(some_data):  
    assert some_data == 42
```

### Monkey Patch pytest
	
	- setattr(target, name, value, raising=True)
	- delattr(target, name, raising=True)
	- setitem(dict, name, value)
	- deitem(dict, name, raising=True)
	- setenv(name, value, prepend=None) - ustawia zmienną środowiskową
	- delenv(name, raising=True)
	- syspath_prepend(path) - modyfikacja importów python (sys.path)
	- chdir(path) - zmienia aktualny folder

---
Metadata:

Status: #pending
Tags: #pytest 
