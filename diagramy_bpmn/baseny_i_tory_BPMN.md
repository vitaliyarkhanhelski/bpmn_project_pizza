# 🏊 Struktura basenów i torów - Proces produkcji mrożonej pizzy

## 🔄 AS IS vs TO BE - Kluczowa różnica: Outsourcing logistyki!

### AS IS (stan obecny): **3 baseny**
- Fabryka (z własnym transportem wewnątrz - tor) → Sklep → Klient
- Transport jest wewnętrznym torem fabryki (drogi, nieefektywny)

### TO BE (usprawnienie): **4 baseny**  
- Fabryka (bez transportu) → **Firma transportowa (OUTSOURCING!)** → Sklep → Klient
- Transport jest osobnym basenem (profesjonalna firma zewnętrzna)

**🎯 Główne usprawnienie**: Transport z toru wewnątrz fabryki → osobna firma transportowa (outsourcing!)

---

## 📊 Struktura AS IS (stan obecny - 3 baseny)

### 🏭 BASEN 1 (AS IS): Fabryka Iglotex - wszystko "in-house"

**Typ**: Organizacja produkcyjna  
**Odpowiedzialność**: Produkcja mrożonej pizzy od surowców do dostawy do sklepów  
**Problem**: Transport własny (drogi, nieefektywny, brak specjalizacji)

### Tory (Lanes):

1. **Dział Piekarni**
   - Odpowiedzialny za przygotowanie ciasta i spodów pizzy
   - Czynności: dozowanie składników, garowanie, kęsowanie, formowanie, prasowanie, pieczenie spodów

2. **Dział Toppingu**
   - Odpowiedzialny za nakładanie składników na pizzę
   - Czynności: chłodzenie spodów, nakładanie sosu, sera, warzyw, mięsa, doprawianie

3. **Dział Produkcji i Zamrażania**
   - Odpowiedzialny za zamrażanie produktu
   - Czynności: zamrażanie w tunelu (-33°C)

4. **Dział Kontroli Jakości**
   - Odpowiedzialny za monitorowanie i kontrolę jakości produktu
   - Czynności: kontrola wizualna, detektor metali, ważenie, weryfikacja norm

5. **Dział Pakowania**
   - Odpowiedzialny za pakowanie produktu
   - Czynności: foliowanie, obkurczanie folii, pakowanie do kartonów, paletyzacja

6. **Magazyn**
   - Odpowiedzialny za składowanie i przygotowanie do wysyłki
   - Czynności: magazynowanie w -23°C (manualne zarządzanie), wydanie do transportu własnego
   - Problem: Brak automatyzacji, ręczna rejestracja w WMS

7. **Dział Dystrybucji (transport własny)**
   - Odpowiedzialny za transport produktów do sklepów
   - Własne samochody ciężarowe
   - Własni kierowcy (pracownicy fabryki)
   - Czynności: planowanie tras, załadunek, transport, rozładunek w sklepach
   - Problem: Mała flota, stare samochody, brak GPS/monitoringu

**Output**: Dostawa do sklepu  
**End Event (Fabryka)**: Produkt dostarczony do sklepu

**→ Message Flow do Basenu 2 (Sklep)**

---

## 🏪 BASEN 2 (AS IS): Sklep detaliczny

**Typ**: Organizacja handlowa (klient B2B fabryki)  
**Odpowiedzialność**: Odbiór, składowanie i sprzedaż produktów

### Tory (Lanes):

1. **Dział Magazynowy Sklepu**
   - Odpowiedzialny za odbiór i składowanie
   - Czynności: przyjęcie dostawy, weryfikacja (manualna), składowanie w zamrażarce (-18°C), wystawienie na półki

**Input**: Dostawa od fabryki (własny transport fabryki)  
**Output**: Produkt dostępny dla klienta

**→ Message Flow do Basenu 3 (Klient)**

---

## 👤 BASEN 3 (AS IS): Klient końcowy

**Typ**: Konsument finalny  
**Odpowiedzialność**: Zakup i konsumpcja

### Tory (Lanes):

1. **Konsument**
   - Czynności: zakup w sklepie, transport do domu, przechowywanie, przygotowanie, konsumpcja

**Input**: Produkt ze sklepu  
**Output**: Konsumpcja (End Event)

---

## 🔄 Przepływ komunikatów (Message Flow) - AS IS

### Między Fabryką a Sklepem:
- **Sklep → Fabryka**: Zamówienie (telefon/fax/email)
- **Fabryka → Sklep**: Potwierdzenie zamówienia
- **Fabryka → Sklep**: Powiadomienie o dostawie (telefon)
- **Sklep → Fabryka**: Ewentualna reklamacja

### Między Sklepem a Klientem:
- **Sklep → Klient**: Dostępność produktu (produkt na półce)
- **Klient → Sklep**: Zakup (płatność)

**Problemy AS IS**:
- ❌ Brak profesjonalnego trackingu transportu
- ❌ Komunikacja głównie telefoniczna/papierowa
- ❌ Fabryka musi utrzymywać własną flotę
- ❌ Brak specjalizacji w logistyce

---

## 📊 Struktura TO BE (usprawnienie - 4 baseny)

### Główne usprawnienie: **Outsourcing logistyki!**

Fabryka **rezygnuje z własnego transportu** i wynajmuje profesjonalną firmę logistyczną.

---

## 🏭 BASEN 1 (TO BE): Fabryka Iglotex - Smart Factory

**Typ**: Organizacja produkcyjna  
**Odpowiedzialność**: Produkcja mrożonej pizzy od surowców do gotowych palet  
**ZMIANA**: Brak własnej dystrybucji - wszystko na outsourcing!

### Tory (Lanes):

1. **Dział Piekarni**
   - Czynności: dozowanie składników, garowanie, kęsowanie, formowanie, prasowanie, pieczenie spodów
   - TO BE: AI optymalizacja, IoT monitoring

2. **Dział Toppingu**
   - Czynności: chłodzenie, nakładanie składników (sos, ser, warzywa, mięso), doprawianie
   - TO BE: AI Vision kontrola jakości, automatyczna analiza odrzutów

3. **Dział Produkcji i Zamrażania**
   - Czynności: zamrażanie w tunelu (-33°C)
   - TO BE: IoT monitoring temperatury real-time

4. **Dział Kontroli Jakości**
   - Czynności: detektor metali, ważenie, kontrola rentgenem (TO BE)
   - TO BE: Automatyczna rejestracja wyników w QMS

5. **Dział Pakowania**
   - Czynności: foliowanie, kartonowanie, paletyzacja, etykietowanie RFID (TO BE)
   - TO BE: Robot paletyzujący, automatyczna owijarka

6. **Magazyn (Smart Warehouse)**
   - Czynności: składowanie, FEFO, przygotowanie wysyłki
   - TO BE: AGV, AS/RS, AI predykcja zapasów, automatyczna rejestracja RFID

**Output**: Palety gotowe do odbioru przez firmę transportową  
**End Event (Fabryka)**: Gotowe do przekazania firmie transportowej

---

## 🚚 BASEN 2 (TO BE): Firma transportowa/Logistyka - **NOWY! Outsourcing**

**Typ**: Organizacja transportowa zewnętrzna (profesjonalny przewoźnik)  
**Odpowiedzialność**: Transport produktów od fabryki do sklepów  
**Usprawnienie**: Specjalizacja, profesjonalny sprzęt, konkurencyjne ceny

### Tory (Lanes):

1. **Dział Transportu**
   - Profesjonalni kierowcy i flota firmy transportowej
   - Nowoczesne samochody z GPS + monitoring temperatury real-time
   - System TMS (Transport Management System)
   - Czynności: przyjęcie zlecenia API, załadunek, transport, monitoring, rozładunek
   - **Korzyści**: SLA, gwarancje, ubezpieczenie, tracking real-time

**Input**: Zlecenie transportowe od fabryki (Message Flow - API)  
**Output**: Dostawa produktów do sklepu + e-dokumenty (e-CMR)

---

## 🏪 BASEN 3 (TO BE): Sklep detaliczny

**Typ**: Organizacja handlowa (klient B2B)  
**Odpowiedzialność**: Odbiór, składowanie i sprzedaż produktów

### Tory (Lanes):

1. **Dział Magazynowy Sklepu**
   - Odpowiedzialny za odbiór i składowanie produktów
   - Czynności: weryfikacja dostawy, przyjęcie towaru, składowanie w zamrażarce (-18°C), wystawienie na półki

**Input**: Dostawa od firmy transportowej  
**Output**: Produkt dostępny dla klienta końcowego

---

## 👤 BASEN 4 (TO BE): Klient końcowy

**Typ**: Konsument finalny  
**Odpowiedzialność**: Zakup i konsumpcja produktu

### Tory (Lanes):

1. **Konsument**
   - Odpowiedzialny za zakup i przygotowanie pizzy
   - Czynności: wybór produktu, zakup, transport do domu, przechowywanie, przygotowanie

**Input**: Produkt ze sklepu  
**Output**: Konsumpcja (End Event)

---

## 🔄 Przepływ komunikatów (Message Flow) - TO BE

**Uwaga**: W TO BE więcej Message Flows niż w AS IS (4 baseny zamiast 3)

### Między Fabryką a Firmą transportową:
- **Fabryka → Transport**: Zlecenie transportu (zamówienie + dokumenty)
- **Transport → Fabryka**: Potwierdzenie odbioru + podpis CMR

### Między Firmą transportową a Sklepem:
- **Transport → Sklep**: Powiadomienie o dostawie (TO BE: automatyczne)
- **Sklep → Transport**: Potwierdzenie odbioru towaru + protokół
- **Sklep → Transport/Fabryka**: Ewentualna reklamacja (wada temperatury, uszkodzenia)

### Między Sklepem a Klientem:
- **Sklep → Klient**: Dostępność produktu, cena, promocje
- **Klient → Sklep**: Zakup (płatność)
- **Klient → Sklep/Fabryka**: Ewentualna reklamacja jakościowa

### Między Fabryką a Sklepem (bezpośrednio):
- **Sklep → Fabryka**: Zamówienie produktów (przez system B2B)
- **Fabryka → Sklep**: Potwierdzenie zamówienia + termin realizacji

---

## 📊 Systemy IT wspierające (w tle, nie jako baseny)

- **System ERP** (Fabryka) - zarządzanie produkcją
- **System MES** (Fabryka) - sterowanie linią
- **System QMS** (Fabryka) - zarządzanie jakością
- **System WMS** (Fabryka + Sklep) - zarządzanie magazynem
- **System TMS** (Firma transportowa) - zarządzanie transportem (TO BE)
- **System IoT** (Fabryka + Transport) - monitoring temperatury (TO BE)
- **System AI/ML** (Fabryka) - analiza i optymalizacja (TO BE)
- **System B2B** (Fabryka ↔ Sklep) - zamówienia

---

## 💰 Uzasadnienie biznesowe outsourcingu logistyki (AS IS → TO BE)

### Koszty w AS IS (transport własny):
- ❌ Własna flota samochodów (amortyzacja, ubezpieczenie)
- ❌ Zatrudnienie kierowców (pensje, szkolenia, ZUS)
- ❌ Utrzymanie samochodów (serwis, paliwo, opony)
- ❌ Brak specjalizacji (kierowcy to nie core business)
- ❌ Mała flota = sztywność (trudno skalować w szczycie)
- ❌ Stary sprzęt = awarie, brak monitoringu

### Korzyści TO BE (outsourcing):
- ✅ **-30% kosztów** (przewoźnik ma ekonomię skali)
- ✅ **Płacisz tylko za usługę** (brak amortyzacji floty)
- ✅ **Profesjonalny sprzęt** (nowe samochody, GPS, monitoring)
- ✅ **SLA gwarantowane** (kary za opóźnienia)
- ✅ **Elastyczność** (łatwo zwiększyć flotę w szczycie)
- ✅ **Fabryka skupia się na produkcji** (core business)
- ✅ **Konkurencja** (można zmienić przewoźnika)
- ✅ **Technologia** (TMS, GPS, IoT - od razu w pakiecie)

### Szacowane oszczędności:
- Transport własny (AS IS): ~2M PLN/rok
- Outsourcing (TO BE): ~1.4M PLN/rok
- **Oszczędność: 600k PLN/rok** 💰

---

## 📝 Uwagi dotyczące notacji BPMN

### AS IS (3 baseny):
- **Basen 1: Fabryka** (7 torów, w tym transport własny)
- **Basen 2: Sklep** (1 tor)
- **Basen 3: Klient** (1 tor)
- **Sequence Flow** wewnątrz każdego basenu
- **Message Flow** między basenami (Fabryka ↔ Sklep, Sklep ↔ Klient)
- Problem: Transport wewnątrz fabryki (tor), nie osobna firma

### TO BE (4 baseny):
1. **Baseny (Pools)** reprezentują różne organizacje - NIE MOŻNA między nimi używać Sequence Flow
2. **Message Flow** (przerywana linia) używany do komunikacji między basenami
3. **Tory (Lanes)** w obrębie basenu reprezentują role/działy w tej samej organizacji
4. **Sequence Flow** (ciągła linia) używany tylko WEWNĄTRZ basenu
5. Każdy basen może mieć własne Start Event i End Event(y)
6. **Outsourcing = nowy basen!** (inna organizacja)

---

## 🎯 Kluczowe punkty synchronizacji

1. **Fabryka → Transport**: Przekazanie palet + dokumenty CMR
2. **Transport → Sklep**: Dostawa + weryfikacja temperatury
3. **Sklep → Klient**: Sprzedaż

Każdy z tych punktów to **Message Flow** w BPMN!

