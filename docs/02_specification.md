## Słowny opis wymagań

### Legenda
UKB - użytkownik konta bankowego - klient banku który posiada w nim konto, środki na tym koncie są własnością klienta.
    Klient może być osobą prywatną, lub firmą.

\begin{figure}[hbtp]
    \makebox[\textwidth][c]{
        \includegraphics[width=\paperwidth]{./docs/requirements_diagram.png}
    }
    \caption{Diagram wymagań}
\end{figure}



### Wymagania funkcjonalne aplikacja klienta
0. Potencjalny klient banku może zarejestrować nowe konto bankowe.
0. UKB ma wgląd do stanu swojego konta bankowego w PLN.
0. UKB ma wgląd do przypisanych do konta i aktywnych lokat.
0. UKB może przelewać pieniądze ze swojego konta bankowego na konto bankowe innego UKB tego samego systemu.
0. UKB może przelewać pieniądze ze swojego konta bankowego na konto bankowe innego UKB zewnętrzego systemu bankowego.
0. UKB może zakładać lokaty bankowe o określonym oprocentowaniu określonym w katalogu lokat banku.
0. UKB może włączyć lub wyłączyć opcję przewalutowanie przelewów ze swojego konta bankowego.
0. UKB ma prawo złożyć podanie elektroniczne o zamknięcie konta bankowe.
0. UKB może zamknąć lokatę przed terminem jej zakończenia.
0. UKB może stworzyć cykliczne zlecenie przelewu ze swojego konta.
0. UKB może edytować istniejące cykliczne zlecenie przelewu ze swojego konta.
0. UKB może zamknąć cykliczne zlecenie przelewu ze swojego konta.
0. UKB ma wgląd do historii wpływów i wypływów finansowych ze swojego konta.
0. UKB może rozpocząć, prowadzić i zakończyć chat z chatbotem w celu uzyskania pomocy i/lub oferty banku.

### Wymagania niefunkcjonalne

0. Podczas rejestracji trzeba podać: imię, nazwisko, PESEL, numer dokumentu tożsamości, adres do korespondencji, datę urodzenia.
0. Dostęp do konta UKB wymaga autoryzacji przez podanie danych dostępowych: loginu, hasła i kodu autoryzacji dwustopniowej (2FA).
0. System obsługuje po stronie użytkownika język polski m.in., generując komunikaty o błędach czy udostępniając interfejs użytkownika w tym języku.
0. Przelew/cykliczne zlecenie między UKB są możliwe tylko pod warunkiem posiadania wystarczających środków na koncie.
0. Przelew do banku, w którym waluta jest inna niż PLN jest możliwy wyłącznie, kiedy UKB ma włączoną opcję przewalutowania.
0. Warunkiem złożenia podania elektronicznego o zamknięcie konta jest nieposiadanie aktywnych lokat.
0. Zamknięcie przedterminowe wiąże się z utratą odsetek przez UKB.
0. Chatbot posiada dostępność 24 godziny na dobę przez 7 dni w tygodniu.
0. Implementacja systemu odbywa się w języku Java.

### Wymagania niefunkcjonalne aplikacja klienta
0. Dostęp do konta UKB wymaga autoryzacji przez podanie danych dostępowych: loginu i hasła.
0. System obsługuje po stronie użytkownika język polski m.in., generując komunikaty o błędach czy udostępniając interfejs użytkownika w tym języku.
0. Przelew między UKB jest możliwy tylko pod warunkiem posiadania wystarczających środków na koncie.
0. Przelew do banku, w którym waluta jest inna niż PLN jest możliwy wyłącznie, kiedy UKB ma włączoną opcję przewalutowania.
0. Aplikacja klienta jest aplikacją przeglądarkową.

### Wymagaania funkcjinalne system bazy danych
0. Właściciel banku może zmodyfikować katalog lokat banku.
0. Właściciel banku ma wgląd do wszystkich kont bankowych w banku.
0. System chatbota ma wgląd do katalogu lokat banku.
0. Właściciel banku może zmodyfikować opłaty za wykonywanie poszczególnych tranzakcji bankowych.

### Wymagania niefunkcjonalne system bazy danych
0. Terminal którym UKB się posługuje łączy się z bazą danych, przy użyciu nieuprzywilejowanego użytkownika
0. Katalog lokat banku jest możliwy tylko przez konto właściciela banku
0. System chatbota używa oddzielnego konta nieuprzywilijowanego.
0. Informacja zleceniu przelewu musi zostać zapisana w systemie.
0. Informacja o utworzeniu lokaty musi zostać zapisana w systemie.
0. Informacja o zamknięciu lokaty musi zostać zapisana w systemie.
0. W razie awarii bazy danych, środki klientów które posiadają nie ulegają zniszczeniu.
0. W razie awarii jednej serwerowni, system bazy danych nadal może działać bez problemów.
0. System bazy danych musi mieć możliwość osłużenia 10 zapytań na sekundę.
0. System bazy danych musi mieć możliwość obsłużenia 500000 połączeń.
0. System bazy danych nie może ulec uszkodzeniu przez błąd komunikacji z aplikacją klienta
0. System bazy danych nie może ulec uszkodzeniu przez złośliwie utworzone zapytanie z aplikacji klienta
0. System bazy danych nie może ulec uszkodzeniu przez złośliwie utworzone zapytanie z aplikacji klienta
0. Podczas logowania, aplikacja klienta zapisuje dane o logowaniu w bazie danych.
0. Rozszerzenie systemu bazy danych, musi być możliwe bez całkowitego przemodelowania infrastruktury teleinformatycznej.
