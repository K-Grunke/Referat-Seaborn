# Zasady współpracy — Referat-Seaborn

Dziękujemy za wkład w projekt — poniższy przewodnik pomaga sprawnie współpracować i utrzymywać jakość materiałów.

---

## Krótkie podsumowanie
- Gałęzie: `main` (stabilna), `dev` (integracja), `feature/*` (praca robocza).
- PR: kieruj do `dev`, wymagane pozytywne CI i przynajmniej 1 review.
- Notebooki: przed commitem uruchom `Restart Kernel & Run All`, nie commituj dużych outputów.

---

## 1. Wymagania
- Python 3.13
- Zależności w `requirements.txt` (instalacja lokalna lub Codespaces)
- Git, konto GitHub

## 2. Struktura (najważniejsze)
- `README.md` — informacje ogólne
- `requirements.txt` — dependencies
- `theory/` — materiały teoretyczne
- `practice/` — notebooki (`practice/seaborn_analysis.ipynb`)
- `.github/workflows/` — CI (notebook validation)

## 3. Praca z gałęziami i PR
1. Zaktualizuj lokalne `dev` i stwórz `feature/<opis>`:
```bash
git checkout dev
git pull
git checkout -b feature/<krótka-nazwa>
```
2. Pracuj lokalnie lub w Codespaces, rób małe, logiczne commity.
3. Przed push: upewnij się, że notebooki są czyste (Restart Kernel & Run All).
4. Push i utwórz PR: `feature/* -> dev`.
5. PR merge po pozytywnym review i przejściu CI.

## 4. Zasady commitów
- Stosuj opisowe komunikaty: `Dodano analizę rozkładów dla dataset tips`.
- Unikaj krótkich, nieopisowych commitów: `fix`, `update`.

## 5. Notebooks — dobre praktyki
- Przed commitem: `Restart Kernel & Run All` i usuń niepotrzebne outputy.
- Trzymaj kod w komórkach tak, żeby dało się go uruchomić od początku.
- Dodaj krótki opis (Markdown) dla każdego wykresu.

## 6. CI — co robi workflow
- `notebook_ci.yml` (validation-only) sprawdza, czy notebook jest poprawny (parsowalny) i raportuje importy.
- PR nie powinien być scalony, jeśli validation job zgłasza błąd.

## 7. Sprawdzanie lokalnie (szybkie komendy)
- Instalacja zależności:
```bash
python -m pip install -r requirements.txt
```
- Uruchomienie notebooka lokalnie (bez GUI):
```bash
python - <<'PY'
import nbformat
nb = nbformat.read('practice/seaborn_analysis.ipynb', as_version=4)
print('Cells:', len(nb.cells))
PY
```

## 8. Code review — oczekiwania
- Sprawdź, czy notebook uruchamia się od początku.
- Oceń czy opisy i wykresy są zrozumiałe.
- Zwróć uwagę na importy i wymagania w `requirements.txt`.

## 9. Issues i komunikacja
- Zgłaszaj błędy przez Issues z opisem i (jeśli możliwe) krokiem reprodukcji.
- Do dyskusji ogólnych używamy Discussions.

## 10. Kontakt/maintainerzy
- Jeśli nie jesteś pewien zmian — otwórz draft PR i poproś o review.

---

Dziękujemy za wkład — każda poprawka i sugestia się liczy.
