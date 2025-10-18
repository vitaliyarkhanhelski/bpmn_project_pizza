# ⚙️ Reguły biznesowe - Proces produkcji mrożonej pizzy

## 📌 Definicja reguł biznesowych

Reguły biznesowe to formalne ograniczenia lub wytyczne, które kierują działaniami, procesami decyzyjnymi i zachowaniami w organizacji podczas produkcji mrożonej pizzy.

---

## BR-001: Kontrola jakości wizualnej po toppingu

**Kategoria**: Kontrola jakości  
**Priorytet**: Wysoki  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Każda pizza po nałożeniu składników (topping) MUSI przejść kontrolę jakości wizualnej przed przekazaniem do zamrażania.

**Warunki**:
- Kontrola wykonywana przez pracownika (AS IS) lub system AI Vision (TO BE)
- Sprawdzane elementy:
  - Równomierne rozłożenie sosu (pokrycie min. 90% powierzchni)
  - Rozmieszczenie sera (bez pustych miejsc > 2 cm²)
  - Obecność wszystkich składników zgodnie z recepturą
  - Brak elementów obcych
  - Ciasto nie jest uszkodzone

**Akcje**:
- JEŚLI pizza spełnia standardy → przekaż do zamrażania
- JEŚLI pizza NIE spełnia standardów → usuń z linii produkcyjnej
- TO BE: Jeśli wykryto niezgodność → automatyczna analiza przyczyn i raport

**Odpowiedzialność**: Specjalista Kontroli Jakości / System AI (TO BE)

---

## BR-002: Detektor metali - zero tolerancji

**Kategoria**: Bezpieczeństwo produktu  
**Priorytet**: Krytyczny  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
KAŻDA pizza MUSI przejść przez detektor metali przed pakowaniem. Wykrycie jakiegokolwiek metalu skutkuje automatycznym odrzuceniem produktu.

**Warunki**:
- Czułość detektora: wykrywanie cząstek metalowych ≥ 1.5 mm (żelazo), ≥ 2.0 mm (stal nierdzewna)
- Test detektora: co 2 godziny (kalibracja)
- 100% produktów przechodzi przez detektor

**Akcje**:
- JEŚLI NIE wykryto metalu → kontynuuj do pakowania
- JEŚLI wykryto metal → 
  - Automatyczne usunięcie produktu z linii
  - Alarm dźwiękowy i wizualny
  - Zatrzymanie linii produkcyjnej
  - Analiza przyczyny (inspekcja linii)
  - Rejestracja incydentu w systemie QMS
  - TO BE: Automatyczna notyfikacja kierownika produkcji

**Odpowiedzialność**: System automatyczny + Kierownik Produkcji

**Dokumentacja**: Protokół zdarzenia, analiza przyczyn, działania korygujące

---

## BR-003: Normy wagowe produktu

**Kategoria**: Kontrola jakości  
**Priorytet**: Wysoki  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Każda pizza MUSI spełniać określone normy wagowe z tolerancją ±5% od wagi nominalnej.

**Warunki**:
- Waga nominalna pizzy: 350 g (przykład - zależna od rodzaju)
- Tolerancja: ±17.5 g (350 g ± 5%)
- Zakres akceptowalny: 332.5 g - 367.5 g
- Automatyczne ważenie każdej pizzy

**Akcje**:
- JEŚLI waga w normie (332.5-367.5 g) → kontynuuj do pakowania
- JEŚLI waga poniżej 332.5 g → 
  - Odrzuć produkt
  - AS IS: Ręczna analiza przyczyn
  - TO BE: Automatyczna kalibracja dozowników składników
- JEŚLI waga powyżej 367.5 g → 
  - Odrzuć produkt
  - AS IS: Ręczna analiza przyczyn
  - TO BE: Automatyczna kalibracja dozowników składników

**Akcje prewencyjne (TO BE)**:
- Jeśli 3 kolejne pizze poza normą → automatyczna kalibracja
- Jeśli trend wzrostowy/spadkowy → alert do operatora

**Odpowiedzialność**: System automatyczny + Specjalista Kontroli Jakości

---

## BR-004: Temperatura zamrażania

**Kategoria**: Proces technologiczny  
**Priorytet**: Krytyczny  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Pizza MUSI być zamrożona w tunelu chłodniczym o temperaturze -33°C (±2°C) przez minimum 20 minut.

**Warunki**:
- Temperatura tunelu: -33°C (zakres: -31°C do -35°C)
- Czas przebywania w tunelu: minimum 20 minut
- Temperatura rdzenia pizzy po zamrożeniu: ≤ -18°C
- Ciągły monitoring temperatury (TO BE: IoT sensors)

**Akcje**:
- JEŚLI temperatura tunelu < -35°C → alarm (za niskie, ryzyko uszkodzenia struktury)
- JEŚLI temperatura tunelu > -31°C → 
  - Alarm krytyczny
  - Zwiększenie czasu zamrażania
  - Wezwanie serwisu chłodniczego
- JEŚLI temperatura rdzenia pizzy > -18°C po wyjściu → 
  - Produkt wraca do tunelu
  - Analiza wydajności tunelu

**Odpowiedzialność**: System automatyczny + Technik chłodnictwa

---

## BR-005: Temperatura przechowywania w magazynie

**Kategoria**: Magazynowanie  
**Priorytet**: Wysoki  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Wszystkie gotowe produkty MUSZĄ być przechowywane w magazynie w temperaturze -23°C (±2°C).

**Warunki**:
- Temperatura magazynu: -23°C (zakres: -21°C do -25°C)
- Monitoring temperatury: co 30 minut (AS IS) / ciągły (TO BE - IoT)
- Automatyczne alarmy przy odchyleniu

**Akcje**:
- JEŚLI temperatura > -21°C → 
  - Alarm
  - Wezwanie serwisu
  - Jeśli > 2 godziny: ocena produktów pod kątem rozmrożenia
- JEŚLI temperatura < -25°C → alert informacyjny (zwiększone koszty energii)

**Odpowiedzialność**: Kierownik magazynu + System BMS (Building Management System)

---

## BR-006: Kontrola temperatury podczas transportu

**Kategoria**: Dystrybucja  
**Priorytet**: Wysoki  
**Status**: Aktywna (AS IS) / Rozszerzona (TO BE)

**Treść reguły**:  
Transport produktów MUSI odbywać się w warunkach kontrolowanej temperatury -18°C (±3°C).

**Warunki**:
- Temperatura w samochodzie chłodniczym: -18°C (zakres: -15°C do -21°C)
- AS IS: Monitoring przez rejestrator temperatury
- TO BE: Real-time monitoring GPS + temperatura + alerty

**Akcje**:
- JEŚLI temperatura > -15°C przez > 30 minut → 
  - Alert do kierowcy
  - Alert do centrum dystrybucji
  - Ocena produktów przy rozładunku
  - Możliwe odrzucenie partii
- TO BE: Automatyczne powiadomienie sklepu o problemie

**Odpowiedzialność**: Kierowca + Koordynator logistyki

---

## BR-007: Maksymalny czas przechowywania w magazynie

**Kategoria**: Zarządzanie zapasami  
**Priorytet**: Średni  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Produkty MOGĄ być przechowywane w magazynie maksymalnie 90 dni od daty produkcji. Stosowana jest zasada FEFO (First Expired, First Out).

**Warunki**:
- Maksymalny czas przechowywania: 90 dni
- Termin ważności produktu: 12 miesięcy od produkcji
- Zastosowanie FEFO przy kompletacji zamówień

**Akcje**:
- JEŚLI produkt > 80 dni w magazynie → 
  - Alert do działu sprzedaży (promocja)
  - Priorytet przy kompletacji zamówień
- JEŚLI produkt > 90 dni w magazynie → 
  - Blokada wysyłki
  - Ocena jakości przez QC
  - Możliwa utylizacja lub przekazanie do sprzedaży outletu

**Odpowiedzialność**: Kierownik magazynu + System WMS

---

## BR-008: Akceptacja surowców przychodzących

**Kategoria**: Zarządzanie surowcami  
**Priorytet**: Wysoki  
**Status**: Aktywna (AS IS i TO BE)

**Treść reguły**:  
Wszystkie surowce przychodzące MUSZĄ być sprawdzone i zaakceptowane przez Specjalistę QC przed dopuszczeniem do produkcji.

**Warunki**:
- Kontrola dokumentacji (certyfikaty, deklaracje zgodności)
- Kontrola organoleptyczna (wygląd, zapach, konsystencja)
- Kontrola temperatury (dla surowców mrożonych i schłodzonych)
- Kontrola terminu ważności (min. 30 dni do końca ważności przy przyjęciu)
- Pobieranie próbek kontrolnych

**Akcje**:
- JEŚLI surowce spełniają kryteria → 
  - Akceptacja w systemie
  - Przekazanie do magazynu surowców
  - Etykietowanie statusem "Zatwierdzone"
- JEŚLI surowce NIE spełniają kryteriów → 
  - Odrzucenie partii
  - Reklamacja do dostawcy
  - Kwarantanna + ewentualna utylizacja

**Odpowiedzialność**: Specjalista Kontroli Jakości

---

## BR-009: Automatyczna reakcja na odchylenia jakościowe (TO BE)

**Kategoria**: Kontrola jakości  
**Priorytet**: Wysoki  
**Status**: Projektowana (TO BE)

**Treść reguły**:  
System AI MUSI automatycznie wykrywać wzorce odchyleń jakościowych i inicjować działania korygujące.

**Warunki**:
- Ciągła analiza danych z kontroli jakości przez AI
- Wykrywanie trendów i anomalii
- Analiza korelacji (np. temperatura → jakość)

**Akcje**:
- JEŚLI wykryto wzrost odrzutów o > 20% w ciągu 1 godziny → 
  - Automatyczny alert do kierownika
  - Analiza przyczyny przez AI
  - Propozycja działań korygujących
- JEŚLI wykryto systematyczne odchylenie parametru → 
  - Automatyczna kalibracja maszyn (jeśli możliwa)
  - Dashboard z rekomendacjami

**Odpowiedzialność**: System AI + Kierownik Produkcji

---

## BR-010: Predykcyjne utrzymanie ruchu (TO BE)

**Kategoria**: Utrzymanie ruchu  
**Priorytet**: Średni  
**Status**: Projektowana (TO BE)

**Treść reguły**:  
System AI MUSI przewidywać awarie maszyn na podstawie danych z czujników IoT i historii eksploatacji.

**Warunki**:
- Ciągły monitoring parametrów maszyn (wibracje, temperatura, ciśnienie, prąd)
- Analiza predykcyjna oparta na ML
- Historia awarii i przeglądów

**Akcje**:
- JEŚLI prawdopodobieństwo awarii > 70% w ciągu 7 dni → 
  - Alert do działu utrzymania ruchu
  - Zaplanowanie przeglądu prewencyjnego
  - Przygotowanie części zamiennych
- JEŚLI wykryto anomalię w parametrach pracy → 
  - Alert w czasie rzeczywistym
  - Analiza przyczyny

**Odpowiedzialność**: System AI + Dział Utrzymania Ruchu

---

## 📊 Podsumowanie reguł

| **ID** | **Nazwa** | **Kategoria** | **Priorytet** | **Status** |
|--------|-----------|--------------|--------------|-----------|
| BR-001 | Kontrola jakości po toppingu | Jakość | Wysoki | AS IS / TO BE |
| BR-002 | Detektor metali | Bezpieczeństwo | Krytyczny | AS IS / TO BE |
| BR-003 | Normy wagowe | Jakość | Wysoki | AS IS / TO BE |
| BR-004 | Temperatura zamrażania | Proces | Krytyczny | AS IS / TO BE |
| BR-005 | Temperatura magazynowania | Magazyn | Wysoki | AS IS / TO BE |
| BR-006 | Temperatura transportu | Dystrybucja | Wysoki | AS IS / TO BE |
| BR-007 | Czas przechowywania | Zapasy | Średni | AS IS / TO BE |
| BR-008 | Akceptacja surowców | Jakość | Wysoki | AS IS / TO BE |
| BR-009 | Reakcja na odchylenia AI | Jakość | Wysoki | TO BE |
| BR-010 | Predykcyjne utrzymanie | Utrzymanie | Średni | TO BE |

