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
> `todo:` more detail?

### Docker

PlantUML provides a Docker container image equivalent to the [public PlantUML service](http://www.plantuml.com/plantuml/).
* Install [Docker](https://docs.docker.com/get-docker/)
* Install [plantuml-server](https://hub.docker.com/r/plantuml/plantuml-server) container
> `todo:` more detail?

## Tooling

| Editor | Plugin Recommendation | Local Render | Service Render | |
| --- | --- | :-: | :-: | --- |
| [Rider](https://www.jetbrains.com/rider/) | [PlantUML integration](https://plugins.jetbrains.com/plugin/7017-plantuml-integration) | :heavy_check_mark: | :heavy_check_mark: |
| [Visual Studio](https://visualstudio.microsoft.com/) | [PlantUml Language Service](https://marketplace.visualstudio.com/items?itemName=KieranBorsden.PlantUmlLanguageService) | :x: | :heavy_check_mark: |
| [Visual Studio Code](https://code.visualstudio.com/) | [PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) | :heavy_check_mark: | :heavy_check_mark: |
| [Sublime Text](https://www.sublimetext.com/) | [PlantUMLDiagrams](https://packagecontrol.io/packages/PlantUmlDiagrams) | :question: | :question: |
| [Atom](https://atom.io/) | [PlantUML Toolkit](https://atom.io/packages/plantuml-toolkit) | :heavy_check_mark: | :x: | *Still looking for a plugin with service render*

# Other Integrations

## Github

It's possible to embed live-updating diagrams in public Github repositories such as this one. You can see this in action on the [Example diagrams](docs/example-diagrams.md) page.

> `todo:` maybe add detail on potential Github integration - but private repositories may be a nonstarter

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
