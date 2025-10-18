# 📦 Projekt BPMN - Produkcja mrożonej pizzy

## 📹 Materiał źródłowy
- **Temat**: Proces produkcji mrożonej pizzy w fabryce Iglotex
- **Źródło**: Filmik YouTube przedstawiający linię produkcyjną

---

## 📁 Struktura dokumentacji projektu

### 1. **baseny_i_tory_BPMN.md**
Definicja struktury diagramu BPMN (zgodnie z BPMN 2.0):
- **4 baseny (pools)** reprezentujące różne organizacje:
  1. Fabryka Iglotex (6 torów)
  2. Firma transportowa (1 tor)
  3. Sklep detaliczny (1 tor)
  4. Klient końcowy (1 tor)
- **Message Flows** między basenami (przepływ komunikatów)

### 2. **diagram_AS_IS_opis.md**
Szczegółowy opis diagramu BPMN AS IS (stan obecny):
- 4 baseny z zadaniami (tasks) w każdym basenie
- Bramki decyzyjne (gateways)
- Wydarzenia (events)
- Message Flows między basenami (8 przepływów komunikatów)
- Zidentyfikowane problemy (15 głównych, we wszystkich basenach)

### 3. **diagram_TO_BE_opis.md**
Szczegółowy opis diagramu BPMN TO BE (stan docelowy):
- 4 baseny z usprawnieniami w każdym
- Nowe technologie w każdym basenie: AI, IoT, robotyka, AGV, AS/RS, TMS, RFID
- Automatyzacja Message Flows (API, e-dokumenty)
- Lista usprawnień we wszystkich 4 basenach

### 4. **rejestr_procesow.md**
Kompleksowy rejestr procesu zawierający:
- Metadane procesu
- Cele biznesowe
- Interesariusze (15 ról)
- Mierniki KPI (10 wskaźników)
- Powiązane reguły biznesowe
- Podprocesy
- Systemy IT
- Ryzyka

### 5. **reguly_biznesowe.md**
10 reguł biznesowych:
- BR-001: Kontrola jakości po toppingu
- BR-002: Detektor metali (zero tolerancji)
- BR-003: Normy wagowe
- BR-004: Temperatura zamrażania
- BR-005: Temperatura magazynowania
- BR-006: Temperatura transportu
- BR-007: Czas przechowywania
- BR-008: Akceptacja surowców
- BR-009: Reakcja na odchylenia AI (TO BE)
- BR-010: Predykcyjne utrzymanie (TO BE)

### 6. **tabela_decyzyjna.md**
7 tabel decyzyjnych (Decision Tables):
1. Akceptacja pizzy po kontroli jakości (8 reguł)
2. Decyzja po detekcji metalu (3 reguły)
3. Akceptacja wagi produktu (5 reguł)
4. Temperatura zamrażania (5 reguł)
5. Wysyłka z magazynu (5 reguł)
6. Akceptacja transportu (4 reguły)
7. Działania korygujące AI (4 reguły, TO BE)

### 7. **analiza_AS_IS_vs_TO_BE.md**
Kompleksowa analiza porównawcza:
- Główne różnice (automatyzacja, monitoring, zarządzanie)
- 8 rozwiązanych problemów
- Korzyści finansowe (~1.5M PLN/rok)
- Korzyści operacyjne (wzrost wydajności +20%)
- ROI: 3.3 lata
- Plan wdrożenia (6 faz, 36 miesięcy)
- Kluczowe wskaźniki sukcesu

---

## 🎯 Cele projektu (spełnione)

✅ Diagram AS IS (szczegółowy opis tekstowy)  
✅ Diagram TO BE (szczegółowy opis tekstowy)  
✅ Rejestr procesów  
✅ Lista interesariuszy z rolami i komunikacją  
✅ Reguły biznesowe (10 reguł)  
✅ Tabele decyzyjne (7 tabel)  
✅ Analiza i weryfikacja (różnice AS IS vs TO BE)  

---

## 💡 Kluczowe usprawnienia w TO BE

1. **AI Vision** - automatyczna kontrola jakości
2. **IoT Sensors** - monitoring temperatury i parametrów w czasie rzeczywistym
3. **Robot paletyzujący** - automatyczna paletyzacja
4. **AGV** - bezzałogowe pojazdy transportowe
5. **AS/RS** - automatyczny system składowania
6. **RFID/QR** - pełne śledzenie produktów (100% traceability)
7. **Predykcyjne zarządzanie** - AI przewiduje zapotrzebowanie i awarie
8. **Real-time dashboard** - monitoring KPI na żywo
9. **Automatyczna analiza** - AI analizuje przyczyny odrzutów
10. **Smart logistics** - monitoring GPS + temperatura w transporcie

---

## 📊 Korzyści TO BE

**Finansowe**: ~1,500,000 PLN oszczędności rocznie  
**Wydajność**: +20% (z 10k do 12k pizz/dzień)  
**Jakość**: Redukcja odrzutów z 2% do 0.5% (-75%)  
**Czas cyklu**: Redukcja z 45 do 38 min (-15%)  
**Przestoje**: Redukcja z 8h do 5h/miesiąc (-37.5%)  
**ROI**: 3.3 lata przy inwestycji 5M PLN

---

## 🔧 Narzędzia do wizualizacji BPMN

Aby stworzyć graficzne diagramy BPMN na podstawie opisów, zalecane narzędzia:

1. **Camunda Modeler** (darmowe) - https://camunda.com/download/modeler/
2. **Bizagi Modeler** (darmowe) - https://www.bizagi.com/platform/modeler
3. **Draw.io** (darmowe) - https://app.diagrams.net/
4. **Lucidchart** (komercyjne)
5. **Signavio** (komercyjne)

---

## 📝 Uwagi

- Wszystkie opisy są zgodne ze standardem BPMN 2.0
- Dokumentacja zawiera pełne informacje do zaimplementowania diagramów w narzędziach BPMN
- Projekt spełnia wszystkie wymagania z wymagania_projektowe.md
- Reguły biznesowe i tabele decyzyjne mogą być zaimplementowane w DMN (Decision Model and Notation)

---

**Data**: 2025-10-17  
**Status**: Kompletny

