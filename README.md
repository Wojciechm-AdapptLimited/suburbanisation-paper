# Wpływ procesu suburbanizacji na proces formowania się rodzin na przykładzie Bydgoszczy i gmin ościennych

## O projekcie

Niniejsze repozytorium zawiera kod źródłowy artykułu naukowego analizującego wpływ procesu suburbanizacji na formowanie się rodzin w Bydgoszczy i gminach ościennych w powiecie bydgoskim (Białe Błota, Dąbrowa Chełmińska, Nowa Wieś Wielka, Osielsko, Sicienko, Solec Kujawski).

## Struktura repozytorium

```
suburbanisation-paper/
│
├── article/                    # Pliki artykułu LaTeX
│   ├── main.tex               # Główny plik źródłowy artykułu
│   ├── main.pdf               # Skompilowany PDF artykułu
│   ├── references.bib         # Bibliografia w formacie BibTeX
│   ├── elsarticle.cls         # Klasa dokumentu Elsevier
│   ├── elsarticle-harv.bst    # Styl bibliografii Harvard
│   └── img/                   # Wykresy i wizualizacje
│       ├── dzietnosc.png      # Współczynnik dzietności 2002-2024
│       ├── kolejnosc_urodzen.png  # Udział urodzeń wysokiej kolejności
│       ├── saldo_migracji.png     # Saldo migracji dla wybranych gmin
│       └── struktura-naplywow.png # Mapa struktury napływów (źródło: MFiPR)
│
├── data/                      # Surowe dane z GUS
│   ├── DBW_DB_*.csv          # Dane z Dziedzinowych Baz Wiedzy
│   └── LUDN_*.csv            # Dane demograficzne z BDL
│
├── src/                       # Kod źródłowy analizy
│   └── notebook.ipynb        # Jupyter Notebook z analizą danych w R
│
├── .gitignore                # Pliki ignorowane przez Git
└── README.md                 # Ten plik
```

### Opis katalogów

#### `article/`
Zawiera wszystkie pliki potrzebne do kompilacji artykułu w formacie LaTeX:
- Dokument główny napisany zgodnie z szablonem **Elsevier** (elsarticle)
- Bibliografia w formacie Harvard (elsarticle-harv)
- Wykresy i wizualizacje wygenerowane w R

#### `data/`
Surowe dane statystyczne pobrane z:
- **Bank Danych Lokalnych GUS** (https://bdl.stat.gov.pl/)
- **Dziedzinowe Bazy Wiedzy GUS** (https://dbw.stat.gov.pl/)
- **Baza Danych Demografia GUS** (https://demografia.stat.gov.pl/)

Pliki zawierają dane dotyczące:
- Salda migracji
- Liczby urodzeń i zawieranych małżeństw
- Współczynników dzietności
- Przyrostu naturalnego
- Struktury ludności

#### `src/`
Kod źródłowy analizy danych:
- **Jupyter Notebook** z kodem w języku **R**
- Wykorzystane biblioteki: `tidyverse`, `ggplot2`, `ggtext`, `showtext`, `kableExtra`
- Generowanie wykresów i tabel do artykułu
- Analiza eksploracyjna danych

## Wymagania

### Do kompilacji artykułu
- **LaTeX** (zalecane: TeXLive lub MikTeX)
- Kompilator **XeLaTeX**/**tectonic** (ze względu na wsparcie dla polskich czcionek)
- Klasa dokumentu `elsarticle` (zawarta w repozytorium)

### Do analizy danych
- **R** (wersja ≥ 4.0)
- **Jupyter Notebook** lub **JupyterLab**
- Kernel IRkernel dla R
- Pakiety R:
  - `tidyverse`
  - `ggplot2`
  - `ggrepel`
  - `ggtext`
  - `showtext`
  - `knitr`
  - `kableExtra`
  - `magrittr`

## Kompilacja artykułu

Aby skompilować artykuł do formatu PDF:

```bash
cd article
tectonic main.tex
```

Lub użyj swojego ulubionego edytora LaTeX (np. Overleaf, TeXShop, TeXstudio).

## Uruchomienie analizy

Aby odtworzyć analizę danych:

1. Zainstaluj wymagane pakiety R:
```r
install.packages(c("tidyverse", "ggrepel", "ggtext", "showtext", "knitr", "kableExtra", "magrittr"))
```

2. Otwórz notebook:
```bash
cd src
jupyter notebook notebook.ipynb
```

3. Uruchom wszystkie komórki, aby wygenerować wykresy.

## Źródła danych

Wszystkie dane wykorzystane w artykule pochodzą z **Głównego Urzędu Statystycznego**:

- [Bank Danych Lokalnych](https://bdl.stat.gov.pl/bdl/start) - dane na poziomie gmin
- [Dziedzinowe Bazy Wiedzy](https://dbw.stat.gov.pl/) - dane szczegółowe o urodzeń
- [Baza Danych Demografia](https://demografia.stat.gov.pl/) - prognozy demograficzne

## Licencja

Kod źródłowy i analiza danych są dostępne na licencji open source. Dane pochodzące z GUS podlegają warunkom użytkowania określonym przez Główny Urząd Statystyczny.

## Autor

**Wojciech Mączka**  
Instytut Socjologii, Uniwersytet Jagielloński  
Kraków, Polska