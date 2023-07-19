# Markdown Languages and Their Build Tools

## Myst and Sphinx

MyST (Markedly Structured Text is a superset of Commonmark. As the MyST Spec explains: 

> MyST is a superset of CommonMark (a standard form of Markdown) and allows you to directly create “directives” and “roles” as extension points
in the language. These extensions points are influenced by ReStructured Text (RST) and Sphinx -- pulling on the nomenclature and introducing additional
standards where appropriate. directives are block-level extension points, like callout panels, tabs, figures or embedded charts; and roles are inline extension points, for components like references, citations, or inline math.

The [mystmd.org](https://mystmd.org/guide/quickstart-myst-markdown) website explains the MyST markdown syntax. MyST can be [used with Sphinx]((https://www.sphinx-doc.org/en/master/usage/markdown.html)
to allow you to write in MyST markdown rather than restructuredtext. Like Sphinx, MyST has its own [Myst Website Build System](https://mystmd.org/guide/quickstart-myst-websites)

MyST has a `list-table` whose syntax takes some getting used to. Here is an example of it that shows how to  specify column widths
in relative terms using integers. The 2nd column is twice the width of the first

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

You can also use percentages like this:

```
    ```{list-table} Example 4 of LZS device product code
    :header-rows: 1
    :name: example-4
    :align: left
    :width: 100%
    :widths: 35 65
    
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

Antora is a build tool for [Asciidoctor Markdown](https://docs.asciidoctor.org/asciidoc/latest/asciidoc-vs-markdown/).
Antora is designed to work with one or more github repositories where the site content resides.

Asciidoctor allows a lot of flexibility when creating tables, and it seems to have just as extensive feature set
as Sphinx (using RestructuredText or MyST Markdown) or the MyST standalone website build tool.
    
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
 
