# GoAudit 11 — Rajd Wikinga

Landing pages imprezy **GoAudit 11 — Rajd Wikinga**, 13–15 listopada 2026 w Dzierżoniowie i na Górach Sowich.

Sześć kompletnych wariantów tej samej strony — identyczna treść merytoryczna, sześć różnych kierunków wizualnych. Wszystkie są statyczne (HTML + CSS + JS wbudowane), bez frameworka i bez build stepu.

## Warianty

| URL | Plik | Styl |
|---|---|---|
| `/wariant-01-ciemny.html` | `docs/wariant-01-ciemny.html` | **Ciemny cinematic** — czerń, czerwień, błękit; parallax hero, canvas z kurzem, animowana mapa OS |
| `/wariant-02-kreskowy.html` | `docs/wariant-02-kreskowy.html` | **Kreskowy** — papier, akwarela, ołówek; Caveat + Gaegu, polaroidy, ciepłe kolory |
| `/wariant-03-plakatowy.html` | `docs/wariant-03-plakatowy.html` | **Plakatowy (brutalizm)** — druk offsetowy; gruba czerń, czerwień, żółć, halfton |
| `/wariant-04-gazetka.html` | `docs/wariant-04-gazetka.html` | **Gazetka rajdowa** — program na papierze gazetowym; masthead, szeryfowe nagłówki, wieloszpaltowe artykuły, wkładka z OS, kupon zgłoszeniowy, archiwum prasy |
| `/wariant-05-terminal.html` | `docs/wariant-05-terminal.html` | **Terminal / timing board** — CRT z lat 80.; zielony fosfor na czarnym, scanlines, sekwencja bootu, drzewo trasy w ASCII, tablica wyników |
| `/wariant-06-rysunek.html` | `docs/wariant-06-rysunek.html` | **Rysunek techniczny** — blueprint; głęboki błękit, siatka, tablica rysunkowa, plan trasy ze strzałkami wymiarowymi, przekrój pionowy, harmonogram w formie wykresu Gantta |

`/` (index) to strona-hub z wyborem wariantu.

## Zawartość

- 12 sekcji: hero, impreza, trasa, harmonogram, klasy, Volvo Euro Cup, lista startowa, baza i serwis, wpisowe, galeria, FAQ, CTA + stopka
- Autorska mapa SVG trasy z animowanym rysowaniem 10 odcinków specjalnych i podświetlaniem na hover
- Harmonogram w 4 zakładkach (piątek / sobota / niedziela / odcinek testowy) z linkami do Google Maps
- 14 klas startowych z filtrem po grupach
- Dwa liczniki odliczające (do startu honorowego, do końca terminu I wpłaty)
- Galeria 13 zdjęć z lightboxem (strzałki + ESC)
- Pasek przełączania wariantów na dole każdej strony (6 wariantów)
- Wariant gazetkowy dodatkowo: spis treści w trzech szpaltach, kupon zgłoszeniowy do druku, archiwum prasy rajdowej
- Wariant terminalowy dodatkowo: sekwencja bootu z „PRESS ENTER", drzewo trasy w ASCII, tablica wyników z migającym polem czasu
- Wariant rysunkowy dodatkowo: plan trasy SVG z rysowaniem ścieżek, przekrój pionowy z profilem wysokości, harmonogram jako wykres Gantta z dwiema ścieżkami na dzień

## Struktura

```
.
├── docs/                      # publikowana strona
│   ├── index.html             # hub z wyborem wariantu
│   ├── wariant-01-ciemny.html
│   ├── wariant-02-kreskowy.html
│   ├── wariant-03-plakatowy.html
│   ├── wariant-04-gazetka.html
│   ├── wariant-05-terminal.html
│   ├── wariant-06-rysunek.html
│   └── assets/img/            # 20 zdjęć WebP
├── .github/workflows/pages.yml
└── README.md
```

## Publikacja

GitHub Actions → Pages (`build_type=workflow`). Każdy push do `main` w katalogu `docs/` republishuje stronę.

## Weryfikacja

- zero błędów JS w konsoli na wszystkich siedmiu stronach (hub + 6 wariantów)
- brak poziomego scrolla (sprawdzone w viewportach 1280 px i 390 px)
- wszystkie referencje do grafik i linki do Google Maps rozwiązane
- lightbox, zakładki harmonogramu, filtr klas i podświetlanie OS działają
- responsywność: breakpointy 960 / 940 / 920 / 900 / 880 / 860 / 760 / 720 / 680 / 640 / 620 / 560 / 520 px

## Źródło zdjęć

Oryginalne zdjęcia rajdu zostały zoptymalizowane do WebP (obrót EXIF, skalowanie, bez metadanych). Skrypt optymalizacji: `tools/build_images.py` w repozytorium roboczym.

## Dane organizacyjne

Organizator: **BGM Sport** (Szymon Mazur) we współpracy z **OSiR Dzierżoniów**, ul. Strumykowa 1.
Zapisy: <https://bgmsport.pl> — limit 120 załóg, wpisowe w I terminie (do 5 listopada) 2100 zł / 512 €.
