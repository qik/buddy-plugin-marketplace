---
description: "Zweryfikuj implementację względem wymagań z ClickUp"
---

# Validate Implementation

Porównaj zmiany w branchu z wymaganiami zadania z ClickUp i zrób review implementacji.

## Instrukcje

1. **Określ task ID:**
   - Jeśli użytkownik podał argument `$ARGUMENTS`, użyj go jako task ID
   - Jeśli argument jest pusty, wyciągnij task ID z nazwy aktualnego brancha git (ostatnia część po ostatnim myślniku)

2. **Pobierz dane zadania** używając MCP tool `mcp__plugin_clickup_clickup__get_task`

3. **Pobierz zmiany z brancha:**
   - Pobierz domyślny branch repozytorium: `git symbolic-ref refs/remotes/origin/HEAD | sed 's@^refs/remotes/origin/@@'`
   - Wykonaj `git diff <default-branch>...HEAD` aby zobaczyć wszystkie zmiany w tym branchu
   - Wykonaj `git log <default-branch>..HEAD --oneline` aby zobaczyć listę commitów

4. **Przeanalizuj wymagania:**
   - Przeczytaj dokładnie opis zadania z ClickUp
   - Wyodrębnij wszystkie wymagania/punkty do zrobienia z opisu
   - Zidentyfikuj acceptance criteria jeśli są podane

5. **Zrób review zmian:**
   - Porównaj każde wymaganie z wykonanymi zmianami
   - Sprawdź czy kod spełnia dane wymaganie

6. **Wygeneruj raport:**

   ```
   ## Zadanie: [Tytuł zadania]

   ### Wymagania z opisu zadania:
   [Lista wymagań wyodrębnionych z opisu]

   ### Status implementacji:

   | Wymaganie | Status | Uwagi |
   |-----------|--------|-------|
   | [wymaganie 1] | ✅ Zrobione / ⏳ Częściowo / ❌ Brak | [szczegóły] |
   | [wymaganie 2] | ... | ... |

   ### Podsumowanie:
   - Zrobione: X/Y wymagań
   - Do zrobienia: [lista brakujących rzeczy]

   ### Dodatkowe uwagi:
   [Ewentualne sugestie, problemy, rzeczy do poprawy]
   ```

## Przykład ekstrakcji task ID z brancha

Branch: `dev-routing-rest-api-869bpr9ue` → Task ID: `869bpr9ue`
Branch: `feature-new-endpoint-abc123def` → Task ID: `abc123def`

## Wykonanie

Argument od użytkownika: $ARGUMENTS

Jeśli `$ARGUMENTS` jest puste, pobierz aktualny branch komendą `git branch --show-current` i wyciągnij ostatnią część (po ostatnim `-`).
