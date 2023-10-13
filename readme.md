# Markdown Languages and Their Build Tools

## MyST

MyST (Markedly Structured Text is a superset of Commonmark. As the MyST Spec explains: 

> MyST is a superset of CommonMark (a standard form of Markdown) and allows you to directly create “directives” and “roles” as extension points
in the language. These extensions points are influenced by ReStructured Text (RST) and Sphinx -- pulling on the nomenclature and introducing additional
standards where appropriate. directives are block-level extension points, like callout panels, tabs, figures or embedded charts; and roles are inline extension points, for components like references, citations, or inline math.

The [mystmd.org](https://mystmd.org/guide/quickstart-myst-markdown) website has Quickstart tutorails and an Authoring guide that explains the MyST markdown syntax.
The MyST is written in javascript. MyST also has its own [Website Build System](https://mystmd.org/guide/quickstart-myst-websites).

MyST can also be with [Sphinx](https://www.sphinx-doc.org/en/master/) as an alternative to RestructuredText. See [MyST Markdown for Sphinx](https://www.sphinx-doc.org/en/master/usage/markdown.html)
Sphinx is written in Python, and the MyST parser for Sphinx is also in Python. 

To export webpages to PDF, you need to install textlive-full:

```bash
sudo apt install -y texlive-full
```

### Tables in MyST Markdown

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

## Sphinx

Like MyST [Sphinx](https://www.sphinx-doc.org/en/master/) is a webiste build system for documentation written in RestructuredText. You may also use MyST markdown
now instead of RestructuredText. Sphin has several themes for different layouts and appearance.


I found that it was easier to first create an Python virtual enviroment and install all Python packages, such as MyST, in the
virtual environment. Fist install these pacages:

```bash
$ sudo apt install -y python3-pip
$ sudo apt install -y python3-venv
```

Then do:

```bash
python3 -m venv python-venv
```

Now you can use the virtual enviroment, say, in a Sphinx project by activating the virtual enviroment each time. You install any
python3 packages like `myst` in the virtual enviroment.

```bash
source ~/python-venv/bin/activate
```

This bash script builds run Sphinx `make` in the virtual enviromnet:

```bash
source ~/python-venv/bin/activate
make clean && make html
deactivate
```
## Executable Books

[Executable Books](https://github.com/executablebooks)  is an international collaboration to build open source tools that facilitate publishing computational narratives using the Jupyter ecosystem.

You can use [MyST Markdown in JupyterLab](https://executablebooks.org/en/latest/blog/author/rowan-cockett/)).

## Antora and Asciidoctor

[Antora](https://antora.org) is a sophisticated static site generator for [Asciidoctor Markdown](https://docs.asciidoctor.org/asciidoc/latest/asciidoc-vs-markdown/).
Unlink Sphinx or most other static site generators, an Antora project does not contain your Asciidoc markdown. Instead it pulls the markdown from
remote git repos. They maybe be several such repos, as in the Fedora documentation.

Github and Gitlab support sites built from Asciidoc pages. Gitlab supports hosting sites built with Antora. See [Publish to Gitlab pages](https://docs.antora.org/antora/latest/publish-to-gitlab-pages/).

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

To install the lunr extension for Antora:

```bash
npm i @antora/lunr-extension
```

- Intros
  - [Using Antora to Publish Your Site](https://fedoramagazine.org/using-antora-for-your-open-source-documentation/) is clear, short and straight forward.
- Others
  - [Intro with Gitlab Antora Demo repos](https://www.magnolia-cms.com/blog/using-asciidoc-and-antora-to-create-online-technical-documentation.html)
  - [The three key concepts you need to know](https://matthewsetter.com/antora/three-core-concepts/)
  - Video: [Documentation for Users with AsciiDoc and Antora](https://www.youtube.com/watch?v=LT0a--DNJhI)
    - [slides](https://speakerdeck.com/ahus1/antora-3-release-celebration) click the download icon at bottom
- Official documetation on [How to Organize Your Content Files](https://docs.antora.org/antora/latest/organize-content-files/)
- [Antora 3 Demo Repo](https://github.com/ahus1/antora3demo/tree/main)
 
