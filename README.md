# Introduction

[PlantUML](https://plantuml.com/) is a rendering tool for diagrams defined in a plain-text domain-specific language.

To get a quick start with it, check out the [public PlantUML service page](http://www.plantuml.com/plantuml/) where you can compose and render diagrams in your browser.

# Installation

## PlantUML

**Local installation is optional**. The easiest path to using PlantUML is with tooling that calls a remote rendering service. We'll need to decide if using the public service long-term is appropriate or if we need to stand up our own service internally - but for now we'll assume that using the public service is acceptable. The only catch with an external renderer is that you won't be able to generate diagrams if you're working offline.

### Local

PlantUML is written in Java and mostly self-contained except for a dependency on a command-line utility provided in [Graphviz](https://graphviz.org/), an open-source graphing tool.

* Install [Java Runtime](https://www.java.com/en/download/)
* Install [Graphviz](https://graphviz.org/download/)
* Add both to `PATH` 
* Configure tooling / plugins to point at the local installations, if required

### Docker

PlantUML provides a Docker container image equivalent to the [public PlantUML service](http://www.plantuml.com/plantuml/).
* Install [Docker](https://docs.docker.com/get-docker/)
* Install [plantuml-server](https://hub.docker.com/r/plantuml/plantuml-server) container

## Tooling

| Editor | Plugin Recommendation | Local Render | Service Render | |
| --- | --- | :-: | :-: | --- |
| [Rider](https://www.jetbrains.com/rider/) | [PlantUML integration](https://plugins.jetbrains.com/plugin/7017-plantuml-integration) | :heavy_check_mark: | :heavy_check_mark: |
| [Visual Studio](https://visualstudio.microsoft.com/) | [PlantUml Language Service](https://marketplace.visualstudio.com/items?itemName=KieranBorsden.PlantUmlLanguageService) | :x: | :heavy_check_mark: |
| [Visual Studio Code](https://code.visualstudio.com/) | [PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) | :heavy_check_mark: | :heavy_check_mark: |
| [Google Docs](https://docs.google.com/) | [PlantUML Gizmo](https://workspace.google.com/marketplace/app/plantuml_gizmo/950520042571) | :x: | :heavy_check_mark: |
| [Sublime Text](https://www.sublimetext.com/) | [PlantUMLDiagrams](https://packagecontrol.io/packages/PlantUmlDiagrams) | :heavy_check_mark: | :heavy_check_mark: |
| [Atom](https://atom.io/) | [PlantUML Toolkit](https://atom.io/packages/plantuml-toolkit) | :heavy_check_mark: | :x: | *Still looking for a plugin with service render*

# Publishing / Sharing Diagrams

## Image Files

The most obvious way to share a diagram is by sharing the PNG or SVG image file the renderer generates.

Interestingly, the renderer embeds the diagram source into the image files it generates, coupling the image and the source it renedered from.

## URLs

The easist way to share diagrams is via URLs pointing to a render service. These services are stateless, so URLs typically contain the diagram source in encoded form, e.g.:

```
http://www.plantuml.com/plantuml/png/SoWkIImgAStDuIe0qfd9cGM9UIKAXXOMfgW2bgRe0cWgZ0mCJRbqTUqWCkb5-QK52fvS88u2K1HY08XGWAj9pKk1gKCeX9W3910AKGn1rUO9DnBYP221Pe43a03w3W00
```

It's also possible for the URL to contain a URL to the diagram source instead - this is the "proxy" feature:

```
http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/alan-playstudios/plantuml-experiments/master/example.puml
```

## Github

You can use "proxy" render URLs as image sources in Github Markdown files such as this one, producing a diagram image that updates when the underlying source file updates. You can see this in action here:

```
![Example](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/alan-playstudios/plantuml-experiments/master/example.puml)
```

>![Example](http://www.plantuml.com/plantuml/proxy?src=https://raw.githubusercontent.com/alan-playstudios/plantuml-experiments/master/example.puml)

More examples are on the [Example diagrams](docs/example-diagrams.md) page.

Unfortunately, this currently only works for public repositories - with a private repository, the render service doesn't have appropriate permissions to access any repository URLs. There are alternate solutions for private repositories - we can follow up on those if we find this functionality desirable.

## Google Docs

You can use [PlantUML Gizmo](https://workspace.google.com/marketplace/app/plantuml_gizmo/950520042571) in Google Docs to embed a diagram and its source into a document. Any user collaborating on the document can edit the diagram source, but users can't simultaneously edit the diagram source.

This is a convenient option, tightly coupling the diagram source, the generated image, and the document in which it's embedded - the downside is that you can't effectively put it under source control.

# Examples

[Example diagrams](docs/example-diagrams.md)

# Other Resources

## PlantUML

* [plantuml.com](https://plantuml.com/) - PlantUML official site
* [Ashley's PlantUML Documentation](https://plantuml-documentation.readthedocs.io/en/latest/index.html) - Unofficial documentation
* [real-world-plantuml.com](https://real-world-plantuml.com/) - A gallery of PlantUML diagrams accessible in public Github repositories

## UML

* [uml.org](https://www.uml.org/) - UML reference - Object Management Group's official site
* [uml-diagrams.org](https://www.uml-diagrams.org/) - UML reference - much more accessible than the standards doc
