# Software documentation

This page aims to synthetically document the software developed for the [LIFE RIPARIAS](https://www.riparias.be/) project and it is based on the work package it belongs to.

## Action A1 - Improving data flow for early detection

### Dataflow: the _big picture_

![data flow](https://user-images.githubusercontent.com/33662631/146169367-d271bf3a-edd5-4c2f-a371-2ab7587a3c9a.png)


The dataflow shown above can be divided into a left part and a right part.
-	The left part depicts how data flows to the [Global Biodiversity Information Facility](https://www.gbif.org/) (GBIF), “an international network and data infrastructure funded by the world's governments and aimed at providing anyone, anywhere, open access to data about all types of life on Earth" (source: ["What is GBIF?"](https://www.gbif.org/what-is-gbif) webpage). Notice that some data providers such as [iNaturalist](https://inaturalist.org/) and observations.be/waarnemingen.be publish their data about alien species on GBIF on a regular basis. Therefore, no mapping of their data is needed in the context of LIFE RIPARIAS. 

-	The right part shows how standardized data are retrieved from GBIF and fed regularly into the LIFE RIPARIAS aggregated database. The early detection system is built upon it.

### Setup dataflows to GBIF (Action A.1.3)

Publishing observations data to GBIF means standardizing them following the international [Darwin Core standard](https://dwc.tdwg.org/), intended to facilitate the sharing of information about biological diversity. 
The data mapping can be performed in different ways depending on the data provider: some of them could opt for mapping their own data and hosting them in the same database hosting the raw data. They could also opt for installing the Integrated Publishing Toolkit (IPT), thus being completely independent from the EVINBO team [oscibio](https://oscibio.inbo.be/), responsible for this action. Others could opt for sharing their own raw data with oscibio for assistance during the mapping and using the INBO's IPT for publishing. Data providers are invited to become official GBIF data publishers, even if their data are hosted on INBO's IPT.

### RIPARIAS aggregated database and early warning system (Action A.1.2)

Observations of a list of IAS is harvested from GBIF and imported in an aggregated LIFE RIPARIAS database every night. Above the database, an early warning system is built, manageable via a website: https://dev-alert.riparias.be/ (development version). Alerts can be set up by the user after the log-in with  a combination of taxonomic and/or geographic filters. An alert results in configurable periodic email notifications. An [early alert system mock-up](https://docs.google.com/presentation/d/1axpzA7atQgIpoqcgrxY1tShL77pPQ5ZCFnLYft4Lmo8/edit?usp=sharing) was developed to show what is intended to be  reached at the end of the development process (i.e. after version 2 is completed).

Useful links:
- Software development repository: https://github.com/riparias/early-warning-webapp/
- Software development documentation: https://github.com/riparias/early-warning-webapp/blob/main/CONTRIBUTING.md
- Early alert system website (dev version): https://dev-alert.riparias.be/

