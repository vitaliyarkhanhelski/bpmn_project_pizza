# 🧮 Tabele decyzyjne - Proces produkcji mrożonej pizzy

## Tabela 1: Decyzja o akceptacji pizzy po kontroli jakości wizualnej

**Cel**: Określenie, czy pizza po nałożeniu toppingu powinna być przekazana do dalszej produkcji czy odrzucona.

**Reguła biznesowa**: BR-001

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** | **R5** | **R6** | **R7** | **R8** |
|---------------------|--------|--------|--------|--------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Pokrycie sosem ≥ 90% | TAK | TAK | TAK | TAK | NIE | TAK | NIE | NIE |
| Ser równomiernie rozłożony (brak pustych miejsc > 2 cm²) | TAK | TAK | NIE | TAK | TAK | NIE | NIE | TAK |
| Wszystkie składniki obecne | TAK | NIE | TAK | TAK | TAK | TAK | NIE | NIE |
| Brak elementów obcych | TAK | TAK | TAK | NIE | TAK | TAK | TAK | NIE |
| Ciasto nieuszkodzone | TAK | TAK | TAK | TAK | TAK | NIE | TAK | TAK |
| **AKCJE (OUTPUT)** |
| **Przekaż do zamrażania** | ✅ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ | ❌ |
| **Odrzuć produkt** | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Zatrzymaj linię** | ❌ | ❌ | ❌ | ✅ | ❌ | ❌ | ❌ | ✅ |
| **Analiza przyczyn (TO BE)** | ❌ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| **Kalibracja aplikatorów (TO BE)** | ❌ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ |

**Legenda**:
- R1: Pizza spełnia wszystkie standardy → AKCEPTACJA
- R2: Brak któregoś składnika → ODRZUCENIE + analiza aplikatora
- R3: Ser nierównomierny → ODRZUCENIE + kalibracja aplikatora sera
- R4: Element obcy → ODRZUCENIE + ZATRZYMANIE LINII (bezpieczeństwo)
- R5: Niedostateczne pokrycie sosem → ODRZUCENIE + kalibracja
- R6: Uszkodzone ciasto → ODRZUCENIE + analiza procesu formowania
- R7: Wiele niezgodności → ODRZUCENIE + kompleksowa analiza
- R8: Element obcy + wiele błędów → ODRZUCENIE + ZATRZYMANIE + audit linii

---

## Tabela 2: Decyzja po detekcji metalu

**Cel**: Określenie działań po wykryciu lub braku wykrycia metalu w produkcie.

**Reguła biznesowa**: BR-002

| **Warunek / Reguła** | **R1** | **R2** | **R3** |
|---------------------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Detektor wykrył metal | NIE | TAK | TAK |
| Kalibracja detektora wykonana < 2h temu | TAK | TAK | NIE |
| **AKCJE (OUTPUT)** |
| **Kontynuuj do pakowania** | ✅ | ❌ | ❌ |
| **Usuń produkt z linii** | ❌ | ✅ | ✅ |
| **Zatrzymaj linię produkcyjną** | ❌ | ✅ | ✅ |
| **Alarm dźwiękowy i wizualny** | ❌ | ✅ | ✅ |
| **Inspekcja linii produkcyjnej** | ❌ | ✅ | ✅ |
| **Rekalibracja detektora** | ❌ | ❌ | ✅ |
| **Rejestracja incydentu w QMS** | ❌ | ✅ | ✅ |
| **Powiadomienie kierownika** | ❌ | ✅ | ✅ |
| **Analiza poprzednich produktów** | ❌ | ✅ | ✅ |

**Legenda**:
- R1: Brak metalu, detektor skalibrowany → KONTYNUACJA
- R2: Wykryto metal, detektor OK → ODRZUCENIE + pełna procedura bezpieczeństwa
- R3: Wykryto metal, brak kalibracji → ODRZUCENIE + rekalibracja + sprawdzenie poprzednich produktów

---

## Tabela 3: Decyzja o akceptacji wagi produktu

**Cel**: Określenie, czy pizza spełnia normy wagowe i jaka akcja powinna być podjęta.

**Reguła biznesowa**: BR-003

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** | **R5** |
|---------------------|--------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Waga nominalna: 350 g (zakres: 332.5-367.5 g) |
| Waga zmierzona | 350 g | 340 g | 330 g | 370 g | 325 g |
| Waga w zakresie (332.5-367.5 g) | TAK | TAK | NIE | NIE | NIE |
| Liczba produktów poza normą w ostatniej godzinie | 0 | 1 | 2 | 1 | 5 |
| Trend odchyleń | Brak | Brak | Spadkowy | Wzrostowy | Chaotyczny |
| **AKCJE (OUTPUT)** |
| **Kontynuuj do pakowania** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Odrzuć produkt** | ❌ | ❌ | ✅ | ✅ | ✅ |
| **Kalibracja dozowników (TO BE)** | ❌ | ❌ | ✅ | ✅ | ✅ |
| **Alert do operatora** | ❌ | ❌ | ✅ | ✅ | ✅ |
| **Zatrzymaj linię do inspekcji** | ❌ | ❌ | ❌ | ❌ | ✅ |
| **Automatyczna analiza AI (TO BE)** | ❌ | ❌ | ✅ | ✅ | ✅ |

**Legenda**:
- R1: Waga idealna → AKCEPTACJA
- R2: Waga w normie, pojedyncze odchylenie → AKCEPTACJA (monitoring)
- R3: Waga poniżej normy, trend spadkowy → ODRZUCENIE + kalibracja
- R4: Waga powyżej normy, trend wzrostowy → ODRZUCENIE + kalibracja
- R5: Wiele odchyleń, brak trendu → ODRZUCENIE + ZATRZYMANIE + pełna inspekcja

---

## Tabela 4: Decyzja dotycząca temperatury zamrażania

**Cel**: Określenie działań w zależności od temperatury w tunelu zamrażającym.

**Reguła biznesowa**: BR-004

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** | **R5** |
|---------------------|--------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Temperatura nominalna: -33°C (zakres: -31°C do -35°C) |
| Temperatura zmierzona | -33°C | -36°C | -30°C | -28°C | -32°C |
| Temperatura w zakresie (-31°C do -35°C) | TAK | NIE (za nisko) | NIE (za wysoko) | NIE (krytycznie wysoko) | TAK |
| Czas trwania odchylenia | - | 5 min | 15 min | 30 min | - |
| Temperatura rdzenia pizzy po wyjściu | ≤ -18°C | ≤ -18°C | -16°C | -14°C | ≤ -18°C |
| **AKCJE (OUTPUT)** |
| **Kontynuuj proces** | ✅ | ❌ | ❌ | ❌ | ✅ |
| **Alert informacyjny** | ❌ | ✅ | ❌ | ❌ | ❌ |
| **Alert krytyczny** | ❌ | ❌ | ✅ | ✅ | ❌ |
| **Zwiększenie czasu zamrażania** | ❌ | ❌ | ✅ | ✅ | ❌ |
| **Wezwanie serwisu** | ❌ | ❌ | ✅ | ✅ | ❌ |
| **Zwrot produktu do tunelu** | ❌ | ❌ | ✅ | ✅ | ❌ |
| **Zatrzymanie linii** | ❌ | ❌ | ❌ | ✅ | ❌ |

**Legenda**:
- R1: Temperatura prawidłowa → KONTYNUACJA
- R2: Temperatura za niska (krótkotrwale) → ALERT (ryzyko uszkodzenia struktury produktu)
- R3: Temperatura za wysoka (15 min) → zwiększenie czasu, wezwanie serwisu
- R4: Temperatura krytycznie wysoka (30 min) → ZATRZYMANIE linii, produkty do ponownego zamrożenia
- R5: Temperatura OK, ale produkty mają nieprawidłową temp. rdzenia → kontrola tunelu

---

## Tabela 5: Decyzja o wysyłce produktu z magazynu

**Cel**: Określenie, czy produkt może zostać wysłany do sklepu na podstawie czasu przechowywania.

**Reguła biznesowa**: BR-007

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** | **R5** |
|---------------------|--------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Maksymalny czas w magazynie: 90 dni |
| Dni od produkcji | 20 | 60 | 82 | 91 | 95 |
| Dni w magazynie < 80 | TAK | TAK | NIE | NIE | NIE |
| Dni w magazynie > 90 | NIE | NIE | NIE | TAK | TAK |
| Kontrola QC przeprowadzona | - | - | - | TAK | NIE |
| Wynik kontroli QC | - | - | - | Pozytywny | - |
| **AKCJE (OUTPUT)** |
| **Wysłać (priorytet standardowy)** | ✅ | ✅ | ❌ | ❌ | ❌ |
| **Wysłać (priorytet wysoki - FEFO)** | ❌ | ❌ | ✅ | ❌ | ❌ |
| **Alert do działu sprzedaży (promocja)** | ❌ | ❌ | ✅ | ❌ | ❌ |
| **Blokada wysyłki** | ❌ | ❌ | ❌ | ✅ | ✅ |
| **Kontrola jakości wymagana** | ❌ | ❌ | ❌ | ✅ | ✅ |
| **Możliwa sprzedaż do outletu** | ❌ | ❌ | ❌ | ✅ | ❌ |
| **Utylizacja** | ❌ | ❌ | ❌ | ❌ | ✅ |

**Legenda**:
- R1: Produkt świeży (20 dni) → standardowa wysyłka
- R2: Produkt w normie (60 dni) → standardowa wysyłka
- R3: Produkt 82 dni → priorytet FEFO + promocja
- R4: Produkt 91 dni, QC pozytywny → możliwa sprzedaż do outletu (zniżka)
- R5: Produkt 95 dni, brak QC → UTYLIZACJA

---

## Tabela 6: Decyzja o akceptacji transportu

**Cel**: Określenie działań na podstawie temperatury podczas transportu.

**Reguła biznesowa**: BR-006

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** |
|---------------------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Temperatura nominalna: -18°C (zakres: -15°C do -21°C) |
| Temperatura podczas transportu | -18°C | -14°C | -13°C | -10°C |
| Czas przekroczenia temperatury > -15°C | 0 min | 20 min | 35 min | 60 min |
| Monitorowanie real-time (TO BE) | NIE | NIE | TAK | TAK |
| **AKCJE (OUTPUT)** |
| **Akceptuj dostawę** | ✅ | ✅ | ❌ | ❌ |
| **Alert do kierowcy** | ❌ | ✅ | ✅ | ✅ |
| **Alert do centrum dystrybucji** | ❌ | ❌ | ✅ | ✅ |
| **Kontrola produktów przy rozładunku** | ❌ | ✅ | ✅ | ✅ |
| **Możliwe odrzucenie partii** | ❌ | ❌ | ✅ | ✅ |
| **Reklamacja do przewoźnika** | ❌ | ❌ | ✅ | ✅ |
| **Powiadomienie sklepu (TO BE)** | ❌ | ❌ | ✅ | ✅ |

**Legenda**:
- R1: Temperatura prawidłowa przez cały transport → AKCEPTACJA
- R2: Krótkie przekroczenie (20 min) → AKCEPTACJA + kontrola przy rozładunku
- R3: Dłuższe przekroczenie (35 min) + monitoring real-time → alerty, kontrola, możliwe odrzucenie
- R4: Długie przekroczenie (60 min) → kontrola obowiązkowa, prawdopodobne odrzucenie, reklamacja

---

## Tabela 7: Decyzja o działaniach korygujących (TO BE - AI)

**Cel**: Automatyczna decyzja systemu AI o działaniach korygujących na podstawie wykrytych odchyleń.

**Reguła biznesowa**: BR-009

| **Warunek / Reguła** | **R1** | **R2** | **R3** | **R4** |
|---------------------|--------|--------|--------|--------|
| **WARUNKI (INPUT)** |
| Wzrost odrzutów w ciągu 1h | +10% | +25% | +40% | +60% |
| Przyczyna wykryta przez AI | TAK | TAK | NIE | NIE |
| Możliwa automatyczna kalibracja | TAK | TAK | NIE | NIE |
| Krytyczność problemu | Niska | Średnia | Wysoka | Krytyczna |
| **AKCJE (OUTPUT)** |
| **Automatyczna kalibracja** | ✅ | ✅ | ❌ | ❌ |
| **Alert do operatora** | ❌ | ✅ | ✅ | ✅ |
| **Alert do kierownika** | ❌ | ✅ | ✅ | ✅ |
| **Raport analizy przyczyn** | ✅ | ✅ | ✅ | ✅ |
| **Propozycja działań korygujących** | ✅ | ✅ | ✅ | ✅ |
| **Wezwanie serwisu** | ❌ | ❌ | ✅ | ✅ |
| **Zatrzymanie linii** | ❌ | ❌ | ❌ | ✅ |

**Legenda**:
- R1: Niewielki wzrost odrzutów, przyczyna znana → automatyczna kalibracja
- R2: Znaczący wzrost, przyczyna znana → kalibracja + alerty
- R3: Duży wzrost, przyczyna nieznana → alerty + wezwanie serwisu
- R4: Krytyczny wzrost → ZATRZYMANIE linii + pełna analiza

---

## 📊 Podsumowanie tabel decyzyjnych

| **Tabela** | **Temat** | **Liczba reguł** | **Powiązana BR** |
|-----------|-----------|-----------------|----------------|
| 1 | Kontrola jakości wizualnej | 8 | BR-001 |
| 2 | Detekcja metalu | 3 | BR-002 |
| 3 | Normy wagowe | 5 | BR-003 |
| 4 | Temperatura zamrażania | 5 | BR-004 |
| 5 | Wysyłka z magazynu | 5 | BR-007 |
| 6 | Akceptacja transportu | 4 | BR-006 |
| 7 | Działania korygujące AI (TO BE) | 4 | BR-009 |

**Zastosowanie**: Tabele decyzyjne mogą być bezpośrednio zaimplementowane w systemach automatycznych (DMN - Decision Model and Notation) lub systemach AI do podejmowania decyzji w czasie rzeczywistym.

