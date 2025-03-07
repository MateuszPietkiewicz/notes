Created: 2025-03-01 22:56

---

Note:
```text
project_name/
│
├── data/
│   ├── raw/                # Surowe dane (niezmodyfikowane)
│   ├── processed/          # Przetworzone dane (po wstępnej obróbce)
│   ├── external/           # Dane zewnętrzne (np. dane publiczne, API)
│   └── interim/            # Tymczasowe dane (np. częściowe wyniki przetwarzania)
│
├── notebooks/
│   ├── exploration/        # Notebooki eksploracyjne (EDA)
│   ├── modeling/           # Notebooki związane z budową modeli
│   └── reporting/          # Notebooki do generowania raportów
│
├── src/                    # Główny kod źródłowy projektu
│   ├── data/               # Skrypty do ładowania i przetwarzania danych
│   ├── features/           # Skrypty do tworzenia cech (feature engineering)
│   ├── models/             # Skrypty do trenowania i ewaluacji modeli
│   └── visualization/      # Skrypty do tworzenia wizualizacji
│
├── reports/
│   ├── figures/            # Wykresy i wizualizacje wyników
│   └── final_report.md     # Końcowy raport projektu (lub PDF)
│
├── tests/                  # Testy jednostkowe dla kodu źródłowego
│
├── requirements.txt        # Lista zależności projektu (Python packages)
├── environment.yml         # Plik środowiska dla Conda (opcjonalnie)
├── README.md               # Opis projektu i instrukcje użytkowania
└── .gitignore              # Plik ignorujący niepotrzebne pliki w repozytorium
```


---
Metadata:

Status: #pending
Tags: #pandas #data
