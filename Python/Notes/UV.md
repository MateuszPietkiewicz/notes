Created: 2025-02-01 11:06

---
Note:

uv to nowoczesny, ultralekki i szybki menedżer pakietów dla Pythona, który jest alternatywą dla pip i virtualenv. Jest rozwijany przez twórców pipenv i pdm i wyróżnia się wysoką wydajnością dzięki implementacji w Rust.

Kluczowe cechy uv:

✅ Szybkość – działa znacznie szybciej niż pip, zwłaszcza przy instalacji wielu pakietów.
✅ Efektywność – lepiej zarządza zależnościami, minimalizując konflikty.
✅ Samodzielność – działa niezależnie od Pythona, nie wymaga środowisk wirtualnych.
✅ Kompatybilność – może współpracować z pip, requirements.txt i pyproject.toml.


**Commands** ```shell
uv # lista wszystkich opcji 
uv init # tworzy podstawową strukture projektowe (nie tworzy virtual env)```


Uruchomienie skryptu python z instalacją tymczasową zależności przy użyciu [[UV]].

```python
# file example.py
import requests r = requests.get('[https://api.nbp.pl/api/exchangerates/rates/a/usd?format=json](https://api.nbp.pl/api/exchangerates/rates/a/usd?format=json)') print(r.json())
```


```python
uv run --with requests example.py
```


--with mówi jakie zależności powinien być zainstalowane, --with może być wiele razy


#### Script dependencies

```python
# /// script # dependencies = [ # "requests<3", # ] # /// 
import requests 
r = requests.get('https://api.nbp.pl/api/exchangerates/rates/a/usd?format=json') 
print(r.json())


```
```shell
uv run example.py
```


 #empty 
---
Metadata:

Status: #pending
Tags: #pip #virtualenv #python_projects
