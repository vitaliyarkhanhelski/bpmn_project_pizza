# 📊 Schemat procesu - wizualizacja tekstowa (4 baseny)

## Przepływ procesu produkcji mrożonej pizzy

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║  BASEN 1: FABRYKA IGLOTEX                                                    ║
╠═══════════════════════════════════════════════════════════════════════════════╣
║                                                                               ║
║  LANE 1.1: DZIAŁ PIEKARNI                                                    ║
║  ─────────────────────────────────────────────────────────────────────────   ║
║  (START) → [Dozowanie składników] → [Mieszanie] → [Kęsowanie] →             ║
║  → [Formowanie] → [Garowanie 1] → [Prasowanie] → [Garowanie 2] →            ║
║  → [Nakłuwanie] → [Pieczenie spodu 270-300°C] → [Odbiór przez robota] ─┐    ║
║                                                                          │    ║
╠══════════════════════════════════════════════════════════════════════════╪═══╣
║  LANE 1.2: DZIAŁ TOPPINGU                                                │    ║
║  ────────────────────────────────────────────────────────────────────── │    ║
║  ┌──────────────────────────────────────────────────────────────────────┘    ║
║  ↓                                                                            ║
║  [Chłodzenie] → [Sos pomidorowy] → [Mozzarella] → [Pieczarki] →             ║
║  → [Cebula] → [Szynka] → [Zioła] → [Mgiełka wodna] →                        ║
║  → [Kontrola jakości] → <Czy OK?> ──┐                                        ║
║                          │ NIE      │ TAK                                     ║
║                          ↓          ↓                                         ║
║                  (END-Odrzucenie)   ┼──────────────────────┐                 ║
║                                                             │                 ║
╠═════════════════════════════════════════════════════════════╪════════════════╣
║  LANE 1.3: DZIAŁ PRODUKCJI I ZAMRAŻANIA                    │                 ║
║  ───────────────────────────────────────────────────────────│─────────────   ║
║  ┌──────────────────────────────────────────────────────────┘                ║
║  ↓                                                                            ║
║  [Zamrażanie w tunelu -33°C przez 20 min] ──────────────────────────┐        ║
║                                                                       │        ║
╠═══════════════════════════════════════════════════════════════════════╪══════╣
║  LANE 1.4: DZIAŁ KONTROLI JAKOŚCI                                    │       ║
║  ───────────────────────────────────────────────────────────────────  │       ║
║  ┌───────────────────────────────────────────────────────────────────┘       ║
║  ↓                                                                            ║
║  [Detektor metali] → <Wykryto metal?> ──┐                                    ║
║                        │ TAK             │ NIE                                ║
║                        ↓                 ↓                                    ║
║                (END-Odrzucenie+Alarm) [Ważenie] → <Waga OK?> ─┐              ║
║                                                    │ NIE      │ TAK           ║
║                                                    ↓          ↓               ║
║                                            (END-Odrzucenie)   ┼──────┐        ║
║                                                                       │        ║
╠═══════════════════════════════════════════════════════════════════════╪══════╣
║  LANE 1.5: DZIAŁ PAKOWANIA                                           │       ║
║  ───────────────────────────────────────────────────────────────────  │       ║
║  ┌───────────────────────────────────────────────────────────────────┘       ║
║  ↓                                                                            ║
║  [Foliowanie] → [Gorący tunel] → [Kartonowanie] →                           ║
║  → [Układanie na paletach] → [Owijanie folią] → [Etykieta RFID] ─┐          ║
║                                                                    │          ║
╠════════════════════════════════════════════════════════════════════╪═════════╣
║  LANE 1.6: MAGAZYN (SMART WAREHOUSE - TO BE)                      │          ║
║  ──────────────────────────────────────────────────────────────────│─────    ║
║  ┌────────────────────────────────────────────────────────────────┘          ║
║  ↓                                                                            ║
║  [Transport AGV] → [AS/RS składowanie] → [Rejestracja RFID auto] →          ║
║  → [Monitoring IoT -23°C] → [Predykcja AI zapasów] →                        ║
║  → ⌚ (oczekiwanie na zamówienie B2B) → [Przygotowanie wysyłki auto] →      ║
║  → [Generowanie zlecenia transportu] → (END-Fabryka)                         ║
║                                              │                                ║
║                                              │ ⚡ Message Flow                ║
╚══════════════════════════════════════════════╪══════════════════════════════╝
                                                │
                                                ↓ Zlecenie transportu (API)
╔═══════════════════════════════════════════════╪══════════════════════════════╗
║  BASEN 2: FIRMA TRANSPORTOWA / LOGISTYKA     │                              ║
╠═══════════════════════════════════════════════╪══════════════════════════════╣
║                                                                               ║
║  LANE 2.1: DZIAŁ TRANSPORTU                                                  ║
║  ─────────────────────────────────────────────────────────────────────────   ║
║  (START-Message) ← Zlecenie od fabryki                                       ║
║  ↓                                                                            ║
║  [Akceptacja w TMS] → [e-CMR generowanie] → [Powiadomienie kierowcy] →     ║
║  → [Dojazd do fabryki] → [Załadunek + RFID scan] →                          ║
║  → ⚡ [Potwierdzenie odbioru] ──────┐                                        ║
║  → [Transport GPS+temp monitoring] →│                                        ║
║  → <Temp OK?> ─────┐                │                                        ║
║       │ NIE        │ TAK             │                                        ║
║       ↓            ↓                 │                                        ║
║    [Alerty]   [Kontynuacja] →       │                                        ║
║  → [Auto powiadomienie sklepu ETA] →│                                        ║
║  → [Dojazd do sklepu] → (END-Transport)                                     ║
║                            │         │                                        ║
║                            │         │ ⚡ Potwierdzenie do fabryki            ║
║                            │         └──────────────────────────→            ║
║                            │ ⚡ Message Flow                                  ║
╚════════════════════════════╪═════════════════════════════════════════════════╝
                             │
                             ↓ Powiadomienie o dostawie (API/SMS)
╔════════════════════════════╪═════════════════════════════════════════════════╗
║  BASEN 3: SKLEP DETALICZNY │                                                 ║
╠════════════════════════════╪═════════════════════════════════════════════════╣
║                                                                               ║
║  LANE 3.1: DZIAŁ MAGAZYNOWY SKLEPU                                           ║
║  ─────────────────────────────────────────────────────────────────────────   ║
║  (START-Message) ← Powiadomienie o ETA                                       ║
║  ↓                                                                            ║
║  [Przygotowanie do odbioru] → (Kierowca przyjechał) →                       ║
║  → [Przyjęcie dostawy] → [RFID scan auto] → <Ilość OK?> ─┐                  ║
║  → [Kontrola temp] → <Temp OK?> ─┐           │ NIE       │ TAK              ║
║       │ NIE              │ TAK    └───→ [Reklamacja] → ⚡ → Transport/Fabryka║
║       └───→ [Reklamacja] ↓              (END-Reklamacja)                     ║
║             ↓            ↓                                                    ║
║         ⚡ Alert    [e-Podpis potwierdzenie] ─────┐                          ║
║                     ↓                              │                          ║
║  [Rozładunek] → [Auto rejestracja w sys. sklepu] →│                          ║
║  → [Składowanie -18°C] → [Wystawienie na półki] → │                          ║
║  → [Update dostępności online] → (END-Sklep)      │                          ║
║                                      │             │                          ║
║                                      │             │ ⚡ Potwierdzenie odbioru ║
║                                      │             └────────────────────→    ║
║                                      │ ⚡ Message Flow                        ║
╚══════════════════════════════════════╪═════════════════════════════════════╝
                                       │
                                       ↓ Produkt dostępny (info online)
╔══════════════════════════════════════╪═════════════════════════════════════╗
║  BASEN 4: KLIENT KOŃCOWY             │                                       ║
╠══════════════════════════════════════╪═════════════════════════════════════╣
║                                                                               ║
║  LANE 4.1: KONSUMENT                                                         ║
║  ─────────────────────────────────────────────────────────────────────────   ║
║  (START) Potrzeba zakupu                                                     ║
║  ↓                                                                            ║
║  [Sprawdzenie dostępności online] → [Wybór w sklepie] → [Zakup] ─┐          ║
║  → [Transport do domu] → [Skan QR - traceability] →               │          ║
║  → [Przechowywanie] → [Przygotowanie] → [Konsumpcja] →            │          ║
║  → <Zadowolony?> ──────┐                                           │          ║
║       │ NIE            │ TAK                                        │          ║
║       ↓                ↓                                            │          ║
║  [Reklamacja online] [Opinia online]                               │          ║
║       │                │                                            │          ║
║       ↓                ↓                                            │          ║
║  (END-Reklamacja)  (END-Sukces)                                    │          ║
║       │                                                             │          ║
║       │ ⚡ Reklamacja do sklep/fabryka                             │ ⚡ Płatność║
║       └──────────────────────────→                                 └─────────→║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

---

## Legenda symboli

- `(START)` - Zdarzenie rozpoczynające proces w basenie
- `(START-Message)` - Start wywołany wiadomością z innego basenu
- `(END)` - Zdarzenie kończące proces w basenie
- `[Zadanie]` - Zadanie (task) do wykonania
- `<Decyzja?>` - Bramka decyzyjna (gateway)
- `→` - Sequence Flow (przepływ wewnątrz basenu)
- `⚡` - Message Flow (komunikacja między basenami)
- `⌚` - Zdarzenie czasowe (timer)
- `│` - Ścieżka alternatywna
- `┌─┐` - Przekazanie między torami (w tym samym basenie)
- `╔═╗` - Basen (Pool) - organizacja
- `║ ║` - Tor (Lane) - dział w organizacji

---

## 🔑 Kluczowe Message Flows (komunikacja między organizacjami)

### 1️⃣ Fabryka ⚡ → Firma transportowa
**Typ**: Zlecenie transportu  
**Zawartość**: 
- Lista palet (RFID tags)
- Dokumenty elektroniczne (e-CMR)
- Adres dostawy, slot czasowy
- Tracking number

**Trigger**: Zamówienie od sklepu + gotowe palety w magazynie

---

### 2️⃣ Firma transportowa ⚡ → Fabryka
**Typ**: Potwierdzenie odbioru  
**Zawartość**:
- Lista potwierdzonych palet (RFID scan)
- Timestamp załadunku
- Podpis kierowcy (elektroniczny)

**Trigger**: Załadunek zakończony

---

### 3️⃣ Firma transportowa ⚡ → Sklep
**Typ**: Powiadomienie o dostawie  
**Zawartość**:
- ETA (2h przed, 30 min przed)
- Link do trackingu GPS
- Lista palet
- Dokumenty dostawy

**Trigger**: 
- Kierowca w drodze
- TO BE: Automatyczne z systemu TMS

---

### 4️⃣ Sklep ⚡ → Firma transportowa
**Typ**: Potwierdzenie odbioru / Reklamacja  
**Zawartość**:
- e-Podpis pracownika sklepu
- Timestamp rozładunku
- Wynik kontroli (ilość, temp.)
- Ewentualnie: Protokół reklamacyjny

**Trigger**: Rozładunek zakończony

---

### 5️⃣ Sklep ⚡ → Klient
**Typ**: Informacja o dostępności  
**Zawartość**:
- Produkt dostępny w sklepie
- Cena, promocje
- Lokalizacja w sklepie (TO BE: mapa w app)

**Trigger**: Produkt wystawiony na półkę

---

### 6️⃣ Klient ⚡ → Sklep
**Typ**: Zakup / Reklamacja / Opinia  
**Zawartość**:
- Płatność
- Ewentualnie: Reklamacja online (zdjęcie, opis)
- Ewentualnie: Ocena produktu (1-5 gwiazdek)

**Trigger**: Transakcja w sklepie / Problem z produktem

---

### 7️⃣ Sklep ⚡ → Fabryka
**Typ**: Zamówienie / Reklamacja  
**Zawartość**:
- Zamówienie produktów (system B2B)
- Ilości, termin dostawy
- Ewentualnie: Reklamacja jakościowa produktu

**Trigger**: 
- Niski stan magazynowy
- Problem z produktem (nie z transportem)

---

### 8️⃣ Fabryka ⚡ → Sklep
**Typ**: Potwierdzenie zamówienia  
**Zawartość**:
- Potwierdzenie przyjęcia zamówienia
- Planowany termin realizacji
- Numer zlecenia

**Trigger**: Zamówienie przyjęte do realizacji

---

## 📊 Mapa przepływu danych (TO BE)

```
┌─────────────────────────────────────────────────────────────────┐
│                     EKOSYSTEM CYFROWY                            │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐             │
│  │ FABRYKA  │ ←──→ │ TRANSPORT│ ←──→ │  SKLEP   │             │
│  │   ERP    │ API  │   TMS    │ API  │   WMS    │             │
│  │   MES    │      │          │      │          │             │
│  │   QMS    │      │   GPS    │      │          │             │
│  │   WMS    │      │  Temp    │      │          │             │
│  └────┬─────┘      └────┬─────┘      └────┬─────┘             │
│       │                 │                  │                    │
│       └────────────────┬┴──────────────────┘                   │
│                        │                                        │
│                  ┌─────▼─────┐                                 │
│                  │   CLOUD   │                                 │
│                  │ IoT + AI  │                                 │
│                  │ Analytics │                                 │
│                  └─────┬─────┘                                 │
│                        │                                        │
│                  ┌─────▼─────┐                                 │
│                  │  KLIENT   │                                 │
│                  │    App    │                                 │
│                  │    Web    │                                 │
│                  │  QR scan  │                                 │
│                  └───────────┘                                 │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🎯 Punkty synchronizacji między basenami

| Punkt | Baseny | Typ | AS IS | TO BE |
|-------|--------|-----|-------|-------|
| **P1** | Fabryka → Transport | Zlecenie | Telefon/Email | API automatyczne |
| **P2** | Transport → Fabryka | Potwierdzenie | Podpis papier | RFID + e-podpis |
| **P3** | Transport → Sklep | Powiadomienie | Telefon | API/SMS auto |
| **P4** | Sklep → Transport | Potwierdzenie | Podpis papier | e-podpis tablet |
| **P5** | Sklep → Klient | Dostępność | Fizyczna półka | App + fizyczna |
| **P6** | Klient → Sklep | Zakup | Kasa | Kasa + self-checkout |
| **P7** | Sklep → Fabryka | Zamówienie | Telefon/Fax | System B2B auto |

---

## 🔥 Ścieżki krytyczne (Critical Paths)

### Ścieżka główna (Happy Path) - wszystkie 4 baseny:

```
START (Fabryka) 
→ Produkcja (10 kroków Piekarnia + 9 Topping + 1 Zamrażanie + 2 Kontrola + 6 Pakowanie + 6 Magazyn)
→ [34 kroki wewnętrzne]
⚡ Message: Zlecenie transportu
→ Transport (9 kroków)
⚡ Message: Powiadomienie sklepu
→ Sklep (10 kroków)
⚡ Message: Dostępność
→ Klient (6 kroków)
→ END (Konsumpcja)
```

**Całkowity czas:**
- Produkcja: ~45 min (AS IS) / ~38 min (TO BE)
- Magazynowanie: 0-90 dni (średnio 14 dni)
- Transport: 2-24 godziny (zależnie od odległości)
- Sklep: 1-7 dni (zależnie od rotacji)
- Klient: 1-30 dni (przechowywanie w domu)

### Ścieżki alternatywne (Exception Paths):

1. **Odrzucenie w Fabryce** (Lane 1.2 lub 1.4):
   - → END (Odrzucenie) → Analiza przyczyn → Raport QMS

2. **Reklamacja temperatury** (Transport → Sklep):
   - → Protokół reklamacyjny → Message do Transport/Fabryka
   - → Kompensata / Wymiana towaru

3. **Reklamacja jakościowa** (Klient):
   - → Message do Sklep lub Fabryka
   - → Weryfikacja (numer partii przez QR)
   - → Zwrot / Kompensata

---

## 📈 Analiza wąskich gardeł (Bottleneck Analysis)

### Basen 1 (Fabryka):
- **AS IS**: Kontrola jakości manualna (10 pizz/min), Paletyzacja ręczna (12 min/paleta)
- **TO BE**: Garowanie ciasta (fixed time ~30 min - proces biologiczny, nie do przyspieszenia)
- **Rozwiązanie TO BE**: Równoległe linie garowania

### Basen 2 (Transport):
- **AS IS**: Brak monitoring real-time (reakcja dopiero po dostawie)
- **TO BE**: Czas transportu (fizyczna odległość)
- **Rozwiązanie TO BE**: Optymalizacja tras przez TMS, monitoring predykcyjny

### Basen 3 (Sklep):
- **AS IS**: Manualna weryfikacja dostawy (10-15 min)
- **TO BE**: Rotacja produktu (zależy od popytu)
- **Rozwiązanie TO BE**: RFID auto-scan (2 min), predykcja popytu

### Basen 4 (Klient):
- Brak wąskich gardeł (proces nieprodukcyjny)

---

## 🔄 Przepływ wartości (Value Stream)

### Działania dodające wartość (Value-Adding):
- ✅ Przygotowanie ciasta (Basen 1)
- ✅ Nakładanie składników (Basen 1)
- ✅ Pieczenie/Zamrażanie (Basen 1)
- ✅ Pakowanie (Basen 1)
- ✅ Transport (Basen 2)
- ✅ Sprzedaż (Basen 3)
- ✅ Konsumpcja (Basen 4)

### Działania niezbędne, ale nie dodające wartości bezpośrednio (Necessary Non-Value-Adding):
- 🟡 Kontrola jakości (Basen 1) - niezbędne dla bezpieczeństwa
- 🟡 Magazynowanie (Basen 1, 3) - bufor między produkcją a popytem
- 🟡 Weryfikacja dostaw (Basen 3) - kontrola transakcji

### Działania marnotrawstwa (Waste - TO BE eliminuje/minimalizuje):
- ❌ Ręczne wprowadzanie danych → TO BE: Automatyczne (RFID, API)
- ❌ Oczekiwanie na informacje → TO BE: Real-time communication
- ❌ Papierowa dokumentacja → TO BE: E-dokumenty
- ❌ Zbędne przemieszczanie → TO BE: AGV optymalne trasy
- ❌ Nadprodukcja/Braki zapasów → TO BE: AI predykcja popytu

---

**Podsumowanie**: Proces obejmuje 4 organizacje (baseny), ~60 kroków całkowitych, 8 kluczowych Message Flows. TO BE wprowadza automatyzację redukcującą czas reakcji o 92% i eliminującą marnotrawstwo.
