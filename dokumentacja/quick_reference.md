# 🚀 Quick Reference Guide - Proces produkcji mrożonej pizzy

## Szybki dostęp do kluczowych informacji

---

## 📊 Metryki w skrócie

| Metryka | AS IS | TO BE | Zmiana |
|---------|-------|-------|--------|
| Wydajność | 10k/dzień | 12k/dzień | +20% ⬆️ |
| Odrzuty | 2% | 0.5% | -75% ⬇️ |
| OEE | 75% | 85% | +10pp ⬆️ |
| Czas cyklu | 45 min | 38 min | -15% ⬇️ |
| Przestoje | 8h/m-c | 5h/m-c | -37% ⬇️ |
| **ROI** | - | **3.3 lata** | - |
| **Inwestycja** | - | **5M PLN** | - |

---

## 🏊 Struktura BPMN - AS IS vs TO BE

### AS IS: **3 baseny** (transport własny w fabryce)
1. 🏭 **Fabryka** (7 torów): Piekarnia, Topping, Produkcja, Kontrola, Pakowanie, Magazyn, **Dystrybucja**
2. 🏪 **Sklep** (1 tor): Odbiór, weryfikacja, sprzedaż
3. 👤 **Klient** (1 tor): Zakup, konsumpcja

**Problem**: Transport wewnątrz fabryki (drogi, nieefektywny)

---

### TO BE: **4 baseny** (outsourcing logistyki!)

1. 🏭 **Fabryka** (6 torów - **BEZ** transportu)
   - Piekarnia, Topping, Produkcja, Kontrola, Pakowanie, Magazyn

2. 🚚 **Firma transportowa** (**NOWY BASEN! Outsourcing**)
   - Profesjonalny przewoźnik, GPS real-time, TMS, SLA
   - 💰 Oszczędność: **-600k PLN/rok**

3. 🏪 **Sklep** (1 tor)
   - RFID auto-scan, e-potwierdzenie

4. 👤 **Klient** (1 tor)
   - QR traceability, online

**⚡ Główne usprawnienie**: Transport z toru fabryki → osobna firma (outsourcing!)

---

## 🔑 10 Reguł biznesowych

| ID | Reguła | Priorytet |
|----|--------|-----------|
| BR-001 | Kontrola jakości po toppingu | ⚠️ Wysoki |
| BR-002 | Detektor metali - zero tolerancji | 🔴 Krytyczny |
| BR-003 | Normy wagowe ±5% (350g → 332-367g) | ⚠️ Wysoki |
| BR-004 | Temperatura zamrażania -33°C ±2°C | 🔴 Krytyczny |
| BR-005 | Temperatura magazynu -23°C ±2°C | ⚠️ Wysoki |
| BR-006 | Temperatura transportu -18°C ±3°C | ⚠️ Wysoki |
| BR-007 | Czas w magazynie max 90 dni (FEFO) | 🟡 Średni |
| BR-008 | Akceptacja surowców (certyfikaty) | ⚠️ Wysoki |
| BR-009 | Reakcja AI na odchylenia (TO BE) | ⚠️ Wysoki |
| BR-010 | Predykcyjne UTR (TO BE) | 🟡 Średni |

---

## ⚖️ 7 Tabel decyzyjnych

1. **Kontrola toppingu** - 8 reguł (pokrycie, składniki, czystość)
2. **Detektor metali** - 3 reguły (wykryto/nie, kalibracja)
3. **Normy wagowe** - 5 reguł (zakres, trend odchyleń)
4. **Temp. zamrażania** - 5 reguł (zakres -31 do -35°C)
5. **Wysyłka z magazynu** - 5 reguł (wiek produktu, QC)
6. **Transport** - 4 reguły (temp., czas odchylenia)
7. **AI korygujące** - 4 reguły (TO BE, poziom problemu)

---

## 🎯 3 Główne bramki decyzyjne

### 1️⃣ Kontrola po toppingu (Lane 2)
- ✅ OK → zamrażanie
- ❌ NIE → odrzuć + analiza (TO BE: auto)

### 2️⃣ Detektor metali (Lane 4)
- ✅ Brak → ważenie
- ❌ Wykryto → STOP linii + alarm + usunięcie

### 3️⃣ Kontrola wagi (Lane 4)
- ✅ 332-367g → pakowanie
- ❌ Poza → odrzuć + kalibracja (TO BE: auto)

---

## 🛠️ Technologie TO BE

| Tech | Zastosowanie | Korzyść |
|------|-------------|---------|
| **AI Vision** | Kontrola jakości | 99.5% wykrywalność |
| **IoT** | Monitoring temp. | Real-time alerty |
| **Robot** | Paletyzacja | 3x szybciej |
| **AGV** | Transport magazyn | Bezzałogowy |
| **AS/RS** | Składowanie | Auto pobieranie |
| **RFID/QR** | Śledzenie | 100% traceability |
| **AI ML** | Predykcja | Zapasy, awarie |

---

## 👥 Kluczowi interesariusze

### Ludzie (12):
- Dyrektor Produkcji
- Kierownik Piekarni
- Kierownik Toppingu
- Operatorzy (12/zmiana)
- Specjaliści QC (3-4/zmiana)
- Magazynierzy (4-6/zmiana)
- Technicy UTR (2-3/zmiana)
- Koordynator logistyki
- Kierowcy (~10-20)
- Dostawcy surowców
- Sklepy (klienci B2B)
- Konsumenci finalni

### Systemy (7):
- ERP, MES, QMS, WMS (AS IS)
- TMS, IoT, AI/ML (TO BE)

---

## 💰 Ekonomia projektu

### Inwestycja TO BE: 5M PLN
- Faza 1 (IoT, dashboard): 500k
- Faza 2 (AI Vision): 1.2M
- Faza 3 (Robot, RFID): 1.5M
- Faza 4 (AGV, AS/RS): 1.8M
- Faza 5 (TMS, GPS): 500k
- Faza 6 (AI UTR): 500k

### Oszczędności: 1.5M PLN/rok
- Odrzuty: 500k
- Praca: 300k
- Przestoje: 250k
- Transport: 150k
- Energia: 100k
- Zapasy: 200k

### ROI: 3.3 lata

---

## 📅 Timeline wdrożenia

```
Rok 1: ████░░░░░░░░ Fazy 1-2 (IoT + AI Vision)
Rok 2: ████████░░░░ Fazy 3-4 (Robot + Magazyn)
Rok 3: ████████████ Fazy 5-6 (Logistyka + UTR)
```

**Start**: Q2 2026  
**Koniec**: Q2 2029  
**Czas**: 36 miesięcy

---

## ⚠️ Top 5 ryzyk

1. **Wysokie koszty** → etapowanie, leasing
2. **Integracja IT** → POC, testy
3. **Opór pracowników** → szkolenia, komunikacja
4. **Brak kompetencji** → rekrutacja AI/IoT
5. **Awarie** → systemy rezerwowe, SLA

---

## ✅ Checklist wdrożenia

### Przed startem:
- [ ] Zatwierdzenie budżetu 5M PLN
- [ ] Powołanie zespołu projektowego
- [ ] Wybór Project Managera
- [ ] Analiza dostawców (RFP)
- [ ] Aplikacja o dotacje UE

### Faza 1 (Quick Wins):
- [ ] Czujniki IoT temperatury
- [ ] Dashboard real-time
- [ ] API integracje
- [ ] Szkolenia IoT

### Faza 2 (AI Vision):
- [ ] Kamery wysokiej rozdzielczości
- [ ] Serwery AI/GPU
- [ ] Trening modeli ML
- [ ] Pilot w Lane 2

### Faza 3 (Robotyzacja):
- [ ] Robot paletyzujący
- [ ] Owijarka automatyczna
- [ ] System RFID
- [ ] Szkolenia safety

### Faza 4 (Smart Warehouse):
- [ ] AGV (3-5 pojazdów)
- [ ] AS/RS (system regałowy)
- [ ] AI zapasy
- [ ] WMS upgrade

### Faza 5 (Smart Logistics):
- [ ] GPS+temp. w samochodach
- [ ] TMS deployment
- [ ] API do sklepów
- [ ] Szkolenia kierowców

### Faza 6 (Predykcja):
- [ ] IoT na maszynach
- [ ] AI models trenowanie
- [ ] Dashboard UTR
- [ ] Procedury nowe

---

## 📞 Kontakty kluczowe

| Rola | Odpowiedzialność | Priorytet |
|------|-----------------|-----------|
| Dyrektor Produkcji | Akceptacja | ⭐⭐⭐ |
| Project Manager | Wdrożenie | ⭐⭐⭐ |
| IT Lead | Integracja | ⭐⭐⭐ |
| Kier. Piekarni | Lane 1 | ⭐⭐ |
| Kier. Toppingu | Lane 2 | ⭐⭐ |
| QC Manager | Kontrola | ⭐⭐⭐ |

---

## 📚 Dokumenty do przeczytania

### Szybki start (15 min):
1. README.md
2. podsumowanie_wykonawcze.md
3. Ten dokument (quick_reference.md)

### Szczegóły BPMN (30 min):
4. baseny_i_tory_BPMN.md
5. schemat_procesu_tekstowy.md

### Deep dive (2h):
6. diagram_AS_IS_opis.md
7. diagram_TO_BE_opis.md
8. analiza_AS_IS_vs_TO_BE.md

### Reguły i decyzje (1h):
9. reguly_biznesowe.md
10. tabela_decyzyjna.md

### Administracja (30 min):
11. rejestr_procesow.md
12. lista_interesariuszy.md

---

## 🔍 Szybkie wyszukiwanie

**Szukasz informacji o...**

- **Temperaturze**: BR-004, BR-005, BR-006 + schemat_procesu (mapa temp.)
- **Kontroli jakości**: BR-001, BR-002, BR-003 + Lane 2, 4
- **Robotyzacji**: diagram_TO_BE (Lane 5) + analiza (Faza 3)
- **AI**: diagram_TO_BE (AI Vision, predykcja) + podsumowanie
- **Kosztach**: analiza_AS_IS_vs_TO_BE (sekcja finansowa)
- **Timeline**: analiza (Plan wdrożenia) + podsumowanie
- **Ryzykach**: rejestr_procesow + analiza + podsumowanie
- **Interesariuszach**: lista_interesariuszy.md (19 ról)
- **KPI**: rejestr_procesow + podsumowanie
- **Systemach IT**: lista_interesariuszy (systemy) + baseny

---

## 📊 Dashboard KPIs do monitorowania

### Produkcja (dzienna):
- [ ] Wydajność: ___/12,000 pizz
- [ ] Odrzuty: ___%  (cel: <0.5%)
- [ ] OEE: ___%  (cel: >85%)
- [ ] Przestoje: ___ min

### Jakość (dzienna):
- [ ] Detektor metali: ___/0 alarmów
- [ ] Waga poza normą: ___%  (cel: <2%)
- [ ] Temp. tunelu: -__°C  (cel: -31 do -35)
- [ ] Temp. magazynu: -__°C  (cel: -21 do -25)

### Logistyka (tygodniowa):
- [ ] Dostawy: ___  (cel: 100%)
- [ ] Przekroczenie temp. transport: ___  (cel: 0)
- [ ] Reklamacje: ___  (cel: <0.1%)
- [ ] On-time delivery: ___%  (cel: >98%)

---

## 💡 Pro Tips

### Dla operatorów:
- 🔔 Reaguj na alarmy < 5 min
- 📊 Sprawdzaj dashboard co godzinę
- 📝 Raportuj anomalie natychmiast
- 🎓 Bierz udział w szkoleniach

### Dla kierowników:
- 📈 Monitoruj trendy (nie tylko punkty)
- 🤝 Angażuj zespół w usprawnienia
- 💬 Komunikuj "why" zmian
- 🎯 Cele SMART dla zespołu

### Dla zarządu:
- 📊 Dashboard weekly review
- 💰 ROI tracking quarterly
- 🚀 Celebrate quick wins
- 🔮 Plan ahead 2-3 fazy

---

## 🎯 Cele krótkoterminowe (Q1-Q2 2026)

- [ ] Prezentacja zarządowi
- [ ] Decyzja GO/NO-GO
- [ ] Tender dostawcy
- [ ] Budżet zatwierdzony
- [ ] PM recruited
- [ ] Aplikacja dotacje
- [ ] Start Fazy 1

**Deadline Q1 prezentacji**: 31.03.2026  
**Deadline Q2 start**: 30.06.2026

---

## ✅ Status projektu

- [x] Analiza AS IS - **DONE**
- [x] Projektowanie TO BE - **DONE**
- [x] Analiza finansowa - **DONE**
- [x] Plan wdrożenia - **DONE**
- [ ] Prezentacja zarządu - **TODO Q1 2026**
- [ ] Tender dostawcy - **TODO Q1 2026**
- [ ] Start wdrożenia - **TODO Q2 2026**

---

**Wersja**: 1.0  
**Data**: 2025-10-17  
**Next review**: Q1 2026

