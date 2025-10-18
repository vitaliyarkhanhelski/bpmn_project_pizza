# 📊 Diagram BPMN AS IS - Proces produkcji mrożonej pizzy

## Opis struktury diagramu (Stan obecny)

### Struktura AS IS: **3 baseny** (pools) reprezentujące różne organizacje

**Kluczowa różnica AS IS vs TO BE**: W AS IS transport jest **torem wewnątrz fabryki**, nie osobnym basenem!

---

# 🏭 BASEN 1 (AS IS): Fabryka Iglotex - wszystko "in-house"

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

**→ Sequence Flow do Lane 1.7 (Dystrybucja - transport własny)**

---

## Lane 1.7: Dział Dystrybucji (transport własny)

**Task 7.1:** Planowanie tras dostaw
- Typ: User Task
- Problem: Ręczne planowanie, brak optymalizacji

**Task 7.2:** Przygotowanie dokumentów dostawy
- Typ: User Task

**Task 7.3:** Załadunek palet na samochód firmowy (własna flota)
- Typ: User Task (wózek widłowy + kierowca)
- Problem: Stare samochody, mała flota

**Task 7.4:** Transport do sklepu
- Typ: Service Task
- Problem: Brak GPS, brak monitoringu temperatury real-time (tylko rejestrator)
- Problem: Własni kierowcy (pracownicy fabryki, nie specjaliści logistyczni)

**Task 7.5:** Powiadomienie sklepu o dostawie
- Typ: User Task (telefon)
- Problem: Komunikacja manualna

**Task 7.6:** Dojazd do sklepu
- Typ: Service Task

**Task 7.7:** Rozładunek towaru w sklepie
- Typ: User Task (kierowca + pracownik sklepu)

**Task 7.8:** Podpisanie dokumentów dostawy
- Typ: User Task

**End Event (Fabryka):** Produkt dostarczony do sklepu

**→ Message Flow do Basenu 2 (Sklep)**  
   *Informacja: Dostawa wykonana (dokumenty, podpisy)*

---

# 🏪 BASEN 2 (AS IS): Sklep detaliczny

## Lane 2.1: Dział Magazynowy Sklepu

**Start Event (Message):** Powiadomienie o dostawie od fabryki (telefon)

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
  - → Message Flow do Basenu 1 - Fabryka (Reklamacja)
  - → End Event (Reklamacja)

**Task 8.5:** Rozładunek towaru
- Typ: User Task (kierowca + pracownik sklepu)

**Task 8.6:** Podpisanie dokumentów odbioru
- Typ: User Task

**→ Message Flow do Basenu 1 (Fabryka)**  
   *Wysłanie: Potwierdzenie odbioru (podpis na dokumencie)*

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

**→ Message Flow do Basenu 3 (Klient)**  
   *Informacja: Produkt dostępny (fizycznie na półce)*

---

# 👤 BASEN 3 (AS IS): Klient końcowy

## Lane 3.1: Konsument

**Start Event:** Potrzeba zakupu pizzy

**Task 9.1:** Wybór produktu w sklepie
- Typ: User Task

**Task 9.2:** Zakup pizzy (płatność)
- Typ: User Task

**→ Message Flow do Basenu 2 (Sklep)**  
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
  - → Message Flow do Basenu 2 (Sklep) lub Basenu 1 (Fabryka)
  - → End Event (Reklamacja)

---

## 🔄 Podsumowanie Message Flow (Przepływ komunikatów) - AS IS

**Struktura: 3 baseny** (Fabryka → Sklep → Klient)

### 1. Sklep → Fabryka
- **Zamówienie** (telefon, fax, email, system B2B)
- Trigger: Niski stan magazynowy w sklepie

### 2. Fabryka → Sklep
- **Powiadomienie o dostawie** (telefon)
- Trigger: Własny transport fabryki w drodze (Lane 1.7)

### 3. Fabryka → Sklep
- **Dostawa produktów** (fizyczna)
- Trigger: Przyjazd kierowcy fabryki

### 4. Sklep → Fabryka
- **Potwierdzenie odbioru** (podpis na dokumentach)
- **Ewentualna reklamacja** (wada produktu, uszkodzenia)
- Trigger: Rozładunek zakończony

### 5. Sklep → Klient
- **Dostępność produktu** (produkt na półce, cena)
- Trigger: Wystawienie towaru

### 6. Klient → Sklep
- **Zakup** (płatność)
- **Ewentualna reklamacja** (wada jakościowa)
- Trigger: Decyzja zakupu

### 7. Klient → Fabryka (przez sklep lub bezpośrednio)
- **Reklamacja jakościowa**
- Trigger: Problem z produktem

---

## ❌ Problemy zidentyfikowane w AS IS (3 baseny)

### Basen 1 (Fabryka - w tym transport własny Lane 1.7):
1. ❌ Brak automatycznej analizy przyczyn wadliwości produktu
2. ❌ Ręczne układanie palet i owijanie folią (czasochłonne)
3. ❌ Brak cyfrowej kontroli przepływu produktu między etapami
4. ❌ Ręczna rejestracja w systemie WMS
5. ❌ Brak predykcyjnego zarządzania zapasami
6. ❌ Kontrola jakości tylko wizualna na jednym etapie
7. ❌ Brak automatycznego raportowania o stratach produkcyjnych
8. ❌ **Transport własny (Lane 1.7)**: Stare samochody, brak GPS, brak monitoringu real-time
9. ❌ **Transport własny**: Mała flota, brak specjalizacji logistycznej
10. ❌ **Transport własny**: Drogie utrzymanie (kierowcy, serwis, paliwo)

### Basen 2 (Sklep):
11. ❌ Manualna weryfikacja dostawy (podatna na błędy)
12. ❌ Brak automatycznego potwierdzenia odbioru
13. ❌ Ręczna rejestracja przyjęcia w systemie sklepowym

### Między basenami:
14. ❌ Brak integracji systemów (fabryka-sklep)
15. ❌ Komunikacja głównie telefoniczna/papierowa
16. ❌ Brak end-to-end visibility (brak widoczności produktu w całym łańcuchu)
17. ❌ **Główny problem**: Transport wewnątrz fabryki (tor), nie specjalistyczna firma

---

## 📝 Uwagi dotyczące diagramu AS IS

### Struktura: 3 baseny
- **Basen 1: Fabryka** (7 torów, w tym Lane 1.7 Dystrybucja - transport własny)
- **Basen 2: Sklep** (1 tor)
- **Basen 3: Klient** (1 tor)

### Notacja BPMN:
- **Baseny (Pools)** = Różne organizacje (Fabryka, Sklep, Klient)
- **Tory (Lanes)** = Działy wewnątrz organizacji (np. Lane 1.7 Dystrybucja w Fabryce)
- **Message Flow** (⚡ przerywana linia) = Komunikacja między organizacjami
- **Sequence Flow** (→ ciągła linia) = Przepływ wewnątrz organizacji
- **Intermediate Event (Message)** = Punkt odbioru wiadomości z innego basenu
- **End Event** w jednym basenie może być triggerem dla **Start Event (Message)** w innym basenie

### Kluczowa różnica AS IS vs TO BE:
⚠️ **AS IS**: Transport = tor wewnątrz fabryki (Lane 1.7) - wszystko "in-house"  
✅ **TO BE**: Transport = osobny basen (Firma transportowa) - outsourcing!
