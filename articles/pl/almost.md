---
Title: Niezmienność (almost) - Vanilla OS
Description: Dowiedz się, jak korzystać z Almost, narzędzia do niezmienności na żądanie.
PublicationDate: 2023-06-10
Authors: 
  - Contributors of Vanilla OS
---

`almost` jest narzędziem, które zapewnia niezmienność na żądanie poprzez przełączanie
niezmienności plików i katalogów w rootcie systemu. Zapewnia również sposób tworzenia
warstw na wierzchu niezmiennych katalogów, pozwalając na testowanie zmian przed ich
zatwierdzeniem.

Note: `almost` has been replaced with `abroot`.

## Jak to działa

Niezmienność w `almost` jest uzyskiwana przez ustawienie flagi `i` na wszystkich plikach
i katalogach w rootcie systemu, z wyjątkiem tych, które są używane do przechowywania
plików konfiguracyjnych oprogramowania i katalogu domowego użytkownika (`/home, /etc,
/var`).

To samo można osiągnąć używając komendy `chattr`, ale `almost` zapewnia spójność poprzez
przywrócenie domyślnego stanu systemu po ponownym uruchomieniu, oraz z dodatkowymi
funkcjami do lepszego zarządzania niezmiennością, np. uruchomienie komendy przy
tymczasowym wyłączeniu niezmienności.

### Niezmienność na życzenie

Nazywa się to niezmiennością *na życzenie*, ponieważ można ją włączyć lub wyłączyć w
dowolnym momencie. Niezmienność ma być używana jako środek bezpieczeństwa, aby zapobiec
przypadkowym zmianom w systemie, więc powinna być utrzymywana włączona przez większość
czasu.

Ze względu na swoją naturę, `almost` jest gotowy do użycia i działa na wszystkich
systemach plików i konfiguracjach.

### Nazwa

Nazwa `almost` pochodzi z faktu, że nie jest to pełnoprawna implementacja niezmienności,
ale raczej narzędzie, które pomaga je osiągnąć, a jednocześnie pozwala na wprowadzanie
zmian w razie potrzeby.

## Czym to nie jest

`almost` nie ma wsparcia dla snapshotów. Każda zmiana dokonana w systemie jest trwała
i nie można jej cofnąć bez przywrócenia z kopii zapasowej lub downgrade'u systemu. Aby
tego uniknąć, powinieneś zawsze testować swoje zmiany używając warstw przed ich
zatwierdzeniem. Jedynym powodem wyłączenia niezmienności byłaby edycja pliku
konfiguracyjnego, który nie znajduje się we wspólnych katalogach, lub instalacja
sterowników. Wyłączenie niezmienności w celu zainstalowania aplikacji lub biblioteki
nie jest zalecane. Zamiast tego użyj [`apx`](/docs/apx), [`Flatpak`](/docs/flatpak),
[`Snap`](/docs/snap) lub [`AppImage`](/docs/appimage).

## Użytek

- [Manpage](almost-manpage)
