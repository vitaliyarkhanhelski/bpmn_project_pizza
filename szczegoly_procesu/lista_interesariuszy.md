# 👥 Lista interesariuszy - Proces produkcji mrożonej pizzy

## Interesariusze wewnętrzni

### 1. Dyrektor Produkcji

**Typ**: Osoba - Zarządzający  
**Odpowiedzialność**:
- Ogólne zarządzanie procesem produkcyjnym
- Nadzór nad wszystkimi działami produkcyjnymi
- Podejmowanie decyzji strategicznych
- Odpowiedzialność za KPI produkcji

**Komunikacja**:
- System ERP - przeglądanie raportów, zatwierdzanie zleceń
- Spotkania zarządcze - cotygodniowe
- Dashboard produkcyjny (TO BE) - real-time monitoring
- Email i telefon - komunikacja operacyjna

**Zaangażowanie w proces**: Wysoki poziom (strategiczne decyzje)

---

### 2. Kierownik Działu Piekarni

**Typ**: Osoba - Manager  
**Odpowiedzialność**:
- Nadzór nad przygotowaniem ciasta i spodów pizzy
- Zarządzanie zespołem operatorów piekarni
- Monitoring jakości spodów
- Optymalizacja procesów garowania i pieczenia

**Komunikacja**:
- System produkcyjny MES - monitoring linii
- Raporty dzienne - dla Dyrektora Produkcji
- Radio/telefon - komunikacja z operatorami
- Briefing shift - na początku każdej zmiany

**Zaangażowanie w proces**: Dzienny, operacyjny (Lane 1)

---

### 3. Kierownik Działu Toppingu

**Typ**: Osoba - Manager  
**Odpowiedzialność**:
- Nadzór nad nakładaniem składników
- Kontrola jakości wizualnej
- Zarządzanie aplikatorami automatycznymi
- Optymalizacja receptur

**Komunikacja**:
- System produkcyjny MES - monitoring aplikatorów
- System QMS - rejestrowanie odrzutów
- Radio/telefon - komunikacja z zespołem
- Briefing shift - na początku każdej zmiany

**Zaangażowanie w proces**: Dzienny, operacyjny (Lane 2)

---

### 4. Operator linii produkcyjnej

**Typ**: Osoba - Wykonawca  
**Odpowiedzialność**:
- Monitoring pracy maszyn i urządzeń
- Reagowanie na alarmy
- Podstawowa kontrola jakości (wizualna)
- Drobne regulacje parametrów

**Komunikacja**:
- Panel sterowania HMI - obsługa maszyn
- Radio - komunikacja z kierownikami
- System MES - rejestrowanie zdarzeń
- Protokoły papierowe - niektóre zapisy (AS IS)

**Liczba**: ~12 operatorów na zmianę  
**Zaangażowanie w proces**: Ciągłe, wszystkie lane

---

### 5. Specjalista Kontroli Jakości

**Typ**: Osoba - Kontroler  
**Odpowiedzialność**:
- Kontrola jakości produktu na różnych etapach
- Weryfikacja zgodności z normami (waga, temperatura)
- Rejestrowanie niezgodności
- Analiza przyczyn odrzutów (AS IS)
- Kontrola surowców przychodzących

**Komunikacja**:
- System QMS - rejestracja wyników kontroli
- Protokoły kontroli - dokumentacja
- Email - raportowanie do zarządu
- TO BE: Dashboard AI - analiza automatyczna

**Liczba**: 3-4 specjalistów na zmianę  
**Zaangażowanie w proces**: Lane 2, 4 + kontrola surowców

---

### 6. Pracownik magazynu / Magazynier

**Typ**: Osoba - Wykonawca  
**Odpowiedzialność**:
- Przyjęcie gotowych palet z produkcji
- Składowanie w odpowiedniej lokalizacji
- Utrzymanie temperatury -23°C
- Kompletacja zamówień do wysyłki
- Rejestracja w systemie WMS (AS IS)

**Komunikacja**:
- System WMS - rejestracja stanów
- Terminal RF (AS IS) / RFID (TO BE) - skanowanie
- Wózek widłowy - transport palet
- Radio - komunikacja z zespołem

**Liczba**: 4-6 magazynierów na zmianę  
**Zaangażowanie w proces**: Lane 6

---

### 7. Technik utrzymania ruchu

**Typ**: Osoba - Serwisant  
**Odpowiedzialność**:
- Przeglądy techniczne maszyn
- Naprawa awarii
- Kalibracja urządzeń (wagi, dozowniki)
- Wymiana części zamiennych
- TO BE: Predykcyjne utrzymanie ruchu

**Komunikacja**:
- System CMMS (Computerized Maintenance Management System)
- Zlecenia pracy - od kierowników
- TO BE: System IoT - alerty o anomaliach
- Radio/telefon - komunikacja operacyjna

**Liczba**: 2-3 techników na zmianę  
**Zaangażowanie w proces**: Support dla wszystkich lane

---

### 8. Kierowca-dostawca

**Typ**: Osoba - Wykonawca / Zewnętrzny kontraktor  
**Odpowiedzialność**:
- Transport produktów do sklepów
- Utrzymanie łańcucha chłodniczego (-18°C)
- Rozładunek w sklepach
- Dokumentacja CMR

**Komunikacja**:
- Dokumenty przewozowe - papierowe/elektroniczne
- System GPS - śledzenie trasy
- TO BE: System TMS - zlecenia transportowe, alerty
- Telefon - komunikacja z centrum dystrybucji

**Liczba**: ~10-20 kierowców  
**Zaangażowanie w proces**: Lane 7

---

### 9. Koordynator logistyki

**Typ**: Osoba - Planista  
**Odpowiedzialność**:
- Planowanie tras dostaw
- Koordynacja z kierowcami
- Monitoring temperatury w transporcie
- Komunikacja ze sklepami

**Komunikacja**:
- System TMS (TO BE) - planowanie tras
- Telefon/email - komunikacja z kierowcami i sklepami
- Excel/ERP - planowanie (AS IS)

**Liczba**: 2-3 koordynatorów  
**Zaangażowanie w proces**: Lane 7

---

## Interesariusze zewnętrzni

### 10. Dostawca surowców

**Typ**: Firma zewnętrzna  
**Kategorie**:
- Dostawca mąki
- Dostawca nabiału (ser mozzarella)
- Dostawca warzyw (pieczarki, cebula)
- Dostawca mięsa (szynka)
- Dostawca opakowań (folia, kartony)

**Odpowiedzialność**:
- Dostawa surowców zgodnie z harmonogramem
- Zapewnienie jakości surowców
- Certyfikaty bezpieczeństwa żywności
- Stabilność cen i dostaw

**Komunikacja**:
- Email - zamówienia, potwierdzenia
- EDI (Electronic Data Interchange) - automatyczna wymiana dokumentów
- Telefon - komunikacja operacyjna
- Portal B2B - dla większych dostawców
- TO BE: API - automatyczne zamówienia na podstawie AI

**Częstotliwość**: Dzienne dostawy (mąka, nabiał), 2-3x/tydzień (warzywa, mięso)

---

### 11. Sklepy detaliczne (sieci handlowe)

**Typ**: Klient B2B  
**Kategorie**:
- Hipermarkety (Carrefour, Auchan)
- Supermarkety (Biedronka, Lidl, Kaufland)
- Dyskonty (Aldi, Netto)
- Sklepy convenience

**Odpowiedzialność**:
- Składanie zamówień
- Odbiór dostaw
- Składowanie w zamrażarkach sklepowych
- Sprzedaż do klientów końcowych
- Zgłaszanie reklamacji

**Komunikacja**:
- System B2B - składanie zamówień online
- EDI - automatyczna wymiana zamówień i potwierdzeń
- Email - komunikacja operacyjna
- Telefon - pilne sprawy, reklamacje
- TO BE: API + automatyczne powiadomienia o dostawie

**Częstotliwość**: Zamówienia 1-3x/tydzień, dostawy codzienne/co 2 dni

---

### 12. Klient końcowy (konsument)

**Typ**: Osoba fizyczna  
**Odpowiedzialność**:
- Zakup pizzy w sklepie
- Przygotowanie według instrukcji
- Ewentualne reklamacje (poprzez sklep lub producenta)

**Komunikacja**:
- Opakowanie produktu - instrukcje, informacje
- Infolinia producenta - reklamacje, pytania
- Social media - opinie, feedback
- Strona www producenta

**Częstotliwość**: Jednorazowy/okresowy zakup

---

## Systemy IT (interesariusze systemowi)

### 13. System ERP (Enterprise Resource Planning)

**Typ**: System informatyczny  
**Przykłady**: SAP, Microsoft Dynamics, Infor  
**Odpowiedzialność**:
- Zarządzanie zleceniami produkcyjnymi
- Planowanie materiałów (MRP)
- Zarządzanie zapasami (surowce + produkty gotowe)
- Finanse i księgowość
- Zarządzanie zamówieniami od klientów

**Komunikacja**:
- API/OData - integracja z MES, WMS, TMS
- Użytkownicy - planista produkcji, księgowość, sprzedaż
- Raporty - dla zarządu

**Zaangażowanie**: Całościowe zarządzanie przedsiębiorstwem

---

### 14. System MES (Manufacturing Execution System)

**Typ**: System informatyczny  
**Przykłady**: Siemens Opcenter, Rockwell FactoryTalk  
**Odpowiedzialność**:
- Sterowanie linią produkcyjną
- Monitoring maszyn w czasie rzeczywistym
- Zbieranie danych produkcyjnych
- Śledzenie wydajności (OEE)
- Alarmy i powiadomienia

**Komunikacja**:
- PLC (Programmable Logic Controllers) - bezpośrednia kontrola maszyn
- API - integracja z ERP, QMS
- HMI (Human-Machine Interface) - panele operatorskie
- TO BE: IoT sensors - rozszerzony monitoring

**Zaangażowanie**: Lane 1-5 (produkcja)

---

### 15. System WMS (Warehouse Management System)

**Typ**: System informatyczny  
**Przykłady**: Manhattan, SAP EWM  
**Odpowiedzialność**:
- Zarządzanie lokalizacjami w magazynie
- Rejestracja przyjęć i wydań
- Optymalizacja tras kompletacji
- Inwentaryzacja
- FEFO (First Expired, First Out)

**Komunikacja**:
- Terminale RF - skanowanie kodów kreskowych (AS IS)
- TO BE: RFID readers - automatyczna rejestracja
- API - integracja z ERP, TMS
- AGV (TO BE) - sterowanie pojazdami bezzałogowymi

**Zaangażowanie**: Lane 6 (magazyn)

---

### 16. System QMS (Quality Management System)

**Typ**: System informatyczny  
**Przykłady**: TraceGains, Sparta Systems  
**Odpowiedzialność**:
- Rejestracja wyników kontroli jakości
- Zarządzanie niezgodnościami
- Śledzenie certyfikatów dostawców
- Procedury HACCP
- Raporty jakościowe

**Komunikacja**:
- Terminale/tablety - wprowadzanie danych przez QC
- TO BE: API - automatyczne dane z AI Vision, wag, detektorów
- Integracja z ERP - raporty
- Protokoły PDF - dokumentacja

**Zaangażowanie**: Lane 2, 4, kontrola surowców

---

### 17. System TMS (Transport Management System) - TO BE

**Typ**: System informatyczny  
**Przykłady**: Oracle Transportation Management, SAP TM  
**Odpowiedzialność**:
- Planowanie tras dostaw
- Optymalizacja załadunku
- Śledzenie GPS pojazdów
- Monitoring temperatury w transporcie
- Automatyczne powiadomienia

**Komunikacja**:
- GPS - lokalizacja pojazdów
- Czujniki temperatury - monitoring łańcucha chłodniczego
- API - integracja z WMS, ERP
- Powiadomienia - email/SMS do sklepów

**Zaangażowanie**: Lane 7 (dystrybucja)

---

### 18. Platforma IoT (Internet of Things) - TO BE

**Typ**: System informatyczny  
**Przykłady**: AWS IoT, Azure IoT Hub, Google Cloud IoT  
**Odpowiedzialność**:
- Zbieranie danych z czujników (temperatura, wilgotność, wibracje)
- Monitoring w czasie rzeczywistym
- Alerty przy przekroczeniu norm
- Big Data storage
- Integracja z systemami analitycznymi

**Komunikacja**:
- MQTT - protokół komunikacji z czujnikami
- API - integracja z MES, AI/ML
- Dashboard - wizualizacja dla operatorów

**Zaangażowanie**: Wszystkie lane (monitoring temperatury, maszyn)

---

### 19. System AI/ML (Artificial Intelligence / Machine Learning) - TO BE

**Typ**: System informatyczny  
**Przykłady**: TensorFlow, Azure ML, AWS SageMaker  
**Odpowiedzialność**:
- AI Vision - kontrola jakości wizualna
- Predykcyjne zarządzanie zapasami
- Predykcyjne utrzymanie ruchu
- Automatyczna analiza przyczyn odrzutów
- Optymalizacja parametrów produkcji

**Komunikacja**:
- API - integracja z MES, QMS, WMS
- Kamery - input dla AI Vision
- Czujniki IoT - dane do predykcji
- Dashboard - rekomendacje dla zarządu

**Zaangażowanie**: Lane 2 (kontrola), Lane 6 (zapasy), Lane 8 (analityka)

---

## Mapa komunikacji interesariuszy

```
                    ┌─────────────────┐
                    │  Dyrektor       │
                    │  Produkcji      │
                    └────────┬────────┘
                             │
            ┌────────────────┼────────────────┐
            │                │                │
     ┌──────▼──────┐  ┌─────▼──────┐  ┌─────▼──────┐
     │ Kierownik   │  │ Kierownik  │  │ Koordynator│
     │ Piekarni    │  │ Toppingu   │  │ Logistyki  │
     └──────┬──────┘  └─────┬──────┘  └─────┬──────┘
            │               │                │
     ┌──────▼──────┐  ┌─────▼──────┐  ┌─────▼──────┐
     │ Operatorzy  │  │ Spec. QC   │  │ Kierowcy   │
     │ linii       │  │            │  │            │
     └─────────────┘  └────────────┘  └────────────┘
            │               │                │
            └───────────────┼────────────────┘
                           │
                    ┌──────▼──────┐
                    │  Magazynier │
                    └──────┬──────┘
                           │
                    ┌──────▼──────┐
                    │   Sklepy    │
                    └──────┬──────┘
                           │
                    ┌──────▼──────┐
                    │   Klienci   │
                    └─────────────┘

     Systemy IT: [ERP] ←→ [MES] ←→ [QMS]
                           ↕
                 [WMS] ←→ [TMS] (TO BE)
                   ↕
           [IoT Platform] ←→ [AI/ML] (TO BE)
```

---

## Matryca RACI (Odpowiedzialność)

| Aktywność | Dyrektor | Kier. Piekarni | Kier. Topping | Operator | QC | Magazynier | Kierowca |
|-----------|----------|----------------|---------------|----------|----|-----------| ---------|
| Zlecenie produkcji | A | C | C | I | I | I | - |
| Przygotowanie ciasta | I | A | - | R | - | - | - |
| Nakładanie toppingu | I | - | A | R | C | - | - |
| Kontrola jakości | C | I | I | I | A/R | - | - |
| Pakowanie | I | - | - | R | C | - | - |
| Magazynowanie | I | - | - | - | C | A/R | - |
| Transport | C | - | - | - | - | I | A/R |

**Legenda RACI**:
- **R** (Responsible) - Odpowiedzialny za wykonanie
- **A** (Accountable) - Rozliczany z wyniku (tylko jedna osoba)
- **C** (Consulted) - Konsultowany
- **I** (Informed) - Informowany

---

## Podsumowanie

**Liczba interesariuszy**: 19 (12 ludzkich ról + 7 systemów)  
**Kluczowi interesariusze**: Dyrektor Produkcji, Kierownicy działów, Specjaliści QC  
**Główne systemy**: ERP, MES, QMS, WMS  
**TO BE - nowe systemy**: TMS, IoT Platform, AI/ML Platform  

**Komunikacja**: Przede wszystkim elektroniczna (systemy IT), wspomagana komunikacją bezpośrednią (radio, telefon, spotkania)

**TO BE**: Zwiększona automatyzacja komunikacji (API, IoT, AI), redukcja komunikacji manualnej

