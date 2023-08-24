---
Title: Manpage almost - Vanilla OS
Description: Manpage dla narzędzia almost.
PublicationDate: 2023-06-10
Authors: Contributors of Vanilla OS
---

# Manpage `almost`

Note: `almost` has been replaced with `abroot`.

## NAZWA

```
almost - narzędzie do niezmienności i warstwowości na żądanie, oparte na atrybucie (i)mmutable pliku i tmpfs.
```

## STRESZCZENIE

```
almost [OPCJE] [POLECENIA] [ARGUMENTY]
```

## OPIS

```
almost jest narzędziem, które zapewnia niezmienność na żądanie poprzez przełączanie niezmienności plików i katalogów w rootcie systemu. Zapewnia również sposób tworzenia warstw na wierzchu niezmiennych katalogów, pozwalając na testowanie zmian przed ich zatwierdzeniem.

Opcje:
	--help/-h		pokaż tą wiadomość
	--verbose/-v		wyjście z większą ilością informacji
	--version/-V		pokaż wersję

Polecenia:
	enter			ustaw system plików jako ro lub rw do czasu ponownego uruchomienia
	config			pokaż obecną konfigurację
	check			sprawdź czy system plików jest tylko do odczytu czy pozwala na odczyt i zapis 
	run			uruchamia polecenie w trybie odczyt-zapis i wraca do trybu odczytu po jego zakończeniu
```

## ENTER

```
Ustaw system plików jako tylko do oczytu lub odczyt-zapis do czasu ponownego uruchomienia

Ustawienie systemu pliku na tryb odczyt-zapis może stanowić ryzyko bezpieczeństwa. Zachowaj ostrożność przy korzystaniu z tego ustawnienia.

Użycie:
    enter [opcje] [polecenie]

Opcje:
	--help/-h		pokaż tą wiadomość
	--verbose/-v		wyjście z większą ilością informacji

Polecenia:
	ro			ustaw system plików jako tylko do odczytu
	rw			ustaw system plików jako odczyt-zapis
	default			ustaw system plików jako domyślny w pliku konfiguracyjnym

Przykłady:
	almost enter ro
	almost enter rw
```

## CONFIG

```
Zarządzaj i pokaż obecną konfigurację.

Użycie:
    config [opcje] [polecenie]

Opcje:
    --help/-h		pokaż tą wiadomość

Polecenia:
    set [key] [value]	ustaw wartość konfiguracji

Przykłady:
    almost config
    almost config set Almost::DefaultMode 1
```

## CHECK

```
Sprawdź czy system plików jest w trybie tylko do odczytu czy odczyt-zapis.

Użycie:
check [opcje] [polecenie]

Opcje:
	--help/-h		pokaż tą wiadomość

Przykłady:
	almost check
```

## RUN

```
Uruchom polecenie w trybie odczyt-zapis i wraca do trybu tylko do odczytu po jego zakończeniu.

Użycie:
    run [polecenie]

Opcje:
	--help/-h		pokaż tą wiadomość
	--verbose/-v		wyjście z większą ilością informacji

Przykłady:
    almost run ls
```

## ZOBACZ TAKŻE

- [`apx`](apx)

## DIAGNOSTYKA

```
almost zwraca 0 przy pomyślnym wykonaniu polecenia, 1 przy napotkaniu błędu.
```

## AUTOR

```
Współtwórcy Vanilla OS
```

## ZGŁASZANIE BŁĘDÓW

Prosimy zgłaszać błędy na [issue trackerze](https://github.com/Vanilla-OS/almost/issues).
