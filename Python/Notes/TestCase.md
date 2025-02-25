Created: 2025-02-25 20:25

---


**Obsługa kodu, w której spodziewamy się wyjątku**
Nie można tego napisac bez context-menagera, gdyż błąd python przerywa test. Zawsze używaj match, w celu upewnienia się, że na pewno odpowiedni wyjątek został wyemitowany.


```python
def add(x):
import pytest

return x

def test_raise_with_info():  
    match_regex = "missing 1 .* positional argument"  
  
  
    with pytest.raises(TypeError, match=match_regex):  
        add()

```
### Test structure

1. Arrange -Act - Assert (AAA)
2. Given - when -then



```python
def test_to_dict():  
    # AAA - arrange, act, assert  
    # Given, when, then        # GIVEN a Card object with known contents  
    c1 = Card("something", "yolo", "todo", 123)  
      
    # WHEN we call to_dict() on the object  
    c2 = c1.to_dict()  
      
    #THEN the result will be a dictionary with known contents  
          
	c2_dict ={  
	        "summary": "something",  
	        "owner": "yolo",  
	        "state": "todo",  
	        "id": 123,  
	    }  
      
    assert c2 == c2_dict
```


---
Metadata:

Status: #pending
Tags: #pytest
