# Referat-Seaborn — Seaborn w teorii i w praktyce


Zbiór materiałów (teoria + praktyka) prezentujących użycie biblioteki Seaborn do wizualizacji danych w Pythonie. Projekt zawiera:

- część teoretyczną (`theory/`),
- część praktyczną w formie Jupyter Notebooków (`practice/`),
- plik `requirements.txt` z zależnościami.

Repo jest projektem edukacyjnym i przykładem współpracy nad analizą danych.

---

## Szybkie rozpoczęcie

1. Sklonuj repo i przejdź do katalogu:

```bash
git clone https://github.com/K-Grunke/referat_seaborn.git
cd referat_seaborn
```

2. (Opcjonalnie) utwórz środowisko wirtualne i aktywuj je:

```bash
python -m venv .venv
source .venv/bin/activate  # Linux / macOS
.venv\Scripts\activate     # Windows (PowerShell)
```

3. Zainstaluj zależności:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

4. (Opcjonalnie) uruchom JupyterLab:

```bash
jupyter lab
```

Notebooki znajdują się w `practice/`, materiały w `theory/`.

---

## Struktura repozytorium (ważniejsze)

```
referat_seaborn/
├── README.md
├── CONTRIBUTING.md
├── LICENSE
├── requirements.txt
├── theory/            # materiały teoretyczne
└── practice/          # notebooki
    └── seaborn_analysis.ipynb
```

---

## CI / Workflow

Aktualny workflow (`.github/workflows/notebook_ci.yml`) działa w trybie validation-only:

- parsuje notebooki i sprawdza, czy są poprawne (nbformat),
- raportuje importy wykryte w komórkach kodu,
- sprawdza poprawność plików JSON

Jeśli chcesz lokalnie sprawdzić notebook (szybka walidacja):

```bash
python - <<'PY'
import nbformat
nb = nbformat.read('practice/seaborn_analysis.ipynb', as_version=4)
print('Cells:', len(nb.cells))
PY
```

Aby wygenerować HTML lokalnie (jeśli potrzebujesz):

```bash
jupyter nbconvert practice/seaborn_analysis.ipynb --to html --execute --output-dir=practice/docs
```

---

## Dobre praktyki i contribution

- Przed commitem notebooków: `Restart Kernel & Run All`.
- Usuń zbędne outputy (duże tabele, obrazy generowane automatycznie).
- Każdy wykres powinien mieć opis w Markdown.
- Twórz gałęzie robocze `feature/<opis>` i otwieraj PR do `dev`.
- PR wymaga przynajmniej 1 review i przejścia CI przed merge.

Szczegóły znajdziesz w `CONTRIBUTING.md`.

---

## Licencja

Projekt udostępniony na licencji MIT — zobacz `LICENSE`.
