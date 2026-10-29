# GoAudit 11 — Rajd Wikinga

Landing pages imprezy **GoAudit 11 — Rajd Wikinga**, 13–15 listopada 2026 w Dzierżoniowie i na Górach Sowich.

Trzy kompletne warianty tej samej strony — identyczna treść merytoryczna, trzy różne kierunki wizualne. Wszystkie są statyczne (HTML + CSS + JS wbudowane), bez frameworka i bez build stepu.

## Warianty

| URL | Plik | Styl |
|---|---|---|
| `/wariant-01-ciemny.html` | `docs/wariant-01-ciemny.html` | **Ciemny cinematic** — czerń, czerwień, błękit; parallax hero, canvas z kurzem, animowana mapa OS |
| `/wariant-02-kreskowy.html` | `docs/wariant-02-kreskowy.html` | **Kreskowy** — papier, akwarela, ołówek; Caveat + Gaegu, polaroidy, ciepłe kolory |
| `/wariant-03-plakatowy.html` | `docs/wariant-03-plakatowy.html` | **Plakatowy (brutalizm)** — druk offsetowy; gruba czerń, czerwień, żółć, halfton |

`/` (index) to strona-hub z wyborem wariantu.

## Zawartość

- 12 sekcji: hero, impreza, trasa, harmonogram, klasy, Volvo Euro Cup, lista startowa, baza i serwis, wpisowe, galeria, FAQ, CTA + stopka
- Autorska mapa SVG trasy z animowanym rysowaniem 10 odcinków specjalnych i podświetlaniem na hover
- Harmonogram w 4 zakładkach (piątek / sobota / niedziela / odcinek testowy) z linkami do Google Maps
- 14 klas startowych z filtrem po grupach
- Dwa liczniki odliczające (do startu honorowego, do końca terminu I wpłaty)
- Galeria 13 zdjęć z lightboxem (strzałki + ESC)
- Pasek przełączania wariantów na dole każdej strony

## Struktura

```
.
├── docs/                      # publikowana strona
│   ├── index.html             # hub z wyborem wariantu
│   ├── wariant-01-ciemny.html
│   ├── wariant-02-kreskowy.html
│   ├── wariant-03-plakatowy.html
│   └── assets/img/            # 20 zdjęć WebP
├── .github/workflows/pages.yml
└── README.md
```

## Publikacja

GitHub Actions → Pages (`build_type=workflow`). Każdy push do `main` w katalogu `docs/` republishuje stronę.

## Weryfikacja

- zero błędów JS w konsoli na wszystkich czterech stronach
- brak poziomego scrolla (sprawdzone w viewportach 1280 px i 390 px)
- wszystkie referencje do grafik i linki do Google Maps rozwiązane
- lightbox, zakładki harmonogramu, filtr klas i podświetlanie OS działają
- responsywność: breakpointy 960 / 940 / 860 / 760 / 720 / 620 / 560 / 520 px

## Źródło zdjęć

Oryginalne zdjęcia rajdu zostały zoptymalizowane do WebP (obrót EXIF, skalowanie, bez metadanych). Skrypt optymalizacji: `tools/build_images.py` w repozytorium roboczym.

## Dane organizacyjne

Organizator: **BGM Sport** (Szymon Mazur) we współpracy z **OSiR Dzierżoniów**, ul. Strumykowa 1.
Zapisy: <https://bgmsport.pl> — limit 120 załóg, wpisowe w I terminie (do 5 listopada) 2100 zł / 512 €.
