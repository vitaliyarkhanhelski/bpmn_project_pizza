# 📋 Rejestr procesów - Produkcja mrożonej pizzy

## Proces główny

| **Parametr** | **Wartość** |
|-------------|------------|
| **ID procesu** | PROC-001 |
| **Nazwa procesu** | Proces produkcji mrożonej pizzy w fabryce Iglotex |
| **Wersja** | AS IS: 1.0, TO BE: 2.0 |
| **Opis** | Kompleksowy proces produkcyjny obejmujący przygotowanie ciasta, nakładanie składników, pieczenie, zamrażanie, kontrolę jakości, pakowanie, magazynowanie i dystrybucję mrożonych pizz |
| **Cel procesu** | Wyprodukowanie wysokiej jakości mrożonej pizzy zgodnie ze standardami bezpieczeństwa żywności i oczekiwaniami klientów |
| **Kategoria** | Proces produkcyjny |
| **Typ** | Proces podstawowy (core process) |
| **Właściciel procesu** | Dyrektor Produkcji |
| **Status AS IS** | Aktywny (wymaga usprawnienia) |
| **Status TO BE** | Projektowany (wdrożenie w fazie planowania) |
| **Data utworzenia** | 2025-10-17 |
| **Data ostatniej aktualizacji** | 2025-10-17 |

---

## Cele biznesowe procesu

1. **Jakość**: Produkcja pizzy spełniającej wszystkie standardy jakościowe (ISO 22000, HACCP)
2. **Efektywność**: Wydajność produkcji min. 10 000 sztuk pizzy dziennie
3. **Bezpieczeństwo**: Zero zanieczyszczeń metalicznych w produkcie finalnym
4. **Koszty**: Optymalizacja kosztów produkcji przy zachowaniu jakości
5. **Zgodność**: 100% zgodność z normami wagowymi (±5% tolerancji)
6. **Ślad**: Pełna identyfikowalność produktu (traceability) od surowca do półki sklepowej

---

## Interesariusze procesu

| **Rola** | **Typ** | **Odpowiedzialność** | **Komunikacja** |
|---------|---------|---------------------|----------------|
| Dyrektor Produkcji | Wewnętrzny | Zarządzanie całym procesem produkcyjnym | System ERP, spotkania |
| Kierownik Działu Piekarni | Wewnętrzny | Nadzór nad przygotowaniem ciasta | System produkcyjny, raporty |
| Kierownik Działu Toppingu | Wewnętrzny | Nadzór nad nakładaniem składników | System produkcyjny, raporty |
| Operator linii produkcyjnej | Wewnętrzny | Monitorowanie maszyn i linii | Panel sterowania, komunikatory |
| Specjalista Kontroli Jakości | Wewnętrzny | Weryfikacja standardów jakości | System QMS, protokoły |
| Pracownik magazynu | Wewnętrzny | Składowanie i wydawanie produktów | System WMS, terminal RF |
| Kierowca-dostawca | Wewnętrzny/Zewnętrzny | Transport produktów do sklepów | System GPS, dokumenty CMR |
| Dostawca surowców | Zewnętrzny | Dostarczanie składników (mąka, ser, warzywa) | E-mail, EDI, telefon |
| Sklepy detaliczne | Zewnętrzny | Odbiór i sprzedaż produktów | System B2B, zamówienia |
| Klient końcowy | Zewnętrzny | Konsument finalny produktu | - |
| System ERP | System | Zarządzanie zleceniami produkcyjnymi | API, integracje |
| System WMS | System | Zarządzanie magazynem | API, RFID |
| System QMS | System | Zarządzanie jakością | API, czujniki |
| System IoT | System | Monitoring parametrów produkcji | Czujniki, MQTT |
| System AI (TO BE) | System | Optymalizacja i kontrola | API, ML modele |

---

## Mierniki procesu (KPI)

| **KPI** | **Jednostka** | **Wartość docelowa** | **Częstotliwość pomiaru** |
|---------|--------------|---------------------|-------------------------|
| Wydajność produkcji | sztuk/dzień | ≥ 10 000 | Dzienna |
| Wskaźnik wadliwości | % | ≤ 2% | Dzienna |
| Czas cyklu produkcyjnego | minuty | ≤ 45 min | Ciągła |
| Zgodność wagowa | % | ≥ 98% | Ciągła |
| Czas przestoju linii | godziny/miesiąc | ≤ 8 h | Miesięczna |
| Efektywność OEE | % | ≥ 85% | Dzienna |
| Koszty produkcji jednostkowej | PLN/sztuka | optymalizacja | Miesięczna |
| Czas dostawy do sklepu | godziny | ≤ 24 h | Per dostawa |
| Temperatura produktu | °C | -18°C ± 3°C | Ciągła |
| Satisfaction rate (sklepy) | skala 1-5 | ≥ 4.5 | Miesięczna |

---

## Powiązane reguły biznesowe

- **BR-001**: Kontrola jakości po toppingu
- **BR-002**: Detektor metali - zero tolerancji
- **BR-003**: Normy wagowe produktu
- **BR-004**: Temperatura zamrażania
- **BR-005**: Temperatura przechowywania
- **BR-006**: Kontrola temperatury transportu
- **BR-007**: Czas przechowywania w magazynie
- **BR-008**: Akceptacja surowców
- **BR-009**: Reakcja na odchylenia jakościowe (TO BE)
- **BR-010**: Predykcyjne utrzymanie ruchu (TO BE)

---

## Podprocesy

1. **PROC-001.1**: Przygotowanie ciasta i spodów pizzy
2. **PROC-001.2**: Nakładanie toppingu
3. **PROC-001.3**: Zamrażanie i pakowanie
4. **PROC-001.4**: Kontrola jakości
5. **PROC-001.5**: Magazynowanie
6. **PROC-001.6**: Dystrybucja
7. **PROC-001.7**: Analiza i raportowanie (TO BE)

---

## Systemy i narzędzia

| **System** | **Funkcja** | **Dostawca** | **Wersja** |
|-----------|-----------|-------------|-----------|
| ERP | Zarządzanie produkcją i zasobami | SAP / Infor | AS IS |
| WMS | Zarządzanie magazynem | Manhattan / SAP EWM | AS IS |
| QMS | Zarządzanie jakością | TraceGains / Sparta | AS IS |
| MES | Manufacturing Execution System | Siemens / Rockwell | AS IS |
| IoT Platform | Monitoring czujników | AWS IoT / Azure IoT | TO BE |
| AI/ML Platform | Analiza predykcyjna | TensorFlow / Azure ML | TO BE |
| TMS | Transport Management System | Oracle / SAP TM | TO BE |
| RFID System | Śledzenie produktów | Zebra / Impinj | TO BE |

---

## Dokumentacja powiązana

- Instrukcje stanowiskowe dla operatorów
- Standardy jakościowe ISO 22000
- Procedury HACCP
- Protokoły kontroli jakości
- Specyfikacje surowców
- Karty technologiczne produktów
- Procedury postępowania z produktem niezgodnym
- Plan utrzymania ruchu
- Procedury BHP i bezpieczeństwa pożarowego

---

## Ryzyka procesu

| **ID** | **Ryzyko** | **Prawdopodobieństwo** | **Wpływ** | **Mitygacja** |
|--------|-----------|----------------------|----------|--------------|
| R-001 | Awaria linii produkcyjnej | Średnie | Wysokie | Utrzymanie ruchu, części zamienne |
| R-002 | Zanieczyszczenie metaliczne | Niskie | Krytyczne | Detektor metali, procedury |
| R-003 | Awaria chłodni | Niskie | Wysokie | Systemy rezerwowe, alarmy |
| R-004 | Niedobór surowców | Średnie | Wysokie | Zapasy bezpieczeństwa, wielu dostawców |
| R-005 | Przekroczenie norm wagowych | Średnie | Średnie | Kalibracja dozowników |
| R-006 | Awaria transportu | Niskie | Średnie | Ubezpieczenie, backup przewoźnicy |
| R-007 | Nieprawidłowa temperatura | Niskie | Wysokie | Monitoring IoT (TO BE), alarmy |

---

## Historia zmian

| **Wersja** | **Data** | **Autor** | **Opis zmian** |
|-----------|---------|----------|---------------|
| 1.0 (AS IS) | 2025-10-17 | Zespół projektowy | Dokumentacja stanu obecnego |
| 2.0 (TO BE) | 2025-10-17 | Zespół projektowy | Projektowanie usprawnieńautomatyzacja, IoT, AI |

---

## Uwagi

- Proces oparty na rzeczywistej linii produkcyjnej w fabryce Iglotex
- Materiał źródłowy: filmik YouTube przedstawiający proces produkcji
- Wersja TO BE wymaga inwestycji w robotyzację, IoT i AI
- Planowany czas wdrożenia TO BE: 18-24 miesiące
- ROI (Return on Investment) dla TO BE: szacowany na 3-4 lata

