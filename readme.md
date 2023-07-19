# Markdown Languages and Their Build Tools

## Myst and Sphinx

MyST (Markedly Structured Text is a superset of Commonmark. As the MyST Spec explains: 

> MyST is a superset of CommonMark (a standard form of Markdown) and allows you to directly create “directives” and “roles” as extension points
in the language. These extensions points are influenced by ReStructured Text (RST) and Sphinx -- pulling on the nomenclature and introducing additional
standards where appropriate. directives are block-level extension points, like callout panels, tabs, figures or embedded charts; and roles are inline extension points, for components like references, citations, or inline math.

[mystmd.org](https://mystmd.org/guide/quickstart-myst-markdown) is its website.

MyST has its own [Myst Website Build System](https://mystmd.org/guide/quickstart-myst-websites)
- [Sphinx wiht Myst](https://www.sphinx-doc.org/en/master/usage/markdown.html)

`{list-table}` was the hardest to understand at first. Here is an example that works that shows column widths specified in relative terms
using integers. The 2nd column is twice the width of the first

```
    ```{list-table} Example 4 of LZS device product code
    :header-rows: 1
    :name: example-4
    :align: left
    :widths: 1 2
    
    * - Field
      - Value
    * - `device.brand_name`
      - "VISX STAR S4 IR EXCIMER LASER"
    * - `device.generic_name`
      - "EXCIMER LASER"
    * - `device.openfda.device_name`
      - "Excimer Laser System"
    * - `device.openfda.device_class`
      - 3
    ```
```

## Antora
    
### Installation of Antora Locally

See [Install and Run Antora Quickstart](https://docs.antora.org/antora/latest/install-and-run-quickstart/)

Install nodejs using apt package manager. Then install nvm per: <https://github.com/nvm-sh/nvm#installation-and-update>

Next install antora in your antora project directory:

```bash
cd myantora
node -e "fs.writeFileSync('package.json', '{}')"
npm i -D -E @antora/cli@3.1
```

- Intros
  - [Intro with Gitlab Antora Demo repos](https://www.magnolia-cms.com/blog/using-asciidoc-and-antora-to-create-online-technical-documentation.html)
  - [The three key concepts you need to know](https://matthewsetter.com/antora/three-core-concepts/)
  - Video: [Documentation for Users with AsciiDoc and Antora](https://www.youtube.com/watch?v=LT0a--DNJhI)
    - [slides](https://speakerdeck.com/ahus1/antora-3-release-celebration) click the download icon at bottom
- Official documetation on [How to Organize Your Content Files](https://docs.antora.org/antora/latest/organize-content-files/)
- [Antora 3 Demo Repo](https://github.com/ahus1/antora3demo/tree/main)
 
