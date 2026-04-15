# The `report-eirb` Package
<div align="center">Version 0.1.0</div>

An unofficial [Typst](https://typst.app/) template for [Enseirb-Matmeca](https://enseirb-matmeca.bordeaux-inp.fr/fr)

## Template adaptation checklist

- [ ] Adapt or deactivate the release workflow in `.github/workflows/release.yml`
  - to deactivate it, delete that file or remove/comment out lines 2-4 (`on:` and following)
  - to use the workflow
    - [ ] check the values under `env:`, particularly `REGISTRY_FORK`
    - [ ] if you don't have one, [create a fine-grained personal access token](https://github.com/settings/tokens?type=beta) with [only Contents permission](https://stackoverflow.com/a/75116350/371191) for the `REGISTRY_FORK`
    - [ ] on this repo, create a secret `REGISTRY_TOKEN` (at `https://github.com/[user]/[repo]/settings/secrets/actions`) that contains the so created token

    if configured correctly, whenever you create a tag `v...`, your package will be pushed onto a branch on the `REGISTRY_FORK`, from which you can then create a pull request against [typst/packages](https://github.com/typst/packages/)
- [ ] remove/replace the example test case
- [ ] (add your actual code, docs and tests)
- [ ] remove this section from the README

## Getting Started

1. **Font Instalalation (optional, but recommended)**
    - The template uses [Linux Libertine](https://www.dafont.com/linux-libertine.font) for the main text
    - The template also uses [JetBrains Mono](https://www.jetbrains.com/lp/mono/) for raw texts (e.g: code blocks)
    - There is a fallback system that will use "New Computer Modern", the default typst font

2. **Configure the template**
    - Edit the template parameters in `main.typ` to set your details:
    ```typ
    #show: template.with(
        sector: "Filière Informatique",
        document-type: "Rapport de Projet",

        title: "Implémentation d'un modèle de rapport académique",

        authors: (
            (name: "Alexandrine Mercier", email: "alexandrine.mercier@enseirb.fr"),
            (name: "Narcisse Fay", email: "narcisse.fay@enseirb.fr"),
            (name: "Johanne Reyer", email: "johanne.reyer@enseirb.fr"),
            (name: "Modestine Lapointe", email: "modestine.lapointe@enseirb.fr"),
        ),
        author-columns: 2,

        advisers: (
            (name: "Adelphe Félix", email: "adelphe.felix@enseirb.fr"),
        ),
        adviser-columns: 1,

        date: "Mai 2025",
        abstract: include "sections/0-abstract.typ",
    )
    ```

3. **Write your content**
    - The sections are split into files for organisation (see the `section` folder)
    - If you add sections, don't forget to add them in the `main.typ` file

4. **Compile your document**
    ```bash
    typst compile main.typ
    ```
    - Or watch for changes and recompile automatically:
    ```bash
    typst watch main.typ
    ```
    
## Getting Started with Typst

### Resources
- [Typst for LaTeX users](https://typst.app/docs/guides/guide-for-latex-users/)
- [Official Typst Documentation](https://typst.app/docs)
- [Typst Examples Book](https://sitandr.github.io/typst-examples-book/book/)

### Installation
> **Note:** There is also an online editor for Typst at [typst.app](https://typst.app/)

1. **Install Typst**
   - [Typst GitHub Repository](https://github.com/typst/typst?tab=readme-ov-file#installation)
   
2. **Editor Integration**
   - [TinyMist Extension](https://github.com/Myriad-Dreamin/tinymist?tab=readme-ov-file#installation) for VSCode, NeoVim, etc.

## Working with References

### Bibliography
- Add references to `bib.yaml`
- Reference in text using `@citation_key` or `#ref(<citation_key>)`
- Bibliography generated automatically at document end
- Supports articles, books, proceedings, web resources, and more

## Credits
This template is built on the foundation provided by [onyx-itu-unofficial](https://github.com/zagoli/simple-typst-thesis/) by FrederikBertelsen.
The original work has been expanded with modified and additional features, french language,
and Enseirb-Matmeca styling.
