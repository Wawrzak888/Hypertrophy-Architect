Hypertrophy Architect / Jack Gym Architect

Witamy w projekcie kalkulatora diety kulturystycznej. Ta aplikacja internetowa została zaprojektowana, aby pomóc użytkownikom w obliczaniu dziennego zapotrzebowania kalorycznego i makroskładników w celu optymalizacji hipertrofii mięśniowej.

Funkcje

Obliczanie Zapotrzebowania: Automatycznie oblicza dzienne zapotrzebowanie na kalorie, białko, węglowodany i tłuszcze na podstawie parametrów użytkownika (wiek, waga, wzrost, poziom aktywności, cel).

Kreator Posiłków: Umożliwia użytkownikom komponowanie codziennych posiłków poprzez dodawanie produktów z obszernej bazy danych.

Baza Danych Produktów: Zawiera setki produktów spożywczych z precyzyjnymi danymi makro.

Dodawanie/Edycja Produktów: Użytkownicy mogą dodawać własne proste produkty.

Nadpisywanie Produktów: Możliwość edycji i nadpisywania domyślnych produktów.

Kompozytor Dań: Zaawansowana funkcja pozwalająca na tworzenie złożonych posiłków (np. zup, dań) z wielu składników i zapisywanie ich jako jeden "produkt" w bazie danych.

Asystent Posiłku AI (Google Gemini):

Analiza poszczególnych posiłków (a nie całego dnia).

Po kliknięciu ikony AI przy posiłku, asystent analizuje jego skład w kontekście celów użytkownika (obliczonych na podstawie docelowej liczby posiłków).

Dostarcza konkretnych rekomendacji, np. "Dodaj 50g ryżu" lub "Osiągnąłeś próg leucynowy, świetna robota!".

Eksport do PDF: Generuje estetyczny raport PDF z całodniowym planem żywieniowym, gotowy do wydruku lub zapisu.

Lokalna Pamięć: Aplikacja zapamiętuje dane użytkownika i dzisiejszy plan posiłków w pamięci podręcznej przeglądarki (localStorage), dzięki czemu dane nie znikają po odświeżeniu strony.

Jak Uruchomić (Wdrożenie na Vercel)

Ta aplikacja jest zaprojektowana do działania w środowisku serwerowym (jak Vercel), a nie jako lokalny plik file:///. Uruchomienie jej przez dwukrotne kliknięcie pliku HTML spowoduje, że Asystent AI nie będzie działał z powodu ograniczeń bezpieczeństwa przeglądarki (CORS).

Zalecana metoda wdrożenia:

Struktura Projektu: Upewnij się, że Twój projekt ma następującą strukturę:

/ (główny folder)
|-- Hypertrophy Architect.html  (lub zmień nazwę na index.html)
|-- /api
    |-- ai.js


Ważne: Plik Hypertrophy Architect.html musi być głównym plikiem HTML w katalogu głównym. Vercel automatycznie rozpozna plik index.html jako stronę główną. Jeśli używasz innej nazwy, może być konieczna konfiguracja.

GitHub: Wrzuć cały projekt (plik HTML i folder api) do repozytorium na GitHub.

Vercel:

Załóż darmowe konto na Vercel.

Połącz swoje konto Vercel z kontem GitHub.

Stwórz "Nowy Projekt" w Vercel i wybierz swoje repozytorium z GitHub.

Vercel powinien automatycznie wykryć, że jest to prosty projekt (Static Site) z funkcją serwerową (/api/ai.js).

Klucz API (NAJWAŻNIEJSZE!):

Asystent AI wymaga klucza API do Google Gemini. Musisz wygenerować swój własny, darmowy klucz w Google AI Studio.

W panelu swojego projektu na Vercel, przejdź do zakładki Settings -> Environment Variables (Zmienne Środowiskowe).

Dodaj nową zmienną o nazwie: GEMINI_API_KEY

W polu wartości wklej swój klucz API wygenerowany z Google AI Studio.

Zapisz i uruchom "Redeploy" (ponowne wdrożenie), aby Vercel załadował nowy klucz.

Po wykonaniu tych kroków Twoja aplikacja będzie dostępna publicznie pod adresem *.vercel.app, a Asystent AI będzie działał poprawnie i bezpiecznie.

Stack Technologiczny

Frontend: HTML5, Tailwind CSS, Czysty JavaScript (ES6+)

Backend (API): Funkcja serwerowa Vercel (Node.js)

AI: Google Gemini API (gemini-2.5-flash-preview-09-2025)

Biblioteki JS:

html2canvas (do generowania obrazu dla PDF)

jspdf (do tworzenia pliku PDF)

marked.js (do formatowania odpowiedzi AI z Markdown na HTML)

Autor

Tomasz Wawrzak
