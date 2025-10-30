# Poradnik: Jak zamieszczać pliki na GitHub

Ten poradnik krok po kroku wyjaśnia, jak pracować z GitHubem – od tworzenia własnego repozytorium i dodawania plików, po współpracę z cudzymi repozytoriami. Zakładam, że masz konto na GitHubie (jeśli nie, załóż je na github.com). Do zaawansowanych operacji potrzebujesz zainstalowanego Git (pobierz z git-scm.com).

## 1. Tworzenie własnego repozytorium i dodawanie plików

### Krok 1: Utwórz nowe repozytorium

- Zaloguj się na GitHub.
- Kliknij "+" w prawym górnym rogu i wybierz "New repository".
- Nadaj nazwę repozytorium, dodaj opis (opcjonalnie), wybierz widoczność (public/private).
- Opcjonalnie: Dodaj README, .gitignore lub licencję.
- Kliknij "Create repository".

### Krok 2: Dodaj pliki przez interfejs webowy (proste, bez Git)

- W repozytorium kliknij "Add file" > "Upload files".
- Przeciągnij pliki lub wybierz je z komputera.
- Dodaj commit message (np. "Dodano pierwsze pliki").
- Kliknij "Commit changes".

### Krok 3: Dodaj pliki za pomocą Git (CLI, dla lokalnych projektów)

- Zainstaluj Git.
- Sklonuj repozytorium: git clone https://github.com/twoj-user/nazwa-repo.git.
- Przejdź do folderu: cd nazwa-repo.
- Dodaj pliki (np. skopiuj je do folderu).
- git add . (dodaj wszystkie zmiany).
- git commit -m "Dodano pliki".
- git push origin main (lub master).

Jeśli masz istniejący lokalny projekt:

- git init w folderze projektu.
- git remote add origin https://github.com/twoj-user/nazwa-repo.git.
- Dodaj, commit, push jak wyżej.

**Uwaga:** Dla dużych plików (>100MB) użyj Git LFS: git lfs track "*.rozszerzenie", potem add/commit/push.

## 2. Dodawanie plików do cudzego repozytorium (Ty wstawiasz coś do repo kogoś innego)

Jeśli nie masz uprawnień do bezpośredniego pusha, użyj forka i pull request (PR) – to standardowy sposób współpracy.

### Krok 1: Fork repozytorium

- Przejdź do repozytorium kogoś innego.
- Kliknij "Fork" w prawym górnym rogu – stworzy to kopię w Twoim koncie.

### Krok 2: Sklonuj forka lokalnie

- git clone https://github.com/twoj-user/nazwa-forka.git.
- Przejdź do folderu: cd nazwa-forka.

### Krok 3: Dodaj zmiany

- Dodaj/modyfikuj pliki.
- git add ..
- git commit -m "Dodano nowe pliki lub zmiany".

### Krok 4: Push do forka

- git push origin main (lub Twoja branch, np. git checkout -b nowa-branch; git push origin nowa-branch).

### Krok 5: Utwórz Pull Request

- Wróć na GitHub do Twojego forka.
- Kliknij "Compare & pull request" (lub "Pull requests" > "New pull request").
- Wybierz base repo (oryginalne) i Twoją branch.
- Dodaj tytuł, opis (wyjaśnij zmiany).
- Kliknij "Create pull request". Właściciel repo otrzyma powiadomienie.

Jeśli masz uprawnienia (np. zaproszony collaborator):

- Właściciel repo zaprasza Cię: W repo > Settings > Collaborators > Add people.
- Potem możesz clone, add, commit, push bezpośrednio do ich repo (bez forka).

## 3. Akceptowanie zmian w własnym repozytorium (Ktoś wstawia coś do Twojego repo)

Ktoś może dodać do Twojego repo przez PR (jeśli forknął i wysłał PR).

### Krok 1: Przejrzyj PR

- W Twoim repo kliknij "Pull requests".
- Wybierz PR, przeczytaj zmiany (diff), komentarze.
- Opcjonalnie: Skomentuj, poproś o zmiany.

### Krok 2: Zaakceptuj i merge

- Jeśli OK: Kliknij "Merge pull request" (wybierz metodę: merge commit, squash, rebase).
- Dodaj commit message.
- Kliknij "Confirm merge".
- Opcjonalnie: Usuń branch po merge.

Jeśli wymagasz review: W Settings > Branches > Add rule > Require pull request reviews.

**Dodatkowe wskazówki:**

- Używaj branchy do zmian: git checkout -b feature/nowa-cecha.
- Aktualizuj forka: git remote add upstream https://github.com/oryginalny-user/repo.git; git fetch upstream; git merge upstream/main.
- Problemy? Sprawdź GitHub Help lub fora.

Ten poradnik oparty na oficjalnej dokumentacji GitHub (stan na 2025). Jeśli coś się zmieni, sprawdź docs.github.com.