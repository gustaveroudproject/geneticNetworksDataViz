# Data visualization of genetic networks

Data visualization of genetic networks for the project "Gustave Roud, *Œuvres complètes*" (Université de Lausanne) in collaboration with Density Design Lab (Politecnico di Milano).

## Documentation
- "Gustave Roud, *Œuvres complètes*": [project page](https://www.unil.ch/clsr/home/menuinst/projets-de-recherche/gustave-roud-oeuvres-completes.html). The project includes the development of a web application to access the texts and the archive of Gustave Roud. The visualizations of the genetic networks will be included in the web application.
- Christen, A., & Spadini, E. (2019). "Modeling genetic networks. Gustave Roud’s œuvre, from diary to poetry collections". *Umanistica Digitale*, 3(7). https://doi.org/10.6092/issn.2532-8816/9063. This article presents the data model used in the project to organize the genetic relationships between the manuscripts and the publications. Some aspects of the data model have evolved since the publication of the article (e.g., we do not take into account anymore the order of the *avant-textes* inside a genetic dossier), but the main concepts remain the same.
- Web application development: https://github.com/gustaveroudproject/roud-oeuvres-app. Documentation: https://github.com/gustaveroudproject/roud-oeuvres-app/blob/master/DOCUMENTATION.md.
- ARKs are persistent identifier in the form of URL pointing to our edition or to a generic interface.
- Slides of a presentation about the collections (*recueils*) in the work of Gustave Roud: https://gustaveroudproject.github.io/talks/20180524_cuso_recueil.html#/ (hover to see details in some of the slides).


## Model

#### Classes and properties
The modelling of the genetic networks of Gustave Roud's works are complexe, especially because each document or publication might be composed of multiple parts or sections.

A simplified model of the genetic networks, without taking into accounts parts, is available in a [human-readable rendering](http://150.146.207.114/lode/extract?url=https%3A%2F%2Fraw.githubusercontent.com%2Fgustaveroudproject%2FgeneticNetworksDataViz%2Fmaster%2Fdoc%2FRoudGeneticsSpecificationWithoutParts.ttl&owlapi=true&lang=en) or a [Turtle file](doc/RoudGeneticsSpecificationWithoutParts.ttl). This is the suggested starting point to read the model.

The complete model, including parts, is available in a [human-readable rendering](http://150.146.207.114/lode/extract?url=https%3A%2F%2Fraw.githubusercontent.com%2Fgustaveroudproject%2FgeneticNetworksDataViz%2Fmaster%2Fdoc%2FRoudGeneticsSpecificationComplete.ttl&owlapi=true&lang=en) or a [Turtle file](doc/RoudGeneticsSpecificationComplete.ttl).

#### Visual rendering
- [Summary](doc/RoudGenetics.png) of all possible genetic relationships
- Visual [rendering](http://visualdataweb.de/webvowl/#opts=cd=240;filter_disjoint=false;mode_compact=true;mode_colorExt=false;#iri=https://raw.githubusercontent.com/gustaveroudproject/geneticNetworksDataViz/master/doc/RoudGeneticsSpecificationWithoutParts.ttl) of the simplified specification, without parts (through WebVOWL; for a better visualisation, scroll for 'Max label width' in the 'Options' menu). This link is also given in the specification itself.
- Visual [rendering](http://visualdataweb.de/webvowl/#opts=cd=240;filter_disjoint=false;mode_compact=true;mode_colorExt=false;#iri=https://raw.githubusercontent.com/gustaveroudproject/geneticNetworksDataViz/master/doc/RoudGeneticsSpecificationComplete.ttl) of the complete specification (through WebVOWL; for a better visualisation, scroll for 'Max label width' in the 'Options' menu). This link is also given in the specification itself.


#### Some info
The project [ontology](https://github.com/LaDHUL/oeuvres-roud) is build on top of the `knora-base` ontology, that is a general purpose schema for data in the humanities and social sciences, compliant with the framework [Knora](https://dsp.dasch.swiss/). Our ontology aims to model archival objects, bibliographical records, persons, places, events and other information related to Roud's works. Here we removed the `knora-base` layer and list only the **classes** (nodes) and **properties** (edges) of the ontology that are relevant for the modelling of the **genetic relationships**. For instance, properties for **titles** and **dates** are not listed in the specification, but present in the data.

In our work, we created a generic model for genetic data, [GENO](https://gen-o.github.io/). Our implementation in the project uses most of GENO's classes and properties, but not all of them; and adds classes and properties that do not exist in GENO, namely decomposing publications, manuscripts and dossiers in parts. 

Technical note: classes and properties can be understood as nodes and edges. The domain of a property indicates the category of the starting point of an edge and the range indicates the category of its ending point. The properties are predicates in a triple of subject-predicate-object. Both classes and properties can have sub-classes (which inherit the properties) and sub-properties (which share the object of the property). The value of an object-type property is a node in the graph, while the value of a data-type property is a string, or literal. One can use both the human-readable label of a class or property (e.g. part of a manuscript), and its IRI (the last part of the IRI, e.g. `MsPart`) to identify it. Unfortunately, in this specification there are a lot of inconsistencies in the naming of classes and properties. 


## About the visualization
What to show, make evident or consider in the visualisation for each node:
* type
* if type is :Publication and subtype :Book => title and date
* if type is :Publication and subtype :PeriodicalArticle => title, date and periodical
* if type is :Publication => if it has photo or not (default is not)
* if type is :Manuscript => title, archive, shelfmark (id of the manuscript), editorial set (for Diary only), genetic stage (not for diary), date
* if type is :MsPart or :PubPart => title and number indicating the order of the parts
* if type is :GeneticDossier or :GeneticDossierPart, no need to visualize properties


## Data

Data for each work by Gustave Roud can be found in the folder [`data`](data). The works are:
* *Adieu*, Au Verseau, 1927
* *Feuillets*, Mermod, 1929
* *Petit traité de la marche en plaine suivi de Lettres, dialogues et morceaux*, Mermod, 1932
* *Essai pour un paradis*, Mermod, 1933
* *Pour un moissonneur*, Mermod, 1941
* *Air de la solitude*, Mermod, 1945
* *Haut-Jora*t, Éditions des Terreaux, 1949
* *Le Repos du cavalier*, Bibliothèque des Arts, 1958
* *Requiem*, Payot, 1967
* *Campagne perdue*, Bibliothèque des Arts, 1972





