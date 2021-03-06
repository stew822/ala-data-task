# ala-data-task
A data task prepared for an interview with the Atlas of Living Australia.

View the rendered HTML for the Jupyter (Python) Notebook at https://stew822.github.io/ala-data-task/ALA%20Data%20Task%20-%20Stewart%20Bisset.html

### Aim
This project is intended to showcase my experience in working with biodiversity data. I have deliberately focussed on integrating data, as this is where my skillset is strongest. The aim of the project is to add some additional information to the ALA data, namely the alien status of the species, and to map this information in an easy-to-understand manner. The alien status of the species comes from the Global Register of Introduced and Invasive Species - Australia checklist (https://cloud.gbif.org/griis/resource?r=griis-australia). 

### Methodology
In order to integrate the GRIIS data, the scientific names in both datasets need to be standardised against a reference backbone. Given the taxon-specific nature of the ALA dataset (reptiles), it would make the most sense to harmonise the names against a reptile-specific Taxonomic Authority File. However, for the purposes of this task, I will use GBIF's Backbone Taxomony (https://www.gbif.org/dataset/d7dddbf4-2cf0-4f39-9b2a-bb099caae36c), as GBIF provides easy-to-use fuzzy name matching functions in their Species API (/species/match, https://www.gbif.org/developer/species). This is not best-practice standardisation methodology (taxon and region-specific authority files provide much greater certainty of matching, as well as different approaches than fuzzy matching, and a lack of manual verification). However, it will suffice for the example. 

### Files in repository
* `ALA Data Task - Stewart Bisset.html`: The HTML file generated from the Jupyter Notebook
* `ALA Data Task - Stewart Bisset.ipynb`: The Jupyter Notebook
* `README.md`: This file
* `proposed_data_task.txt`: Original instructions.

### Notes
1. No Coordinate Reference System (CRS) was specified in the metadata for the ALA dataset. The terms in the field seem to mostly follow Darwin Core Terms (https://dwc.tdwg.org/terms/), however the field 'geodeticDatum' is missing. A quick google and download of ALA data suggests that ALA typically uses WGS84. To sense-check this assumption, the data was plotted in QGIS. As is typical of occurrence records, many were located around roads and waterways. Additionally, there was a cluster around the Australian National Botanic Gardens, indicating that WGS84 is likely correct. However, in a real situation, I would attempt to verify the CRS and other relevant details with the third-party before proceeding to ingest the data, as the approach used would not handle eg. the 1.8m difference between GDA94 and GDA2020.
2. 193 records were located in New South Wales (Jervis Bay), rather than being contained to the ACT as specified. There were left in the dataset as it does not impact the visualisation.


### Data sources
* `ALA_EcoCommons_Data_Analyst_dataset.csv`: Supplied by Atlas of Living Australia for the task; used with permission
* `dwca-griis-australia-v1.6.zip`: Randall J, McDonald J, Wong L J, Pagad S (2021): Global Register of Introduced and Invasive Species - Australia. v1.6. Invasive Species Specialist Group ISSG. Dataset/Checklist. https://cloud.gbif.org/griis/resource?r=griis-australia&v=1.6
