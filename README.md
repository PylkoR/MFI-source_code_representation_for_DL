# Reprezentacje kodu źródłowego dla Deep Learning

Projekt badawczy dotyczący metod reprezentacji kodu źródłowego (np. grafowe, tokenowe, AST) na potrzeby modeli głębokiego uczenia. Artykuł przygotowany w formacie konferencyjnym **IEEE**.

## Wymagania systemowe
Do poprawnej kompilacji lokalnej wymagane są:
* **Dystrybucja LaTeX:** MiKTeX (zalecane na Windows) lub TeX Live.
* **Silnik:** XeLaTeX (wymagany ze względu na obsługę fontów systemowych i polskich znaków).
* **Czcionki:** Pakiet `TeX Gyre Termes` (odpowiednik Times New Roman).

## Struktura projektu
* `MFI_paper.tex` - główny plik źródłowy artykułu.
* `IEEEtran.cls` - klasa dokumentu IEEE.
* `figures/` - katalog z grafikami i schematami.
* `.gitignore` - konfiguracja pomijania plików pomocniczych LaTeX.

## Kompilacja w VS Code
Projekt jest skonfigurowany pod rozszerzenie **LaTeX Workshop**. 
1. Otwórz plik `.tex`.
2. Użyj skrótu `Ctrl+,` lub wejdź w ustawienia vscode.
3. Wpisz latex recipes i wybierz "Edit in settings.json"
3. Tak wygląda działający json.
```json
{
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOC%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX (Simple)",
            "tools": [
                "xelatex"
            ]
        }
    ],
    "latex-workshop.latex.recipe.default": "XeLaTeX (Simple)",
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.latex.autoBuild.run": "onSave",
    "latex-workshop.latex.clean.enabled": true
}
```

## Rozwiązywanie problemów z czcionkami
Jeśli otrzymujesz błąd dotyczący braku czcionki `TeX Gyre Termes`:
1. Otwórz **MiKTeX Console**.
2. W zakładce **Packages** wyszukaj i zainstaluj `tex-gyre`.
3. W zakładce **Tasks** wybierz `Refresh font map files`.