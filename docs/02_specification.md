# Słowny opis wymagań

## Legenda
UKB - użytkownik konta bankowego - klient banku który posiada w nim konto, środki na tym koncie są własnością klienta.
    Klient może być osobą prywatną, lub firmą.

\begin{figure}[hbtp]
    \makebox[\textwidth][c]{
        \includegraphics[width=\paperwidth]{./docs/requirements_diagram.png}
    }
    \caption{Diagram wymagań}
\end{figure}



## Wymagania funkcjonalne aplikacje klienckie
0. Potencjalny klient banku może zarejestrować nowe konto bankowe.
0. UKB może złożyć podanie o zamknięcie swojego konta bankowego.
0. UKB ma wgląd do stanu swojego konta bankowego w PLN.
0. UKB ma wgląd do historii wpływów i wypływów finansowych ze swojego konta.
0. UKB ma wgląd do przypisanych do konta i aktywnych lokat.
0. UKB może przelewać pieniądze ze swojego konta bankowego na konto bankowe innego UKB tego samego systemu.
0. UKB może przelewać pieniądze ze swojego konta bankowego na konto bankowe innego UKB zewnętrzego systemu bankowego.
0. UKB może włączyć lub wyłączyć opcję przewalutowanie przelewów ze swojego konta bankowego.
0. UKB może stworzyć cykliczne zlecenie przelewu ze swojego konta.
0. UKB może edytować istniejące cykliczne zlecenie przelewu ze swojego konta.
0. UKB może zamknąć cykliczne zlecenie przelewu ze swojego konta.
0. UKB może zakładać lokaty bankowe o określonym oprocentowaniu określonym w ofercie lokat banku.
0. UKB może zamknąć lokatę przed terminem jej zakończenia.
0. UKB może rozpocząć, prowadzić i zakończyć chat z chatbotem w celu uzyskania pomocy i/lub oferty banku.


## Wymagania niefunkcjonalne aplikacje klienckie
0. Podczas rejestracji trzeba podać: imię, nazwisko, PESEL, numer dokumentu tożsamości, adres do korespondencji, datę urodzenia.
0. Dostęp do konta UKB wymaga autoryzacji przez podanie danych dostępowych: loginu, hasła i kodu autoryzacji dwustopniowej (2FA).
0. Przelew/cykliczne zlecenie między UKB są możliwe tylko pod warunkiem posiadania wystarczających środków na koncie.
0. Przelew do banku, w którym waluta jest inna niż PLN jest możliwy wyłącznie, kiedy UKB ma włączoną opcję przewalutowania.
0. Warunkiem złożenia podania elektronicznego o zamknięcie konta jest nieposiadanie aktywnych lokat.
0. Zamknięcie przedterminowe wiąże się z utratą odsetek przez UKB.
0. Aplikacja kliencka UKB łączy się z bazą danych, przy użyciu nieuprzywilejowanego użytkownika, posiadającego minimalne przywileje potrzebne do poprawnego funkcjonowania.

## Wymagania niefunkcjonalne oficjalna aplikacja kliencka banku
0. Oficjalna aplikacja kliencka banku musi spełniać wymagania niefunkcjonalne zwykłych aplikacji klienckich.
0. Oficjalna aplikacja kliencka banku obsługuje po stronie użytkownika język polski m.in., generując komunikaty o błędach czy udostępniając interfejs użytkownika w tym języku.
0. Oficjalna aplikacja kliencka banku jest aplikacją przeglądarkową.
0. Oficjalna aplikacja kliencka banku jest oparta o technologię java.

## Wymagania niefunkcjonalne systemu chatbota
0. Chatbot posiada dostępność 24 godziny na dobę przez 7 dni w tygodniu.
0. System chatbota łączy się z systemem bazy danych, przy użyciu nieuprzywilejowanego użytkownika, posiadającego minimalne przywileje potrzebne do poprawnego funkcjonowania.
0. System chatbota jest niezależny od aplikacji klienckich.

## Wymagania funkcjinalne właściciela banku
0. Właściciel banku może zmodyfikować ofertę lokat banku.
0. Właściciel banku ma wgląd do wszystkich kont bankowych w banku.
0. Właściciel banku może zmodyfikować opłaty za wykonywanie poszczególnych tranzakcji bankowych.

## Wymagania niefunkcjonalne system bazy danych
0. System bazy danych zapisuje dane logujących się UKB
0. System bazy danych musi wykonywać codziennie kopie zapasowe różnicowe.
0. System bazy danych musi wykonywać co tydzień kopie zapasowe zupełne.
0. W razie awarii bazy danych, środki klientów które posiadają nie ulegają zniszczeniu.
0. W razie awarii jednej serwerowni, system bazy danych nadal może działać bez problemów.
0. System bazy danych nie może ulec uszkodzeniu przez błąd komunikacji z aplikacją klienta
0. System bazy danych nie może ulec uszkodzeniu przez złośliwie utworzone zapytanie z aplikacji klienta
0. System bazy danych nie może ulec uszkodzeniu przez złośliwie utworzone zapytanie z aplikacji klienta
0. Rozszerzenie systemu bazy danych, musi być możliwe bez całkowitego przemodelowania infrastruktury teleinformatycznej.
0. System bazy danych musi mieć możliwość osłużenia 1000 zapytań na sekundę.
0. System bazy danych musi mieć możliwość obsłużenia 500 jednoczesnych połączeń.
0. System bazy danych ma być oparty o serwer baz danych postresssql

## Wymagania niefunkcjonalne infrastruktury serwerowej
0. Wszystkie serwery należące do infrastruktury sieciowej banku działają na systemie operacyjnym RedHat Enterprise Linux w wersji 8.10.
0. Wszystkie serwery należące do infrastruktury sieciowej banku są połączone ze sobą przez sieć Internet.
