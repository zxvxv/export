# 🚀 IntegraSoft Shadow-PV PRO v2.05

Inteligentny system zarządzania eksportem dla falowników Deye. 
Maksymalizuje zyski z RCE (cen godzinowych), dbając o bezpieczeństwo przed OSD.

---

## 💎 Główna Funkcja: "Cierpliwy Sprzedawca"

Większość systemów popełnia błąd: sprzedaje prąd z baterii, gdy tylko cena przekroczy próg. 
**Shadow-PV PRO jest mądrzejszy.** 1. **Szukanie Szczytu:** Jeśli cena jest dobra, ale sensor PSE mówi, że "Najdroższe Okno" jest później – system nie dotyka baterii. Sprzedaje tylko nadwyżkę słońca.
2. **Atak na Szczyt:** Dopiero w najdroższym oknie dnia uruchamia "Mnożnik Agresywności" i zrzuca tanią energię z baterii po najwyższym kursie.
3. **Cloud-Breaker:** Jeśli w najdroższym oknie nie ma słońca, system symuluje "wyjście słońca zza chmur", modulując moc od 60% do 100%. Wygląda to naturalnie na liczniku OSD.

---

## 🛠️ Trzy Poziomy Inteligencji

* **Cena poniżej progu:** System blokuje eksport. Cała moc idzie w magazyn.
* **Cena OK, ale nie szczyt:** Eksportujemy tylko (Słońce + Dom). Magazyn czeka.
* **Najdroższe okno:** Pełna moc, mnożnik i symulacja zjawisk pogodowych.

---

## 🛡️ Bezpieczeństwo 24/7

* **Matryca 12 m-cy:** Twardy kalendarz godzinowy dla Polski. Zero eksportu w nocy, niezależnie od cen.
* **SOC 100% Safety:** Jeśli bateria jest pełna, system ignoruje niskie ceny i puszcza prąd w sieć, by falownik nie ograniczał produkcji (clipping).
* **Pełna Kompatybilność:** Obsługuje MPPT falownika oraz mikroinwertery na porcie GEN.

---

## ⚙️ Szybki Start
1. Zaimportuj Blueprint.
2. Wybierz swój profil (Lewa Ręka, OZE, itd.).
3. Ustaw **Moc Zgłoszoną** (bezpiecznik OSD) i **Cenę Minimalną**.
4. Resztę robi algorytm.

[![Open Blueprint Import](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fzxvxv%2Fexport%2Fblob%2Fmain%2Fexport.yaml)
