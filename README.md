# rdUB - an application profile based on DataCite 4.3

rdUB is the data format of the research data platform “discover” of the University Library of LMU Munich. It extends the DataCite schema 4.3 by some elements, which are useful for searching and displaying versioned and fine granular data.  

## Support of fine granular data
We speak of (fine) granular data when there is more than one level of description. For example: A research project consists of several items. In addition, these items are aggregated into (different types of) datasets. As we describe both the project, the datasets and the items with (rdUB) metadata, there are three levels of description: The [project-level](https://github.com/UB-LMU/rdUB/blob/main/examples/VA_192.xml) (“level1”), the [aggregation-level](https://github.com/UB-LMU/rdUB/blob/main/examples/C53_v5_192.xml) (“level2”) and the [item level](https://github.com/UB-LMU/rdUB/blob/main/examples/G27060_v1_192.xml) (“level3”).
The information, to which level a research data object belongs to, can be stored in the element **hierarchy**. This element is especially useful for filtering the data, for example with the help of a facet or an OAI-PMH set.  

## Support of versioned data
rdUB has two elements for adding version information: **projectVersion** and **objectVersion**. While projectVersion refers to the version of the project as a whole, objectVersion refers to the version of a single object.  
Another element for describing versioned data is **currentVersion**. currentVersion tags the latest version of an object. This element is useful if you don`t support logical objects (= objects without versioning). 

## Overview of the rdUB elements
The root element of rdUB, rData, behaves like a wrapper. It contains a complete DataCite record and a couple of elements that are not (yet) part of DataCite.  
Apart from those already mentioned, the elements of rdUB are:

| Element | Description |
| ------ | ------ |
| contentUrls | The link(s) to the location(s) where the research data is stored. |
| metadataUrl | The link to the location where the metadata record (= rdUB) of the research data is stored.  |
| checksums | SHA1 file checksum(s). |
| collections | One ore more projects or (data) collections to which the research data can be related.  |
| faculties | The faculty or faculties, the research data belongs to. |
| geoIdentifier | An additional child element of datacite:geoLocation to store a reference, for example, to GeoNames. |
 
