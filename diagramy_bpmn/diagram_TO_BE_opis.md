# 📊 Diagram BPMN TO BE - Proces produkcji mrożonej pizzy (Usprawnienia)

## Opis struktury diagramu (Stan docelowy)

### Struktura: 4 baseny (pools) z zaawansowaną automatyzacją

---

# 🏭 BASEN 1: Fabryka Iglotex (Smart Factory 4.0)

## Lane 1.1: Dział Piekarni

**Start Event:** Automatyczne otrzymanie zlecenia z systemu ERP (API)

**Task 1.1:** Automatyczne dozowanie składników z kontrolą AI
- Typ: Service Task (automatyczne + AI)
- **NOWOŚĆ:** System AI optymalizuje proporcje na podstawie warunków atmosferycznych i jakości surowców

**Task 1.2:** Mieszanie składników w mieszalniku
- Typ: Service Task (automatyczne)

**Task 1.3:** Dzielenie ciasta (kęsowanie)
- Typ: Service Task (automatyczne)

**Task 1.4:** Formowanie ciasta w kulki
- Typ: Service Task (automatyczne)

**Task 1.5:** Pierwsze garowanie ciasta z monitoringiem IoT
- Typ: Service Task (automatyczne, z timerem)
- **NOWOŚĆ:** Czujniki IoT monitorują temperaturę i wilgotność w czasie rzeczywistym

**Task 1.6:** Prasowanie na gorąco
- Typ: Service Task (automatyczne)

**Task 1.7:** Drugie garowanie z monitoringiem IoT
- Typ: Service Task (automatyczne, z timerem)
- **NOWOŚĆ:** Dynamiczna regulacja czasu na podstawie danych z czujników

**Task 1.8:** Prasowanie i nakłuwanie ciasta
- Typ: Service Task (automatyczne)

**Task 1.9:** Pieczenie spodu z kontrolą AI (270-300°C)
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** AI dostosowuje czas i temperaturę dynamicznie dla każdej partii

**Task 1.10:** Odbiór spodów przez robota + skanowanie QR
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Każdy spód otrzymuje unikalny kod QR (digital twin), rejestracja w systemie

**→ Sequence Flow do Lane 1.2 (Dział Toppingu)**

---

## Lane 1.2: Dział Toppingu

**Task 2.1:** Chłodzenie spodów z monitoringiem IoT
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Czujniki temperatury w czasie rzeczywistym, alerty przy odchyleniach

**Task 2.2:** Nakładanie sosu pomidorowego z kamerą AI
- Typ: Service Task (automatyczne, aplikator + AI Vision)
- **NOWOŚĆ:** Kamera AI kontroluje równomierność nałożenia w czasie rzeczywistym

**Task 2.3-2.6:** Nakładanie składników (mozzarella, pieczarki, cebula, szynka) z kontrolą AI
- Typ: Service Task (automatyczne, aplikator + AI Vision)
- **NOWOŚĆ:** AI weryfikuje ilość i rozmieszczenie każdego składnika, natychmiastowe korekty

**Task 2.7:** Doprawianie ziołami
- Typ: Service Task (automatyczne)

**Task 2.8:** Aplikacja mgiełki wodnej
- Typ: Service Task (automatyczne)

**Task 2.9:** Automatyczna kontrola wizualna przez system AI Vision
- Typ: Service Task (automatyczne - AI)
- **NOWOŚĆ:** System wizyjny AI zastępuje kontrolę manualną, 99.5% wykrywalność

**Gateway (Exclusive):** Czy pizza spełnia standardy jakości (AI Decision)?
- **TAK** → Sequence Flow do Lane 1.3
- **NIE** → **Sub-Process (nowy):** Automatyczna analiza przyczyn odrzucenia
  - System AI identyfikuje przyczynę (np. "aplikator sera - nierównomierne od 30 min")
  - Automatyczne powiadomienie operatora + dashboard alert
  - Zapis w systemie QMS
  - **Gateway:** Czy możliwa automatyczna kalibracja?
    - **TAK** → Automatyczna kalibracja aplikatora → kontynuacja produkcji
    - **NIE** → Alert do technika + End Event (Odrzucenie)
  
**→ Sequence Flow do Lane 1.3 (Produkcja i Zamrażanie)**

---

## Lane 1.3: Dział Produkcji i Zamrażania

**Task 3.1:** Zamrażanie w tunelu (-33°C) z monitoringiem IoT
- Typ: Service Task (automatyczne, z timerem)
- **NOWOŚĆ:** Monitoring temperatury i czasu w czasie rzeczywistym, automatyczne alarmy, dashboard

**→ Sequence Flow do Lane 1.4 (Kontrola Jakości)**

---

## Lane 1.4: Dział Kontroli Jakości

**Task 4.1:** Przejście przez detektor metali z rejestracją
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Automatyczna rejestracja wyniku w systemie QMS + timestamp

**Gateway (Exclusive):** Czy wykryto metal?
- **TAK** → **Sub-Process (rozszerzony):**
  - Automatyczny alarm dźwiękowy i wizualny
  - Zatrzymanie linii produkcyjnej
  - Usunięcie produktu
  - **NOWOŚĆ:** Automatyczna analiza AI: które produkty przed/po mogą być zagrożone
  - Powiadomienie kierownika przez SMS/email
  - Raport incydentu w QMS
  - → End Event (Odrzucenie)
- **NIE** → Kontynuacja

**Task 4.2:** Ważenie pizzy z rejestracją
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Automatyczna rejestracja wagi w systemie + analiza trendów

**Gateway (Exclusive):** Czy waga jest w normie?
- **TAK** → Kontynuacja
- **NIE** → **Sub-Process (nowy):**
  - **NOWOŚĆ:** Automatyczna analiza odchyleń przez AI
  - System identyfikuje, który dozownik jest źródłem problemu
  - Automatyczna kalibracja dozowników (jeśli możliwa)
  - Alert do operatora
  - → End Event (Odrzucenie wadliwego produktu)

**Task 4.3:** Kontrola rentgenem (nowy)
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Dodatkowa kontrola struktury wewnętrznej produktu (bąble powietrza, rozprowadzenie składników)

**Gateway (Exclusive):** Czy struktura OK?
- **TAK** → Kontynuacja
- **NIE** → Analiza + End Event

**→ Sequence Flow do Lane 1.5 (Pakowanie)**

---

## Lane 1.5: Dział Pakowania

**Task 5.1:** Pakowanie w folię
- Typ: Service Task (automatyczne)

**Task 5.2:** Przejście przez gorący tunel (obkurczanie folii)
- Typ: Service Task (automatyczne)

**Task 5.3:** Pakowanie do kartonów zbiorczych
- Typ: Service Task (w pełni automatyczne)
- **NOWOŚĆ:** Robot kartoniarz zastępuje pracę semi-automatyczną

**Task 5.4:** Automatyczne układanie kartonów na paletach
- Typ: Service Task (robot paletyzujący)
- **NOWOŚĆ:** Robot paletyzujący - 4 min/paleta vs 12 min manualnie

**Task 5.5:** Automatyczne owijanie palet folią
- Typ: Service Task (automatyczna owijarka)
- **NOWOŚĆ:** Automatyczna owijarka palet - równomierne naciągnięcie, oszczędność folii

**Task 5.6:** Etykietowanie palet z QR i RFID
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Każda paleta otrzymuje etykietę z QR code + RFID tag
- Zawiera: numer partii, data produkcji, termin ważności, zawartość, destynacja

**→ Sequence Flow do Lane 1.6 (Magazyn)**

---

## Lane 1.6: Smart Warehouse (Magazyn inteligentny)

**Task 6.1:** Automatyczny transport AGV do magazynu
- Typ: Service Task (AGV - Automated Guided Vehicle)
- **NOWOŚĆ:** Bezzałogowe pojazdy transportują palety bez interwencji człowieka

**Task 6.2:** Automatyczne składowanie przez AS/RS
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System AS/RS (Automated Storage and Retrieval System) automatycznie znajduje optymalne miejsce

**Task 6.3:** Automatyczna rejestracja w systemie WMS
- Typ: Service Task (automatyczne - RFID)
- **NOWOŚĆ:** Bramka RFID automatycznie skanuje paletę przy wjeździe, zero ręcznego wprowadzania

**Task 6.4:** Monitoring temperatury i lokalizacji w czasie rzeczywistym
- Typ: Service Task (IoT)
- **NOWOŚĆ:** Czujniki IoT ciągle monitorują temperaturę (-23°C), alerty przy odchyleniach

**Task 6.5:** System AI - predykcyjne zarządzanie zapasami
- Typ: Service Task (AI)
- **NOWOŚĆ:** AI przewiduje zapotrzebowanie na podstawie:
  - Dane historyczne sprzedaży
  - Sezonowość
  - Promocje planowane w sklepach
  - Trendy rynkowe
  - Prognozy pogody
- System automatycznie generuje zlecenia produkcyjne

**Intermediate Event (Message):** Otrzymanie zamówienia od sklepu (przez API systemu B2B)
- **NOWOŚĆ:** Automatyczna integracja, sklep składa zamówienie online, system weryfikuje dostępność

**Task 6.6:** Automatyczne przygotowanie wysyłki
- Typ: Service Task (AGV + AS/RS)
- **NOWOŚĆ:** System automatycznie:
  - Wybiera palety (FEFO - First Expired, First Out)
  - AGV pobiera palety
  - Przygotowuje do strefy załadunkowej
  - Generuje dokumenty wysyłkowe

**Task 6.7:** Automatyczne generowanie zlecenia transportowego
- Typ: Service Task (integracja z TMS)
- **NOWOŚĆ:** System automatycznie tworzy zlecenie dla firmy transportowej

**End Event (Fabryka):** Gotowe do załadunku

**→ Message Flow do Basenu 2 (Firma transportowa)**  
   *Wysłanie API: Zlecenie transportu (JSON) + dokumenty elektroniczne + tracking number*

---

# 🚚 BASEN 2: Firma transportowa/Logistyka (Smart Logistics)

## Lane 2.1: Dział Transportu

**Start Event (Message - API):** Automatyczne otrzymanie zlecenia transportu z systemu fabryki

**Task 7.1:** Automatyczna akceptacja zlecenia w systemie TMS
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System TMS automatycznie:
  - Przypisuje kierowcę i samochód
  - Optymalizuje trasę (uwzględnia ruch, dystans, koszty)
  - Rezerwuje slot czasowy u odbiorcy

**Task 7.2:** Automatyczne generowanie dokumentów CMR
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Dokumenty elektroniczne (e-CMR), automatyczne wypełnienie z danych zlecenia

**Task 7.3:** Powiadomienie kierowcy (automatyczne)
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Aplikacja mobilna kierowcy otrzymuje zlecenie z mapą, szczegółami

**Task 7.4:** Dojazd do fabryki
- Typ: Service Task

**Task 7.5:** Załadunek palet (częściowo automatyczny AGV)
- Typ: Service Task
- **NOWOŚĆ:** AGV fabryki załadowuje samochód, kierowca nadzoruje

**Task 7.6:** Automatyczne potwierdzenie załadunku (skan RFID)
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System automatycznie skanuje RFID wszystkich palet, weryfikuje kompletność

**→ Message Flow do Basenu 1 (Fabryka)**  
   *Wysłanie API: Potwierdzenie odbioru (timestamp, lista palet)*

**Task 7.7:** Transport z monitoringiem GPS + temperatura
- Typ: Service Task
- **NOWOŚĆ:** Real-time monitoring:
  - GPS - lokalizacja co 5 min
  - Temperatura w komorze chłodniczej - monitoring co 10 min
  - Alerty SMS/email przy przekroczeniu -15°C przez > 30 min
  - Dashboard dla koordynatora logistyki

**Gateway (Event-based):** Monitoring podczas transportu
- **Temperatura OK** → Kontynuacja
- **Temperatura poza normą** → **Sub-Process:**
  - Automatyczny alert do kierowcy (SMS + app)
  - Alert do koordynatora logistyki
  - Alert do sklepu (przygotowanie na możliwe opóźnienie/reklamację)
  - Logowanie incydentu

**Task 7.8:** Automatyczne powiadomienie sklepu o ETA
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System automatycznie wysyła powiadomienie do sklepu:
  - 2 godziny przed przyjazdem
  - 30 minut przed przyjazdem
  - Aktualny ETA (Estimated Time of Arrival)

**→ Message Flow do Basenu 3 (Sklep)**  
   *Wysłanie API/SMS: Powiadomienie o dostawie (ETA, tracking link)*

**Task 7.9:** Dojazd do sklepu
- Typ: Service Task

**End Event (Transport):** Przygotowany do rozładunku

---

# 🏪 BASEN 3: Sklep detaliczny (Smart Store)

## Lane 3.1: Dział Magazynowy Sklepu

**Start Event (Message - API):** Automatyczne powiadomienie o dostawie (ETA)

**Task 8.1:** Przygotowanie do odbioru
- Typ: User Task
- **NOWOŚĆ:** Pracownik sklepu ma wcześniejszą informację, może zaplanować pracę

**Intermediate Event (Message):** Kierowca przyjechał

**Task 8.2:** Przyjęcie dostawy
- Typ: User Task

**Task 8.3:** Automatyczne skanowanie RFID palet
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Bramka RFID automatycznie skanuje wszystkie palety, weryfikuje z dokumentami

**Gateway (Exclusive):** Czy ilość się zgadza?
- **TAK** → Kontynuacja
- **NIE** → **Task 8.4a:** Automatyczne zgłoszenie niezgodności
  - System automatycznie generuje protokół
  - → Message Flow do Basenu 2 i Basenu 1

**Task 8.4:** Kontrola temperatury produktów (czujnik laserowy)
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** Czujnik temperatury laserowy sprawdza temperaturę powierzchni produktów

**Gateway (Exclusive):** Czy temperatura OK?
- **TAK** → Kontynuacja
- **NIE** → Reklamacja → Message Flow do Basenu 2 (Transport)

**Task 8.5:** Elektroniczne potwierdzenie odbioru (e-podpis)
- Typ: User Task (tablet)
- **NOWOŚĆ:** Elektroniczny podpis na tablecie, automatyczne wysłanie

**→ Message Flow do Basenu 2 (Transport)**  
   *Wysłanie API: Potwierdzenie odbioru (e-podpis, timestamp, temp. OK)*

**Task 8.6:** Rozładunek towaru
- Typ: User Task

**Task 8.7:** Automatyczna rejestracja w systemie sklepowym
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System sklepu automatycznie dodaje produkty do magazynu na podstawie skanu RFID

**Task 8.8:** Transport do zamrażarki sklepowej
- Typ: User Task

**Task 8.9:** Składowanie w zamrażarce (-18°C)
- Typ: User Task

**Task 8.10:** Wystawienie produktów na półki
- Typ: User Task

**Task 8.11:** Automatyczna aktualizacja dostępności online
- Typ: Service Task (automatyczne)
- **NOWOŚĆ:** System automatycznie aktualizuje dostępność produktu na stronie/w aplikacji sklepu

**End Event (Sklep):** Produkt dostępny do sprzedaży

**→ Message Flow do Basenu 4 (Klient)**  
   *Informacja: Produkt dostępny (cena, promocje, lokalizacja w sklepie)*

---

# 👤 BASEN 4: Klient końcowy (Connected Consumer)

## Lane 4.1: Konsument

**Start Event:** Potrzeba zakupu pizzy

**Task 9.1:** Sprawdzenie dostępności online (opcjonalne)
- Typ: User Task
- **NOWOŚĆ:** Klient może sprawdzić w aplikacji sklepu, czy produkt jest dostępny

**Task 9.2:** Wybór produktu w sklepie
- Typ: User Task

**Task 9.3:** Zakup pizzy (płatność)
- Typ: User Task

**→ Message Flow do Basenu 3 (Sklep)**  
   *Wysłanie: Płatność*

**Task 9.4:** Transport pizzy do domu
- Typ: User Task

**Task 9.5:** Skanowanie QR code na opakowaniu (opcjonalne)
- Typ: User Task
- **NOWOŚĆ:** Klient może zeskanować QR code i zobaczyć:
  - Data produkcji, termin ważności
  - Informacje o składnikach, wartości odżywcze
  - Przepisy, porady przygotowania
  - Historia produktu (traceability)

**Task 9.6:** Przechowywanie w zamrażarce domowej
- Typ: Timer Event (opcjonalne)

**Task 9.7:** Przygotowanie pizzy według instrukcji
- Typ: User Task

**Task 9.8:** Konsumpcja
- Typ: User Task

**Gateway (Exclusive):** Czy klient jest zadowolony?
- **TAK** → **Task 9.9 (opcjonalne):** Pozostawienie opinii online
  - **NOWOŚĆ:** System umożliwia łatwe pozostawienie opinii przez app/QR
  - → End Event (Sukces)
- **NIE** → **Task 9.10:** Reklamacja online lub przez infolinię
  - **NOWOŚĆ:** Formularz online z załączeniem zdjęcia produktu
  - System automatycznie identyfikuje partię po zeskanowanym QR/numerze
  - → Message Flow do Basenu 3 lub Basenu 1
  - → End Event (Reklamacja)

---

# 📊 BASEN DODATKOWY (opcjonalny, w tle): System Analityczny

## Monitoring i Analiza (Cross-pool)

**Task 10.1:** Ciągła analiza danych produkcyjnych (BI + AI)
- **NOWOŚĆ:** Dashboard w czasie rzeczywistym dla zarządu
- Zbiera dane ze wszystkich basenów:
  - Basen 1: Wydajność, odrzuty, OEE, temperatura
  - Basen 2: On-time delivery, temperatura transportu
  - Basen 3: Przyjęcia, reklamacje
  - Basen 4: Opinie klientów, reklamacje

**Task 10.2:** Automatyczne raportowanie KPI
- **NOWOŚĆ:** Dzienne, tygodniowe, miesięczne raporty automatyczne

**Task 10.3:** Predykcyjne utrzymanie ruchu
- **NOWOŚĆ:** AI przewiduje awarie maszyn na podstawie danych IoT

**Task 10.4:** Optymalizacja procesów przez AI
- **NOWOŚĆ:** System proponuje usprawnienia

---

## 🔄 Podsumowanie Message Flow TO BE (Zautomatyzowane)

### 1. Fabryka → Firma transportowa (API)
- **Zlecenie transportowe** (JSON, automatyczne)
- **Dokumenty elektroniczne** (e-CMR)
- **Tracking number** (RFID tags)

### 2. Firma transportowa → Fabryka (API)
- **Potwierdzenie odbioru** (automatyczne, RFID scan)
- **Status transportu** (real-time GPS + temperatura)

### 3. Firma transportowa → Sklep (API/SMS)
- **Powiadomienie o ETA** (2h i 30 min przed)
- **Link do trackingu** (real-time)
- **Alert** (jeśli problem z temperaturą)

### 4. Sklep → Firma transportowa (API)
- **Potwierdzenie odbioru** (e-podpis, automatyczne)
- **Reklamacja** (jeśli dotyczy transportu)

### 5. Sklep → Klient (App/Web)
- **Dostępność produktu** (real-time)
- **Promocje** (push notifications)

### 6. Klient → Sklep (Digital)
- **Zakup** (płatność)
- **Opinie** (rating, komentarze)
- **Reklamacja online** (formularz + zdjęcie)

### 7. Sklep → Fabryka (API B2B)
- **Zamówienie automatyczne** (triggered by low stock)
- **Reklamacja** (jeśli dotyczy produktu)

---

## ✅ Usprawnienia wprowadzone w TO BE

### Basen 1 (Fabryka):
✅ Automatyczna analiza przyczyn wadliwości (AI)  
✅ Robotyzacja pakowania (paletyzacja, owijanie)  
✅ Digital twin produktu (QR/RFID na każdej pizzy)  
✅ Automatyczna rejestracja (zero ręcznego wprowadzania)  
✅ Predykcyjne zarządzanie zapasami (AI)  
✅ Wielopoziomowa kontrola jakości (AI, metal, waga, rentgen)  
✅ Smart Warehouse (AGV, AS/RS)  
✅ Real-time monitoring (IoT)  

### Basen 2 (Transport):
✅ Real-time tracking (GPS + temperatura)  
✅ Automatyczne powiadomienia (ETA do sklepu)  
✅ E-dokumenty (e-CMR)  
✅ Natychmiastowe alerty (problemy z temperaturą)  

### Basen 3 (Sklep):
✅ Automatyczne skanowanie RFID  
✅ E-potwierdzenia (e-podpis)  
✅ Automatyczna rejestracja przyjęć  
✅ Online availability update  

### Basen 4 (Klient):
✅ Sprawdzanie dostępności online  
✅ Traceability przez QR code  
✅ Łatwa reklamacja online  
✅ Digital engagement  

### Między basenami:
✅ Pełna integracja systemów (API)  
✅ End-to-end visibility (widoczność produktu w całym łańcuchu)  
✅ Automatyczna komunikacja (minimum interwencji człowieka)  
✅ Real-time data sharing  

---

## 🎯 Korzyści TO BE vs AS IS

- **+20% wydajność** (Basen 1)
- **-75% odrzuty** (Basen 1)
- **-92% czas reakcji** (wszystkie baseny)
- **100% traceability** (wszystkie baseny)
- **-80% strat w transporcie** (Basen 2)
- **-50% czas kompletacji** (Basen 1 i 3)
- **ROI: 3.3 lata**
