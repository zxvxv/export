# 🚀 IntegraSoft Shadow-PV PRO (Cloud-Breaker & RCE)

**IntegraSoft Shadow-PV PRO** to potężny algorytm dla inwerterów hybrydowych Deye w Home Assistant. 

Został stworzony jako system **Plug & Play**, aby maksymalizować zyski z magazynów energii. Robi to w sposób całkowicie bezpieczny, symulując przed operatorem (OSD) idealnie naturalną pracę fotowoltaiki.

---

## ⚠️ Jaki problem rozwiązujemy?

Klienci z niezgłoszonymi magazynami nie mogą po prostu "wypchnąć" 5 kW do sieci po zachodzie słońca. 
Systemy OSD natychmiast wykryją to jako anomalię. 

Klasyczny falownik nie potrafi płynnie "domieszkować" energii z baterii do sieci. Nasz system ukrywa pracę baterii w cieniu pracy Twoich paneli.

---

## 🧠 Jak działa Ghost Export? (Logika)

Algorytm opiera się na **Efekcie Pustego Domu** oraz **Mnożniku Zysku**.
Działa w czasie rzeczywistym (co 2 minuty) według poniższego schematu:

> **Docelowy Eksport = [(PV + Mikroinwertery) * Mnożnik] + Zużycie Domu**

* **Krok 1:** System sumuje produkcję z dachu i mikroinwerterów.
* **Krok 2:** Mnoży wynik przez ustaloną wartość (np. 1.50). Jeśli panele dają 2 kW, system dąży do 3 kW (dobierając 1 kW z magazynu).
* **Krok 3:** Koryguje wynik o aktualne zużycie domu. Jeśli włączysz czajnik (2 kW), falownik podniesie limit wysyłania do 5 kW.

**Efekt:** Na e-liczniku OSD zawsze widać piękny, stabilny eksport (np. 3 kW), niezależnie od tego, co robisz w domu. Zarabiasz więcej.

---

## 🌩️ Technologia Cloud-Breaker (Przełamywacz Chmur)



Co zrobić, gdy cena giełdowa RCE jest na szczycie, a nad Twoim domem wiszą grube chmury?
Wysłanie płaskiego 6 kW z baterii w deszczowy dzień to pewna kontrola. 

**Wkracza moduł Cloud-Breaker:**
* Gdy system wykryje najdroższe 2-godzinne okno sprzedażowe i brak słońca, uruchamia matematyczną symulację.
* Falownik nie uderza stałą mocą. Zamiast tego tworzy **płynną, poszarpaną krzywą** (od 60% do 100% mocy).
* Dla OSD wygląda to jak naturalne, lokalne przejaśnienie i wyjście słońca zza chmur. 

---

## 🛡️ Tarcze ochronne i rentowność

System posiada 3 kuloodporne zabezpieczenia, które chronią Twój portfel i sprzęt:

1. **💰 Blokada taniej sprzedaży (Ochrona Kapitału)**
   * Ustalasz swój próg (np. 0.20 zł). 
   * Jeśli giełda płaci mniej, system odcina eksport do sieci. 
   * Falownik ładuje magazyn na 100% i darmowo zasila dom.

2. **🔋 Zawór Bezpieczeństwa (Over-ride SOC 100%)**
   * Cena jest niska, ale Twój magazyn dobija w południe do 100%. 
   * Falownik zablokowałby panele (clipping), marnując słońce. 
   * IntegraSoft to wykrywa, znosi blokadę cenową i wypycha darmowy prąd do sieci, ratując Cię przed stratami.

3. **🌙 Matryca Astronomiczna (Twarda Blokada Nocna)**
   * W kod zaszyto 12-miesięczny kalendarz pór dnia dla Polski.
   * W grudniu po godzinie 15:00 system fizycznie nie wyśle prądu do sieci.
   * Działa to niezależnie od Internetu, gwarantując 100% bezpieczeństwa przed OSD.

---

## ⚙️ Instalacja (Krok po Kroku)

Nie potrzebujesz zewnętrznych integracji pogodowych. Wystarczy integracja `rce_pse`.

1. Kliknij poniższy przycisk, aby zaimportować Blueprint.
2. W oknie automatyzacji podaj prefiks urządzeń (domyślnie `deye_inverter`).
3. Wybierz swój profil encji (Lewa-Ręka, OZE4HOME, Dashboard lub SUN-12K).
4. Wpisz Zgłoszoną Moc PV (np. 6000 W).
5. Ustal mnożnik agresywności i próg cenowy.
6. **Zapisz i gotowe! System zaczyna zarabiać.**

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fzxvxv%2Fexport%2Fblob%2Fmain%2Fexport.yaml)
