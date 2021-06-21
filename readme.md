# Data visualization of genetic networks

Data visualization of genetic networks for the project "Gustave Roud, *Œuvres complètes*" (Université de Lausanne) in collaboration with Density Design Lab (Politecnico di Milano).

## Documentation
- "Gustave Roud, *Œuvres complètes*": [project page](https://www.unil.ch/clsr/home/menuinst/projets-de-recherche/gustave-roud-oeuvres-completes.html). The project includes the development of a web application to access the texts and the archive of Gustave Roud. The visualizations of the genetic networks will be included in the web application.
- Christen, A., & Spadini, E. (2019). "Modeling genetic networks. Gustave Roud’s œuvre, from diary to poetry collections". *Umanistica Digitale*, 3(7). https://doi.org/10.6092/issn.2532-8816/9063. This article presents the data model used in the project to organize the genetic relationships between the manuscripts and the publications. Some aspects of the data model have evolved since the publication of the article (e.g., we do not take into account anymore the order of the *avant-textes* inside a genetic dossier), but the main concepts remain the same.
- Web application development: https://github.com/gustaveroudproject/roud-oeuvres-app. Documentation: https://github.com/gustaveroudproject/roud-oeuvres-app/blob/master/DOCUMENTATION.md.
- ARKs are persistent identifier in the form of URL pointing to our edition or to a generic interface.

## Model

#### Some info
The project [ontology](https://github.com/LaDHUL/oeuvres-roud) is build on top of the `knora-base` ontology, that is a general purpose schema for data in the humanities and social sciences, compliant with the framework [Knora](https://dsp.dasch.swiss/). Our ontology aims to model archival objects, bibliographical records, persons, places, events and other information related to Roud's works. Here we'll list only the **classes** (nodes) and **properties** (edges) of the ontology that are relevant for the modelling of the **genetic relationships**.

In our work, we created a generic model for genetic data, [GENO](https://gen-o.github.io/). Our implementation in the project uses most of GENO's classes and properties, but not all of them; and adds classes and properties that do not exist in GENO, namely decomposing publications, manuscripts and dossiers in parts. 

Technical note: classes and properties can be understood as nodes and edges. The domain of a property indicates the category of the starting point of an edge, while the range indicates the category of its ending point. Both classes and properties can have sub-classes and sub-properties. One can use both the human-readable label of a class or property (e.g. part of a manuscript), and its IRI (the last part of the IRI, e.g. `MsPart`) to identify it.

#### Classes and properties
See the [human-readable rendering](http://150.146.207.114/lode/extract?url=https%3A%2F%2Fraw.githubusercontent.com%2Fgustaveroudproject%2FgeneticNetworksDataViz%2Fmaster%2Fdoc%2FRoudGeneticsSpecification.ttl&owlapi=true&lang=en) of the [specification](doc/RoudGeneticsSpecification.ttl) for a detailed description of classes and properties.

##### Summary
- Here it is a [summary](doc/RoudGenetics.png) of all possible genetic relationships.



## About the visualization
* For each **node**, show the resource type.
* If the resource has type :**Publication** and subtype :Book, show title and date.
* If the resource has type :Publication and subtype :PeriodicalArticle, show title, date and periodical.
* If the resource has type :Publication, show if it has photo or not (default is not).
* If the resource has type :**Manuscript**, show title, archive, shelfmark, editorial set (for Diary only), genetic stage (not for diary), date (***TO BE ADDED***).


## Sample data

#### "Deux moments d'une quête", *Suisse contemporaine*, 1941
- **IRI**: <http://rdfh.ch/0112/OXLofRkPRCKOcLrEy6DZ8w>
- **Genetic dossier IRI**: <http://rdfh.ch/0112/gtxOIRZySkGGkvXWg0nkEQ>
- **ARK**: <http://ark.dasch.swiss/ark:/72163/1/0112/OXLofRkPRCKOcLrEy6DZ8wf.20180831T1412546Z>
- **Description**. This publication reuses the article "Dédicace", published in the journal *Schweizer Annalen* in 1935 (property `roud-oeuvres:publicationIsReusedInDossier`). For the article "Dédicace", there are two *avant-textes* (`roud-oeuvres:msIsAvantTextInGeneticDossier`) and one diary entry reused in it (`roud-oeuvres:msIsReusedInDossier`).
- **Data** are available in various formats (RDF-XML, TTL, JSON-LD) in the folder [`sample`](sample/DeuxMoments_SuisseContemporaine_1941).


#### *Adieu*, 1927
- **IRI**: <http://rdfh.ch/0112/K2OVZydJS42GUsMJvKhP-A>
- **Genetic dossier IRI**: <http://rdfh.ch/0112/XqZUUgzjQXaX8rEnfyifJg>
- **ARK**: <http://ark.dasch.swiss/ark:/72163/1/0112/K2OVZydJS42GUsMJvKhP=AE.20180919T155223417Z>
- **Description**. This book is composed of two parts (`:PubPart` and `:GeneticDossierPart`). The first has two *avant-textes* (`:msIsAvantTextInGeneticDossierPart`), the second has one *avant-texte* and four diary entries reused in it (`:msIsReusedInDossierPart`). The book has been re-edited in 1944 with the publisher Éditions des Portes de France (`:publicationIsRepublishedDossier`) and in the volume *Écrits* in 1950. The first part alone has been reused in *Annonce d'un adieu* published in the journal « Présence » in 1932 (`:pubPartIsReusedInDossier`).
- **Data** are available in JSON-LD in the folder [`sample`](sample/Adieu_1944).






