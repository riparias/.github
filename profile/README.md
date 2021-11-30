# Software documentation

This page aims to synthetically document the software developed for the [LIFE RIPARIAS](https://www.riparias.be/) project. We describe it based on the work package it belongs to.

## Action A1 - Improving data flow for early detection

### Dataflow: the _big picture_

![data flow](https://user-images.githubusercontent.com/33662631/143939604-93eec246-bd33-48c0-b500-2abd6af1d455.png)

We can clearly separate the dataflow shown above into a _left part_ and a _right_ part. The left part accounts for estabilishing data flows to the [Global Biodiversity Information Facility](https://www.gbif.org/) (GBIF), _an international network and data infrastructure funded by the world's governments and aimed at providing anyone, anywhere, open access to data about all types of life on Earth_ (source: ["What is GBIF?"](https://www.gbif.org/what-is-gbif) webpage). Notice that some data providers such as [iNaturalist](https://inaturalist.org/) and observations.be/waarnemingen.be publish their data on GBIF about alien species on a regular basis and so no mapping is needed in the context of LIFE RIPARIAS. The right part accounts for retrieving the standardized data from GBIF and so regularly maintain the RIPARIAS aggregated database. The early alert system is built upon it.

### Setup dataflows to GBIF (Action A.1.3)

Publishing observations data to GBIF means standardizing them following the international [Darwin Core standard](https://dwc.tdwg.org/), intended to facilitate the sharing of information about biological diversity. The data mapping can be performed in different ways depending on the data provider: some of them could opt for mapping their own data and hosting them in the same database hosting the raw data. They could also opt for installing the Integrated Publishing Toolkit (IPT) and so being completely independent by the EVINBO team [oscibio](https://oscibio.inbo.be/), responsible for this action. Others could opt for sharing their own raw data with oscibio for assistance during the mapping and using the INBO's IPT for publishing. However, data providers are invited to become official GBIF data publishers, even if their data are hosted on INBO's IPT.

### RIPARIAS aggregated database and early warning system (Action A.1.2)

We automatically harvest observations of alien species from GBIF and import them in an aggregated RIPARIAS database at each night. Above the database, an early warning system is built, manageable via a website: https://dev-alert.riparias.be/ (development version). Alerts can be set up by the user after the log-in by a combination of taxonomic and/or geographic filters. The creation of an alert results in periodic email notifications at the desired frequency. We provide an [early alert system mock-up](https://docs.google.com/presentation/d/1axpzA7atQgIpoqcgrxY1tShL77pPQ5ZCFnLYft4Lmo8/edit?usp=sharing) to show the goal we would like to reach at the end of the development process.

Software development repository: https://github.com/riparias/early-warning-webapp/
Early alert system website (dev version): https://dev-alert.riparias.be/
