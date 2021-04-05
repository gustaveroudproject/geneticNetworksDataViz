# Data visualization of genetic networks

Data visualization of genetic networks for the project "Gustave Roud, *Œuvres complètes*" (Université de Lausanne) in collaboration with Density Design Lab (Politecnico di Milano).

## Documentation
- "Gustave Roud, *Œuvres complètes*": [project page](https://www.unil.ch/clsr/home/menuinst/projets-de-recherche/gustave-roud-oeuvres-completes.html). The project includes the development of a web application to access the texts and the archive of Gustave Roud. The visualizations of the genetic networks will be included in the web application.
- Christen, A., & Spadini, E. (2019). "Modeling genetic networks. Gustave Roud’s œuvre, from diary to poetry collections". *Umanistica Digitale*, 3(7). https://doi.org/10.6092/issn.2532-8816/9063. This article presents the data model used in the project to organize the genetic relationships between the manuscripts and the publications. Some aspects of the data model have evolved since the publication of the article (e.g., we do not take into account anymore the order of the *avant-textes* inside a genetic dossier), but the main concepts remain the same.
- [Summary](RoudGenetics.png) of all possible genetic relationships.
- Web application development: https://github.com/gustaveroudproject/roud-oeuvres-app. Documentation: https://github.com/gustaveroudproject/roud-oeuvres-app/blob/master/DOCUMENTATION.md.


## Sample data

#### "Deux moments d'une quête", *Suisse contemporaine*, 1941
- **IRI**: <http://rdfh.ch/0112/OXLofRkPRCKOcLrEy6DZ8w>
- **Genetic dossier IRI**: <http://rdfh.ch/0112/gtxOIRZySkGGkvXWg0nkEQ>
- **Description**. This publication reuses the article "Dédicace", published in the journal *Schweizer Annalen* in 1935 (`roud-oeuvres:publicationIsReusedInDossier`). For the article "Dédicace", there are two *avant-textes* (`roud-oeuvres:msIsAvantTextInGeneticDossier`) and one diary entry reused in it (`roud-oeuvres:msIsReusedInDossier`).
- **Data** are available in various formats (RDF-XML, TTL, JSON-LD) in the dir [`sample`](sample/DeuxMoments_SuisseContemporaine_1941).


#### Adieu 1927
- **IRI**: <http://rdfh.ch/0112/K2OVZydJS42GUsMJvKhP-A>
- **Genetic dossier IRI**: <http://rdfh.ch/0112/XqZUUgzjQXaX8rEnfyifJg>
- **Description**. This book is composed of two parts. The first has four *avant-textes*, the second only one. A second version of the work has been published.
- **Data** in progress.






