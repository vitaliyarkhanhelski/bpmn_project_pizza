# 🍕 Projekt BPMN - Proces produkcji mrożonej pizzy

## 📋 O projekcie

Projekt modelowania procesu biznesowego w notacji BPMN na podstawie rzeczywistego procesu produkcji mrożonej pizzy w fabryce Iglotex.

---

## 📹 Materiał źródłowy

**Temat**: Proces produkcji mrożonej pizzy  
**Źródło**: Filmik YouTube przedstawiający linię produkcyjną w fabryce Iglotex  
**Zakres**: Pełny proces od przygotowania ciasta do dystrybucji do sklepów

---

## 📁 Struktura projektu

```
projekt_produkcja_mrozonej_pizzy/
│
├── README.md                      ← Ty jesteś tutaj (start)
│
├── 📂 dokumentacja/               (Dokumentacja główna)
│   ├── quick_reference.md         (Szybki przewodnik - wszystko w 1 miejscu)
│   ├── informacje_o_projekcie.md  (Spis treści, podsumowanie)
│   └── podsumowanie_wykonawcze.md (Executive Summary dla zarządu)
│
├── 📂 diagramy_bpmn/              (Diagramy BPMN)
│   ├── baseny_i_tory_BPMN.md      (Struktura AS IS vs TO BE)
│   ├── diagram_AS_IS_opis.md      (3 baseny - transport własny w fabryce)
│   ├── diagram_TO_BE_opis.md      (4 baseny - outsourcing logistyki!)
│   └── schemat_procesu_tekstowy.md (Wizualizacja ASCII)
│
├── 📂 szczegoly_procesu/          (Szczegóły procesu)
│   ├── rejestr_procesow.md        (Metadane, KPI, ryzyka)
│   ├── lista_interesariuszy.md    (19 interesariuszy + RACI)
│   ├── reguly_biznesowe.md        (10 reguł BR-001 do BR-010)
│   ├── tabela_decyzyjna.md        (7 tabel decyzyjnych)
│   └── analiza_AS_IS_vs_TO_BE.md  (Porównanie, ROI, plan wdrożenia)
│
├── 📂 opis_projektu/              (Opisy źródłowe z filmu)
│   ├── opis1.md                   (Opis procesu - wersja 1)
│   ├── opis2.md                   (Opis procesu - wersja 2)
│   └── opis_podsumowanie.md       (Szczegółowy opis etapów)
│
└── 📂 materialy_wejsciowe/        (Materiały wstępne)
    ├── wymagania_projektowe.md    (Specyfikacja zadania)
    ├── wstepny_plan.md            (Wstępny plan procesu)
    └── wstepne_baseny_tory.md     (Wstępne baseny - zaktualizowane)
```

### 🚀 Quick Start

1. **Chcesz szybki przegląd?** → [`dokumentacja/quick_reference.md`](dokumentacja/quick_reference.md)
2. **Chcesz zobaczyć strukturę BPMN?** → [`diagramy_bpmn/baseny_i_tory_BPMN.md`](diagramy_bpmn/baseny_i_tory_BPMN.md)
3. **Chcesz executive summary?** → [`dokumentacja/podsumowanie_wykonawcze.md`](dokumentacja/podsumowanie_wykonawcze.md)

---

## 🏊 Struktura BPMN - Kluczowa różnica AS IS vs TO BE

### AS IS (stan obecny): **3 baseny**
1. 🏭 **Fabryka Iglotex** (7 torów - transport własny wewnątrz):
   - Piekarnia, Topping, Produkcja, Kontrola, Pakowanie, Magazyn, **Dystrybucja**
   - Problem: Transport własny (stare auta, brak GPS, drogie)

2. 🏪 **Sklep detaliczny** (1 tor)
   - Odbiór, weryfikacja manualna, składowanie

3. 👤 **Klient końcowy** (1 tor)
   - Zakup, konsumpcja

**⚡ Message Flow AS IS**: Telefon/fax (prymitywna komunikacja)

---

### TO BE (usprawnienie): **4 baseny**
**🎯 Główne usprawnienie: Outsourcing logistyki!**

1. 🏭 **Fabryka Iglotex** (6 torów - **BEZ** transportu):
   - Piekarnia, Topping, Produkcja, Kontrola, Pakowanie, Magazyn
   - AI, IoT, robotyzacja

2. 🚚 **Firma transportowa** (1 tor) - **NOWY! Outsourcing!**
   - Profesjonalny przewoźnik
   - GPS real-time, TMS, SLA, monitoring temp.
   - 💰 **Oszczędność: -600k PLN/rok**

3. 🏪 **Sklep detaliczny** (1 tor)
   - Odbiór (RFID auto-scan), e-potwierdzenie

4. 👤 **Klient końcowy** (1 tor)
   - Zakup, QR traceability, online opinions

**⚡ Message Flow TO BE**: API, GPS tracking, e-dokumenty (smart communication)

---

### 📊 Porównanie:
| Aspekt | AS IS (3 baseny) | TO BE (4 baseny) | Korzyść |
|--------|------------------|------------------|---------|
| **Transport** | Wewnątrz fabryki (tor) | Osobna firma (basen) | Outsourcing! |
| **Koszty transportu** | 2M PLN/rok | 1.4M PLN/rok | **-600k PLN** |
| **Monitoring** | Brak | GPS + temp real-time | ✅ |
| **Specjalizacja** | Brak | Profesjonalna firma | ✅ |
| **Komunikacja** | Telefon/fax | API, e-dokumenty | ✅ |

---

## 🎯 Zrealizowane wymagania

| Wymaganie | Status | Plik |
|-----------|--------|------|
| Diagram AS IS | ✅ | `diagram_AS_IS_opis.md` |
| Diagram TO BE | ✅ | `diagram_TO_BE_opis.md` |
| Rejestr procesów | ✅ | `rejestr_procesow.md` |
| Interesariusze | ✅ | `rejestr_procesow.md` (sekcja 4) |
| Reguły biznesowe | ✅ | `reguly_biznesowe.md` (10 reguł) |
| Tabela decyzyjna | ✅ | `tabela_decyzyjna.md` (7 tabel) |
| Analiza i weryfikacja | ✅ | `analiza_AS_IS_vs_TO_BE.md` |

---

## 💡 Kluczowe usprawnienia (AS IS → TO BE)

| Obszar | AS IS | TO BE | Korzyść |
|--------|-------|-------|---------|
| Kontrola jakości | Manualna | AI Vision | +99.5% wykrywalności |
| Paletyzacja | Ręczna (12 min) | Robot (4 min) | 3x szybciej |
| Monitoring temp. | Co 30 min | Real-time IoT | Natychmiastowa reakcja |
| Śledzenie produktu | Numer partii | QR/RFID na każdej pizzy | 100% traceability |
| Zarządzanie zapasami | Reaktywne | Predykcyjne AI | -70% braków |
| Transport | Podstawowy | GPS + temp. + alerty | -80% strat |
| Utrzymanie ruchu | Według grafiku | Predykcyjne | -40% przestojów |

---

## 📊 Kluczowe wskaźniki

### AS IS
- Wydajność: **10,000 pizz/dzień**
- Odrzuty: **2%**
- Czas cyklu: **45 min**
- OEE: **75%**
- Przestoje: **8h/miesiąc**

### TO BE (cele)
- Wydajność: **12,000 pizz/dzień** (+20%)
- Odrzuty: **0.5%** (-75%)
- Czas cyklu: **38 min** (-15%)
- OEE: **85%** (+10pp)
- Przestoje: **5h/miesiąc** (-37.5%)

---

## 💰 Aspekty finansowe

**Inwestycja w TO BE**: ~5,000,000 PLN  
**Oszczędności roczne**: ~1,500,000 PLN  
**ROI (zwrot inwestycji)**: ~3.3 lata  

### Składowe oszczędności:
- Redukcja odrzutów: 500k PLN
- Oszczędność pracy: 300k PLN
- Redukcja przestojów: 250k PLN
- Mniejsze straty w transporcie: 150k PLN
- Optymalizacja energii: 100k PLN
- Lepsza prognoza zapasów: 200k PLN

---

## 🛠️ Narzędzia do wizualizacji

Aby stworzyć graficzne diagramy BPMN na podstawie przygotowanych opisów:

### Darmowe narzędzia:
1. **Camunda Modeler** - https://camunda.com/download/modeler/
2. **Bizagi Modeler** - https://www.bizagi.com/platform/modeler
3. **Draw.io** (diagrams.net) - https://app.diagrams.net/

### Komercyjne:
4. **Lucidchart** - https://www.lucidchart.com/
5. **Signavio** - https://www.sap.com/signavio

**Instrukcja**:
1. Otwórz wybrany edytor BPMN
2. **AS IS**: Stwórz 3 Pools (Fabryka z 7 torami, Sklep, Klient)
3. **TO BE**: Stwórz 4 Pools (Fabryka z 6 torami, Firma transportowa, Sklep, Klient)
4. Zaimplementuj zadania, bramki i wydarzenia zgodnie z opisami
5. Dodaj Message Flows między basenami (szczegóły w `baseny_i_tory_BPMN.md`)

---

## 📖 Jak czytać dokumentację

### Krok 0: Szybki start (5 minut)
👉 [`dokumentacja/quick_reference.md`](dokumentacja/quick_reference.md) - wszystko w jednym miejscu!

### Krok 1: Przeczytaj ogólne informacje
👉 `README.md` (ten plik) i [`dokumentacja/informacje_o_projekcie.md`](dokumentacja/informacje_o_projekcie.md)

### Krok 2: Zrozum strukturę procesu
👉 [`diagramy_bpmn/baseny_i_tory_BPMN.md`](diagramy_bpmn/baseny_i_tory_BPMN.md) - struktura AS IS (3 baseny) vs TO BE (4 baseny)

### Krok 3: Poznaj AS IS (stan obecny - transport własny)
👉 [`diagramy_bpmn/diagram_AS_IS_opis.md`](diagramy_bpmn/diagram_AS_IS_opis.md) - szczegółowy opis każdego kroku

### Krok 4: Poznaj TO BE (stan docelowy - outsourcing logistyki!)
👉 [`diagramy_bpmn/diagram_TO_BE_opis.md`](diagramy_bpmn/diagram_TO_BE_opis.md) - usprawnienia i nowe technologie

### Krok 5: Zgłęb szczegóły
👉 [`szczegoly_procesu/rejestr_procesow.md`](szczegoly_procesu/rejestr_procesow.md) - metadane, KPI, ryzyka  
👉 [`szczegoly_procesu/reguly_biznesowe.md`](szczegoly_procesu/reguly_biznesowe.md) - 10 reguł biznesowych  
👉 [`szczegoly_procesu/tabela_decyzyjna.md`](szczegoly_procesu/tabela_decyzyjna.md) - 7 tabel decyzyjnych

### Krok 6: Zrozum korzyści
👉 [`szczegoly_procesu/analiza_AS_IS_vs_TO_BE.md`](szczegoly_procesu/analiza_AS_IS_vs_TO_BE.md) - porównanie, ROI, plan wdrożenia

---

## 🔍 Reguły biznesowe (skrót)

| ID | Nazwa | Priorytet | Status |
|----|-------|-----------|--------|
| BR-001 | Kontrola jakości po toppingu | Wysoki | AS IS/TO BE |
| BR-002 | Detektor metali | Krytyczny | AS IS/TO BE |
| BR-003 | Normy wagowe | Wysoki | AS IS/TO BE |
| BR-004 | Temperatura zamrażania | Krytyczny | AS IS/TO BE |
| BR-005 | Temperatura magazynowania | Wysoki | AS IS/TO BE |
| BR-006 | Temperatura transportu | Wysoki | AS IS/TO BE |
| BR-007 | Czas przechowywania | Średni | AS IS/TO BE |
| BR-008 | Akceptacja surowców | Wysoki | AS IS/TO BE |
| BR-009 | Reakcja na odchylenia AI | Wysoki | TO BE |
| BR-010 | Predykcyjne utrzymanie | Średni | TO BE |

---

## 📋 Tabele decyzyjne (skrót)

1. **Akceptacja pizzy po kontroli** - 8 reguł decyzyjnych
2. **Detekcja metalu** - 3 reguły (zero tolerancji)
3. **Normy wagowe** - 5 reguł (zakres 332.5-367.5g)
4. **Temperatura zamrażania** - 5 reguł (-33°C ±2°C)
5. **Wysyłka z magazynu** - 5 reguł (max 90 dni, FEFO)
6. **Akceptacja transportu** - 4 reguły (-18°C ±3°C)
7. **Działania korygujące AI** - 4 reguły (TO BE)

---

## 👥 Interesariusze

**Wewnętrzni**:
- Dyrektor Produkcji
- Kierownik Działu Piekarni
- Kierownik Działu Toppingu
- Operator linii produkcyjnej
- Specjalista Kontroli Jakości
- Pracownik magazynu
- Kierowca-dostawca

**Zewnętrzni**:
- Dostawca surowców
- Sklepy detaliczne
- Klient końcowy

**Systemy**:
- ERP, WMS, QMS, MES
- IoT Platform (TO BE)
- AI/ML Platform (TO BE)
- TMS (TO BE)

---

## 📅 Plan wdrożenia TO BE

| Faza | Czas | Zakres | Koszt |
|------|------|--------|-------|
| 1. Quick Wins | 3-6 m | IoT, raportowanie | 500k PLN |
| 2. Kontrola jakości | 6-12 m | AI Vision, rentgen | 1.2M PLN |
| 3. Robotyzacja | 12-18 m | Robot, RFID | 1.5M PLN |
| 4. Smart Warehouse | 18-24 m | AGV, AS/RS, AI | 1.8M PLN |
| 5. Smart Logistics | 24-30 m | GPS, TMS | 500k PLN |
| 6. Predykcyjne UTR | 30-36 m | IoT, AI awarii | 500k PLN |

**Całość**: 36 miesięcy, 5M PLN

---

## ✅ Status projektu

**Dokumentacja**: ✅ Kompletna (100%)  
**Zgodność z wymaganiami**: ✅ Wszystkie wymagania spełnione  
**Jakość opisów BPMN**: ✅ Zgodne ze standardem BPMN 2.0  
**Reguły biznesowe**: ✅ 10 reguł szczegółowo opisanych  
**Tabele decyzyjne**: ✅ 7 tabel gotowych do implementacji DMN  
**Analiza**: ✅ Pełna analiza AS IS vs TO BE  

---

## 📝 Uwagi końcowe

- Projekt spełnia wszystkie wymagania z `wymagania_projektowe.md`
- Opisy są wystarczająco szczegółowe do stworzenia graficznych diagramów BPMN
- Reguły biznesowe i tabele decyzyjne mogą być zaimplementowane jako DMN
- Wszystkie usprawnienia TO BE są realistyczne i technologicznie dostępne
- ROI 3.3 lata jest akceptowalny dla tego typu inwestycji

---

**Data utworzenia**: 2025-10-17  
**Autorzy**: Zespół projektowy  
**Wersja**: 1.0  
**Status**: Gotowy do prezentacji

