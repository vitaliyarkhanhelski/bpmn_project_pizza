# 📊 Diagram BPMN AS IS - Proces produkcji mrożonej pizzy

## Opis struktury diagramu (Stan obecny)

### Struktura: 4 baseny (pools) reprezentujące różne organizacje

---

# 🏭 BASEN 1: Fabryka Iglotex

## Lane 1.1: Dział Piekarni

**Start Event:** Otrzymanie zlecenia produkcyjnego (z systemu ERP)

**Task 1.1:** Automatyczne dozowanie składników ciasta (mąka, woda, drożdże, olej)
- Typ: Service Task (automatyczne)

**Task 1.2:** Mieszanie składników w mieszalniku
- Typ: Service Task (automatyczne)

**Task 1.3:** Dzielenie ciasta (kęsowanie)
- Typ: Service Task (automatyczne)

**Task 1.4:** Formowanie ciasta w kulki
- Typ: Service Task (automatyczne)

**Task 1.5:** Pierwsze garowanie ciasta
- Typ: Service Task (automatyczne, z timerem)

**Task 1.6:** Prasowanie na gorąco
- Typ: Service Task (automatyczne)

**Task 1.7:** Drugie garowanie
- Typ: Service Task (automatyczne, z timerem)

**Task 1.8:** Prasowanie i nakłuwanie ciasta
- Typ: Service Task (automatyczne)

**Task 1.9:** Pieczenie spodu (270-300°C)
- Typ: Service Task (automatyczne)

**Task 1.10:** Odbiór spodów przez robota
- Typ: Service Task (automatyczne)

**→ Sequence Flow do Lane 1.2 (Dział Toppingu)**

---

## Lane 1.2: Dział Toppingu

**Task 2.1:** Chłodzenie spodów pizzy
- Typ: Service Task (automatyczne)

**Task 2.2:** Nakładanie sosu pomidorowego
- Typ: Service Task (automatyczne, aplikator)

**Task 2.3:** Nakładanie mozzarelli
- Typ: Service Task (automatyczne, aplikator)

**Task 2.4:** Nakładanie pieczarek
- Typ: Service Task (automatyczne, aplikator)

**Task 2.5:** Nakładanie cebuli
- Typ: Service Task (automatyczne, aplikator)

**Task 2.6:** Nakładanie szynki
- Typ: Service Task (automatyczne, aplikator)

**Task 2.7:** Doprawianie ziołami
- Typ: Service Task (automatyczne)

**Task 2.8:** Aplikacja mgiełki wodnej (wiązanie składników)
- Typ: Service Task (automatyczne)

**Task 2.9:** Kontrola wizualna jakości przez pracownika
- Typ: User Task (manualne)

**Gateway (Exclusive):** Czy pizza spełnia standardy jakości?
- **TAK** → Sequence Flow do Lane 1.3
- **NIE** → End Event (Odrzucenie wadliwego produktu)

**→ Sequence Flow do Lane 1.3 (Dział Produkcji)**

---

## Lane 1.3: Dział Produkcji i Zamrażania

**Task 3.1:** Zamrażanie w tunelu (-33°C, min 20 minut)
- Typ: Service Task (automatyczne, z timerem)

**→ Sequence Flow do Lane 1.4 (Kontrola Jakości)**

---

## Lane 1.4: Dział Kontroli Jakości

**Task 4.1:** Przejście przez detektor metali
- Typ: Service Task (automatyczne)

**Gateway (Exclusive):** Czy wykryto metal?
- **TAK** → End Event (Odrzucenie + Alarm + Zatrzymanie linii)
- **NIE** → Kontynuacja

**Task 4.2:** Ważenie pizzy
- Typ: Service Task (automatyczne)

**Gateway (Exclusive):** Czy waga jest w normie (332.5-367.5g dla pizzy 350g)?
- **TAK** → Kontynuacja
- **NIE** → End Event (Odrzucenie + Manualna analiza przyczyn)

**→ Sequence Flow do Lane 1.5 (Pakowanie)**

---

## Lane 1.5: Dział Pakowania

**Task 5.1:** Pakowanie w folię
- Typ: Service Task (automatyczne)

**Task 5.2:** Przejście przez gorący tunel (obkurczanie folii)
- Typ: Service Task (automatyczne)

**Task 5.3:** Pakowanie do kartonów zbiorczych
- Typ: Service Task (semi-automatyczne)

**Task 5.4:** Układanie kartonów na paletach
- Typ: User Task (manualne, ciężka praca)

**Task 5.5:** Owijanie palet folią stretch
- Typ: User Task (manualne)

**→ Sequence Flow do Lane 1.6 (Magazyn)**

---

## Lane 1.6: Magazyn

**Task 6.1:** Transport palet do magazynu głównego
- Typ: User Task (wózek widłowy)

**Task 6.2:** Składowanie w temperaturze -23°C
- Typ: User Task

**Task 6.3:** Rejestracja w systemie WMS
- Typ: User Task (manualne wprowadzanie danych)

**Task 6.4:** Przechowywanie (FEFO - First Expired, First Out)
- Typ: Timer Event (oczekiwanie na zamówienie)

**Intermediate Event (Message):** Otrzymanie zamówienia od sklepu (przez system B2B/telefon)

**Task 6.5:** Przygotowanie palet do wysyłki
- Typ: User Task

**Task 6.6:** Przygotowanie dokumentów wysyłkowych
- Typ: User Task

**End Event (Fabryka):** Gotowe do przekazania firmie transportowej

**→ Message Flow do Basenu 2 (Firma transportowa)**  
   *Wysłanie: Zlecenie transportu + Dokumenty CMR + Szczegóły dostawy*

---

# 🚚 BASEN 2: Firma transportowa/Logistyka

## Lane 2.1: Dział Transportu

**Start Event (Message):** Otrzymanie zlecenia transportu od fabryki

**Task 7.1:** Przyjęcie zlecenia i planowanie trasy
- Typ: User Task

**Task 7.2:** Przygotowanie dokumentów przewozowych (CMR)
- Typ: User Task

**Task 7.3:** Dojazd do fabryki
- Typ: Service Task

**Task 7.4:** Załadunek palet na samochód chłodniczy
- Typ: User Task (wózek widłowy fabryki lub kierowca)

**Task 7.5:** Potwierdzenie odbioru (podpis CMR)
- Typ: User Task

**→ Message Flow do Basenu 1 (Fabryka)**  
   *Wysłanie: Potwierdzenie odbioru*

**Task 7.6:** Transport do sklepu (monitoring temperatury -18°C ±3°C)
- Typ: Service Task
- Problem AS IS: Brak monitoringu real-time, tylko rejestrator

**Task 7.7:** Dojazd do sklepu
- Typ: Service Task

**End Event (Transport):** Przygotowany do rozładunku

**→ Message Flow do Basenu 3 (Sklep)**  
   *Wysłanie: Powiadomienie o przyjeździe (telefon/SMS)*

---

# 🏪 BASEN 3: Sklep detaliczny

## Lane 3.1: Dział Magazynowy Sklepu

**Start Event (Message):** Powiadomienie o dostawie od firmy transportowej

**Task 8.1:** Przyjęcie dostawy
- Typ: User Task

**Task 8.2:** Weryfikacja dokumentów (CMR, faktura)
- Typ: User Task

**Task 8.3:** Kontrola ilościowa (liczba kartonów)
- Typ: User Task

**Task 8.4:** Kontrola jakościowa wizualna
- Typ: User Task

**Gateway (Exclusive):** Czy dostawa jest zgodna?
- **TAK** → Kontynuacja
- **NIE** → **Task 8.5a:** Sporządzenie protokołu reklamacyjnego
  - → Message Flow do Basenu 2 i/lub Basenu 1 (Reklamacja)
  - → End Event (Reklamacja)

**Task 8.5:** Rozładunek towaru
- Typ: User Task (kierowca + pracownik sklepu)

**Task 8.6:** Podpisanie dokumentów odbioru (CMR)
- Typ: User Task

**→ Message Flow do Basenu 2 (Transport)**  
   *Wysłanie: Potwierdzenie odbioru (podpis CMR)*

**Task 8.7:** Transport do zamrażarki sklepowej
- Typ: User Task

**Task 8.8:** Składowanie w zamrażarce (-18°C)
- Typ: User Task

**Task 8.9:** Rejestracja przyjęcia w systemie sklepowym
- Typ: User Task

**Task 8.10:** Wystawienie produktów na półki/do zamrażarki sprzedażowej
- Typ: User Task

**Task 8.11:** Oczekiwanie na klienta
- Typ: Timer Event

**End Event (Sklep):** Produkt dostępny do sprzedaży

**→ Message Flow do Basenu 4 (Klient)**  
   *Informacja: Produkt dostępny (cena, promocje)*

---

# 👤 BASEN 4: Klient końcowy

## Lane 4.1: Konsument

**Start Event:** Potrzeba zakupu pizzy

**Task 9.1:** Wybór produktu w sklepie
- Typ: User Task

**Task 9.2:** Zakup pizzy (płatność)
- Typ: User Task

**→ Message Flow do Basenu 3 (Sklep)**  
   *Wysłanie: Płatność*

**Task 9.3:** Transport pizzy do domu
- Typ: User Task

**Task 9.4:** Przechowywanie w zamrażarce domowej
- Typ: Timer Event (opcjonalne)

**Task 9.5:** Przygotowanie pizzy według instrukcji
- Typ: User Task

**Task 9.6:** Konsumpcja
- Typ: User Task

**End Event:** Proces zakończony (satysfakcja klienta)

**Gateway (Exclusive):** Czy klient jest zadowolony?
- **TAK** → End Event (Sukces)
- **NIE** → **Task 9.7:** Reklamacja do sklepu/producenta
  - → Message Flow do Basenu 3 lub Basenu 1
  - → End Event (Reklamacja)

---

## 🔄 Podsumowanie Message Flow (Przepływ komunikatów)

### 1. Fabryka → Firma transportowa
- **Zlecenie transportu** (dokumenty, termin, adres sklepu)
- Trigger: Zamówienie sklepu + gotowe palety

### 2. Firma transportowa → Fabryka
- **Potwierdzenie odbioru** (podpis CMR)
- Trigger: Załadunek zakończony

### 3. Firma transportowa → Sklep
- **Powiadomienie o dostawie** (telefon/SMS)
- Trigger: Kierowca w drodze

### 4. Sklep → Firma transportowa
- **Potwierdzenie odbioru** (podpis CMR)
- **Ewentualna reklamacja** (uszkodzenia, temperatura)
- Trigger: Rozładunek zakończony

### 5. Sklep → Klient
- **Dostępność produktu** (produkt na półce, cena)
- Trigger: Wystawienie towaru

### 6. Klient → Sklep
- **Zakup** (płatność)
- **Ewentualna reklamacja** (wada jakościowa)
- Trigger: Decyzja zakupu

### 7. Sklep → Fabryka (pośrednio lub bezpośrednio)
- **Zamówienie** (system B2B, telefon, email)
- **Reklamacja** (jeśli dotyczy produktu, nie transportu)
- Trigger: Niski stan magazynowy / Potrzeba

---

## ❌ Problemy zidentyfikowane w AS IS

### Basen 1 (Fabryka):
1. ❌ Brak automatycznej analizy przyczyn wadliwości produktu
2. ❌ Ręczne układanie palet i owijanie folią (czasochłonne)
3. ❌ Brak cyfrowej kontroli przepływu produktu między etapami
4. ❌ Ręczna rejestracja w systemie WMS
5. ❌ Brak predykcyjnego zarządzania zapasami
6. ❌ Kontrola jakości tylko wizualna na jednym etapie
7. ❌ Brak automatycznego raportowania o stratach produkcyjnych

### Basen 2 (Transport):
8. ❌ Brak monitoringu temperatury w czasie rzeczywistym podczas transportu
9. ❌ Brak automatycznego powiadamiania sklepu o dostawie
10. ❌ Ręczne przygotowanie dokumentów CMR

### Basen 3 (Sklep):
11. ❌ Manualna weryfikacja dostawy (podatna na błędy)
12. ❌ Brak automatycznego potwierdzenia odbioru

### Między basenami:
13. ❌ Brak integracji systemów (fabryka-transport-sklep)
14. ❌ Komunikacja głównie telefoniczna/papierowa
15. ❌ Brak end-to-end visibility (brak widoczności produktu w całym łańcuchu)

---

## 📝 Uwagi dotyczące diagramu

- **Baseny (Pools)** = Różne organizacje (Fabryka, Transport, Sklep, Klient)
- **Message Flow** (⚡ przerywana linia) = Komunikacja między organizacjami
- **Sequence Flow** (→ ciągła linia) = Przepływ wewnątrz organizacji
- **Intermediate Event (Message)** = Punkt odbioru wiadomości z innego basenu
- **End Event** w jednym basenie może być triggerem dla **Start Event (Message)** w innym basenie
