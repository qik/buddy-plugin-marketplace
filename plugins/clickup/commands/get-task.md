---
description: "Pobierz dane zadania z ClickUp"
---

# Get ClickUp Task

Pobierz dane zadania z ClickUp.

## Instrukcje

1. Określ task ID:
   - Jeśli użytkownik podał argument `$ARGUMENTS`, użyj go jako task ID
   - Jeśli argument jest pusty, wyciągnij task ID z nazwy aktualnego brancha git (ostatnia część po ostatnim myślniku)

2. Pobierz dane zadania używając MCP tool `mcp__plugin_clickup-mcp_clickup__get_task`

3. Wyświetl użytkownikowi:
   - Tytuł zadania
   - Opis zadania (jeśli istnieje)

## Przykład ekstrakcji task ID z brancha

Branch: `dev-routing-rest-api-869bpr9ue` → Task ID: `869bpr9ue`
Branch: `feature-new-endpoint-abc123def` → Task ID: `abc123def`

## Wykonanie

Argument od użytkownika: $ARGUMENTS

Jeśli `$ARGUMENTS` jest puste, pobierz aktualny branch komendą `git branch --show-current` i wyciągnij ostatnią część (po ostatnim `-`).
