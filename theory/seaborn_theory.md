# Biblioteka Seaborn – Nowoczesna wizualizacja danych w Pythonie
### Autorzy:
- **Konrad Grünke**
- **Jakub Malc**
- **Bartosz Sulerzycki**
- **Karolina Borża**

---

## Geneza i historia Seaborn
- **Stworzony przez Michaela Waskoma (2012–2013)** – Biblioteka powstała jako projekt badawczy, który miał ułatwić tworzenie estetycznych wykresów statystycznych w Pythonie. Z czasem stała się jednym z najpopularniejszych narzędzi do wizualizacji danych w ekosystemie Pythona.

- **Rozszerzenie Matplotlib o statystyczne wizualizacje** – Seaborn bazuje na Matplotlib, ale dodaje gotowe funkcje do tworzenia wykresów statystycznych, takich jak rozkłady, regresje czy wykresy kategorii, dzięki czemu dużo szybciej można uzyskać informacyjne grafiki.

- **Nastawiony na estetykę i analizę eksploracyjną** – Domyślne style i palety kolorów są bardziej nowoczesne i czytelne niż w czystym Matplotlib, co pozwala skupić się na analizie danych bez konieczności ręcznego dostosowywania wyglądu każdego wykresu.

- **Dynamiczny rozwój** — wersje 0.10+ i 0.12+ wprowadzają duże zmiany API – W tych wersjach pojawiły się nowe funkcje i uproszczone interfejsy (np. displot, relplot, catplot), większa spójność w projektowaniu wykresów oraz lepsza integracja z pandas, co ułatwia pracę z danymi i tworzenie złożonych wizualizacji.

---

## Cele i filozofia projektowa Seaborn

- Ułatwienie tworzenia estetycznych wykresów w Pythonie z minimalnym kodem.
- Integracja ze strukturami danych pandas, aby szybko wizualizować DataFrame’y.
- Dostarczanie gotowych motywów i stylów, które wyglądają profesjonalnie bez dodatkowej konfiguracji.
- Ułatwienie analizy statystycznej poprzez wbudowane funkcje do regresji, estymacji gęstości, wykresów relacji itp
- Ujednolicenie interfejsu do tworzenia wykresów i zapewnienie spójności pomiędzy różnymi typami wizualizacji.
- Skupienie na relacjach między zmiennymi oraz strukturze danych, a nie na pojedynczych seriach.
- Automatyczne zarządzanie złożonymi elementami wykresów, jak legendy, siatki, kolory czy faceting (podziały na podwykresy).

Seaborn powstał jako warstwa wyższego poziomu nad biblioteką Matplotlib, mająca uprościć proces tworzenia wykresów i uczynić go bardziej intuicyjnym. Jego filozofia opiera się na założeniu, że statystyczna wizualizacja danych powinna być maksymalnie prosta, a jednocześnie domyślnie estetyczna i profesjonalna. Dzięki temu użytkownik może skupić się na interpretacji danych, a nie na technicznych szczegółach rysowania wykresów.

Kluczowym elementem filozofii Seaborn jest silna integracja z pandas – biblioteka „rozumie” DataFrame’y, nazwy kolumn oraz relacje między zmiennymi. Zamiast ręcznie wybierać serie danych, użytkownik pracuje na logicznym poziomie: wskazuje, która kolumna jest zmienną x, która y, a Seaborn zajmuje się resztą.

Ważnym filarem jest też estetyka i spójność. Seaborn dostarcza zestaw eleganckich motywów oraz palet kolorów, które tworzą wizualizacje atrakcyjne bez dodatkowego stylizowania. Twórcy przyjęli filozofię „mniej kodu – więcej treści”, co czyni bibliotekę przystępną zarówno dla początkujących, jak i ekspertów.

---

## Kluczowe funkcjonalności Seaborn

- **Wykresy statystyczne wysokiego poziomu** – Biblioteka dostarcza gotowe funkcje do tworzenia złożonych wizualizacji statystycznych, takich jak wykresy regresji, rozkładów czy zależności między zmiennymi, bez konieczności pisania dużej ilości kodu.

- **Automatyczna estetyka i style wykresów** – Seaborn zapewnia eleganckie, domyślne style i palety kolorów, które natychmiast poprawiają wygląd wykresów, ograniczając potrzebę ręcznego dostosowywania.

- **Obsługa danych tabelarycznych (DataFrame)** – Funkcje Seaborna akceptują dane w formacie kolumnowym, dzięki czemu można od razu przekazywać DataFrame’y i wybierać zmienne po nazwach kolumn.

- **Facetowanie i siatki wykresów** – Biblioteka umożliwia łatwe tworzenie wielu podobnych wykresów obok siebie, podzielonych według kategorii lub wartości zmiennych, co wspiera analizę porównawczą.

- **Integracja z Pandas i Matplotlib** – Seaborn korzysta z Pandas do pracy z danymi, a z Matplotlib do wyświetlania wykresów, dzięki czemu dobrze współpracuje z istniejącym ekosystemem narzędzi analitycznych.

- **Figure-level API (relplot, catplot, displot)** – Ten wyższy poziom API tworzy całe figury wraz z siatką wykresów, oferując spójną logikę ustawień i umożliwiając wygodne budowanie złożonych wizualizacji jednym wywołaniem funkcji.

---

## Typy wykresów w Seaborn

- **Relacyjne:** scatterplot, lineplot, relplot
- **Kategoryczne:** barplot, boxplot, violinplot, catplot
- **Dystrybucji:** histplot, kdeplot, displot
- **Regresyjne:** regplot, lmplot
- **Macierzowe:** heatmap, clustermap

---

## Style, motywy i estetyka w Seaborn

**Gotowe style: darkgrid, whitegrid, dark, white, ticks –** Seaborn oferuje zestaw predefiniowanych stylów, które zmieniają tło, siatkę i ogólną estetykę wykresów, pozwalając szybko dopasować wygląd do charakteru prezentacji danych.

**Konfiguracja globalna: sns.set() –** Jedno polecenie umożliwia ustawienie domyślnego stylu, palety kolorów i kontekstu dla wszystkich kolejnych wykresów, co pomaga zachować spójność w całej analizie.

**Palety kolorów: deep, muted, pastel, colorblind –** Seaborn zawiera gotowe palety zaprojektowane pod kątem czytelności i estetyki; można wybierać między bardziej wyrazistymi, stonowanymi czy przyjaznymi osobom z wadami widzenia.

**Kontekst: paper, notebook, talk, poster –** Kontekst określa skalę elementów wykresu (np. tekstu, grubości linii) i pozwala łatwo dostosować grafikę do medium, w którym będzie używana, czy to publikacja, prezentacja czy praca w notebooku.

---

## Integracja z Pandas i Matplotlib
- **Naturalna praca z DataFrame –** Seaborn jest projektowany z myślą o danych tabelarycznych, dzięki czemu większość funkcji przyjmuje DataFrame’y bez dodatkowego przygotowania.

- **Automatyczne mapowanie nazw kolumn –** Wystarczy podać nazwy kolumn jako argumenty x, y czy hue, a Seaborn sam pobiera odpowiednie 
dane, eliminując konieczność ręcznego indeksowania.

- **Łatwe łączenie z funkcjami Matplotlib –** Wykresy tworzone przez Seaborn opierają się na Matplotlib, co pozwala dalej dostosowywać je standardowymi funkcjami, np. dodawać tytuły, zmieniać etykiety czy formatowanie osi.

- **Pełna kompatybilność ekosystemu PyData –** Biblioteka płynnie współpracuje z Pandas, NumPy, SciPy i innymi narzędziami analitycznymi, umożliwiając spójny przepływ pracy od wczytania danych aż po zaawansowaną wizualizację.

---

## Facetowanie i wizualizacja wielowymiarowa + zaawansowane możliwości API
**Czym jest facetowanie?**
- Automatyczny podział danych na kategorie i prezentacja w formie siatki wykresów
- Ułatwia analizę wielowymiarową
- Pozwala porównywać relacje w różnych grupach danych

**Parametry grupowania**
- **hue -** grupowanie kolorem
- **col, row -** tworzenie siatki wykresów
- **size -** różnicowanie rozmiarem
- **style -** różnicowanie kształtem

**Siatki wykresów**
- **FacetGrid -** tworzenie siatek wykresów na podstawie zmiennych kategorycznych
- **PairGrid -** macierz wykresów analizująca wszystkie pary zmiennych
- **pairplot() -** uproszczona wersja do szybkiej eksploracji
---
**Figure-level API**
Funkcje pracujące na poziomie całych figur:
- **relplot() -** wizualizacja relacji między zmiennymi
- **catplot() -** wykresy dla danych kategorycznych
- **displot() -** wizualizacja rozkładów danych
**Zalety:**
- Jedno polecenie tworzy kompleksową siatkę wykresów
- Automatyczne zarządzanie układem, legendami, tytułami
- Spójna składnia dla różnych typów wizualizacji

**Zaawansowane możliwości**
- Niestandardowe style i motywy
- Własne palety kolorów
- Pełna integracja z Matplotlib
- Łączenie high-level API z low-level customizacją

---

## Wbudowane mechanizmy statystyczne

- Automatyczne dopasowanie modeli (regresja)

- Przedziały ufności i estymacja niepewności

- Wizualizacja rozkładów (KDE, histogramy, ECDF)

- Grupowanie i agregacja danych

- Wsparcie statystyczne w wykresach kategorycznych

## Seaborn vs. Matplotlib

**Poziom abstrakcji:** Matplotlib jest narzędziem niskopoziomowym („jak narysować”), podczas gdy Seaborn działa na wyższym poziomie („co pokazać”).

**Kod:** Stworzenie złożonego wykresu w Matplotlib wymaga znacznie więcej kodu.

**Estetyka:** Domyślne wykresy Seaborna są nowocześniejsze i bardziej atrakcyjne.

**Statystyka:** Seaborn ma wbudowane funkcje statystyczne (regresja, przedziały ufności), które w Matplotlib muszą być implementowane ręcznie.

**Zależność:** Seaborn nie zastępuje Matplotliba, ale na nim bazuje, co pozwala na użycie funkcji plt do finalnego dostrojenia wykresu.

---

## Seaborn vs. Plotly

**Interaktywność:** Podstawowa różnica. Plotly tworzy w pełni interaktywne wykresy (zoom, tooltips, panowanie), podczas gdy wykresy Seaborna są statyczne (choć można je zapisać w wysokiej rozdzielczości).

**Złożoność:** Plotly może wymagać więcej konfiguracji dla prostych wykresów.

**Zastosowanie:** Seaborn jest doskonały do szybkiej EDA i statycznych raportów PDF. Plotly dominuje w aplikacjach webowych i dashboardach, gdzie interaktywność jest kluczowa.

**Skalowanie:** Plotly często lepiej radzi sobie z bardzo dużymi zbiory danych w kontekście interaktywnym.

---

## Seaborn vs. ggplot (R)
- **Filozofia:** Oba narzędzia implementują „gramatykę grafiki” (Grammar of Graphics), ale w inny sposób. ggplot2 w R jest jej bezpośrednią implementacją (warstwy: data, aes, geom). Seaborn jest jej interpretacją w Pythonie, oferując bardziej zintegrowane funkcje wysokiego poziomu.
- **Składnia:** Składnia Seaborna jest bardziej imperatywna (sns.boxplot(...)), podczas gdy ggplot2 jest deklaratywny i oparty na operatorze +.
- **Ekosystem:** ggplot2 jest głęboko zintegrowany z ekosystemem „tidyverse” w R, oferując niesamowitą spójność. Seaborn natomiast doskonale wpasowuje się w ekosystem PyData (Pandas, NumPy).

---

## Zaawansowane zastosowanie Seaborn

**Analiza wielowymiarowa z PairGrid i FacetGrid –** Te klasy pozwalają tworzyć całe siatki wykresów, porównujące wiele zmiennych jednocześnie, co ułatwia dostrzeganie zależności i wzorców w danych.

**Wizualizacja macierzy korelacji (heatmap) –** Funkcja heatmap umożliwia szybkie przedstawienie korelacji między wieloma zmiennymi w postaci kolorowej macierzy, co pomaga identyfikować silne powiązania.

**Łączenie wykresów i niestandardowe motywy –** Dzięki integracji z Matplotlib można tworzyć złożone układy wykresów, dodawać własne style oraz modyfikować elementy wykresów według potrzeb analitycznych lub prezentacyjnych.

**Wykresy czasowe i trendów z lineplot –** lineplot dobrze radzi sobie z danymi szeregowymi, automatycznie wygładzając serie i podkreślając trendy oraz zmiany w czasie.

**Eksploracja danych z brakami i outlierami –** Seaborn oferuje wykresy (np. boxplot, violinplot, scatterplot) ułatwiające zauważenie wartości odstających i wzorców braków danych, wspierając wczesną diagnozę jakości danych.

---

## Podsumowanie

- Seaborn: wysokopoziomowa biblioteka do wizualizacji danych
- Estetyka, intuicyjne API, integracja z Pandas i Matplotlib
- Obsługa wykresów statystycznych, kategorycznych, dystrybucji i macierzy
- Facetowanie i figure-level API ułatwiają analizę wielowymiarową
- Automatyczne mechanizmy statystyczne wspierają eksplorację danych
- Doskonałe narzędzie do szybkiej i profesjonalnej prezentacji wyników

## Źródła

(https://seaborn.pydata.org/api.html)
(https://seaborn.pydata.org/tutorial/function_overview.html)
(https://seaborn.pydata.org/generated/seaborn.PairGrid.html)
(https://realpython.com/python-seaborn/)
(https://www.geeksforgeeks.org/python/introduction-to-seaborn-python/)
Chat Gpt
