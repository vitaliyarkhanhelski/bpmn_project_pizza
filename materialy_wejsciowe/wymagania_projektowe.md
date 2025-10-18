## 🧩 Zadanie: Modelowanie procesu biznesowego w BPMN

### 🎯 Cel zadania

Zidentyfikować rzeczywisty proces (na podstawie krótkiego filmiku z YouTube), przedstawić jego przebieg **AS IS** (stan obecny), a następnie zaprojektować jego wersję usprawnioną **TO BE** (stan docelowy).

Następnie przeprowadzić analizę procesu, zdefiniować reguły biznesowe i opracować tabelę decyzyjną.

---

### 📹 1. Wybór materiału

- Znaleźć **filmik na YouTube** przedstawiający dowolny proces (np. obsługa klienta, proces reklamacji, przyjęcie zamówienia, przygotowanie kawy, obsługa paczki w magazynie, itp.).
- Czas trwania filmu: **maksymalnie 5 minut**.
- Na podstawie filmu zidentyfikować proces i uczestniczące w nim role.

---

### 🧭 2. Modelowanie procesu

### a) Diagram **AS IS**

- Przedstawia **aktualny stan procesu** (tak, jak przebiega na filmiku).
- Zawiera wszystkie kroki i role tak, jak są obecnie realizowane.
- Diagram AS IS należy **zamodelować w narzędziu do BPMN**.

### b) Diagram **TO BE**

- Przedstawia **stan docelowy** po usprawnieniach.
- Można dodać automatyzacje, usunięcie zbędnych kroków, lepszy przepływ informacji itp.
- Diagram TO BE należy **zamodelować w narzędziu do BPMN**.

---

### 🧱 3. Struktura modelu BPMN

- **Jeden proces = jeden basen (pool)**.
- W każdym basenie mogą znajdować się **tory (lanes)** odpowiadające rolom.
- Nazwa procesu powinna być **czytelna i opisowa** (np. „Proces obsługi zamówienia online”).
- Jeżeli występują podprocesy, oznaczyć je zgodnie z semantyką BPMN.

---

### 👥 4. Interesariusze

- Wypisać **wszystkich uczestników procesu** (osoby lub systemy).
- Dla każdego interesariusza określić **rolę** (np. Klient, Pracownik, System, Kierownik).
- Opisać **sposób komunikacji między nimi** (np. e-mail, rozmowa, system CRM, formularz online).

---

### 📊 5. Rejestr procesów

- Utworzyć **rejestr procesów**, zawierający co najmniej:
    - Nazwę procesu
    - Krótki opis
    - Cel procesu
    - Interesariuszy
    - Status (AS IS / TO BE)
    - Powiązane reguły biznesowe
    - Autor/odpowiedzialny

---

### ⚙️ 6. Reguły biznesowe

- Opracować **kilka reguł biznesowych** (np. „Zamówienie o wartości > 1000 zł wymaga akceptacji kierownika”).
- Reguły te powinny być **związane z procesem** z filmiku.

---

### 🧮 7. Tabela decyzyjna

- Opracować **tabelę decyzyjną (Decision Table)** opisującą, jak decyzje są podejmowane w procesie (np. kryteria akceptacji zamówienia, ścieżki reklamacji, itd.).
- Każda tabela powinna zawierać:
    - Warunki (input)
    - Reguły
    - Wyniki (output)

---

### 🔍 8. Analiza i weryfikacja

- Przeprowadzić analizę różnic między AS IS i TO BE:
    - Co zostało usprawnione?
    - Jakie problemy rozwiązano?
    - Jakie są korzyści z nowego procesu?
- Weryfikacja: sprawdzić poprawność semantyki BPMN (np. poprawne zdarzenia startowe/końcowe, przepływy, bramki).

---

### ✅ Efekty końcowe (co należy oddać)

1. Filmik (link do YouTube).
2. Diagram **AS IS** (np. w formacie .bpmn lub zrzut ekranu).
3. Diagram **TO BE**.
4. Rejestr procesów.
5. Lista interesariuszy z rolami i komunikacją.
6. Reguły biznesowe.
7. Tabela decyzyjna.
8. Analiza i weryfikacja (krótki opis w Word/PDF).