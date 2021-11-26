# ala-data-task
A data task prepared for an interview with the Atlas of Living Australia

### Methodology


### Notes
1. No Coordinate Reference System (CRS) was specified in the metadata for the ALA dataset. The terms in the field seem to mostly follow Darwin Core Terms (https://dwc.tdwg.org/terms/), however the field 'geodeticDatum' is missing. A quick google and download of ALA data suggests that the standard for that organisation is WGS84. To sense-check this assumption, the data was plotted in QGIS. As is typical of occurrence records, many were located around roads and waterways. Additionally, there was a cluster around the Australian National Botanic Gardens, indicating that WGS is the correct CRS. 


### Data sources
* `ALA_EcoCommons_Data_Analyst_dataset.csv`: Supplied by Atlas of Living Australia for the task; used with permission
* `dwca-griis-australia-v1.6.zip`: Randall J, McDonald J, Wong L J, Pagad S (2021): Global Register of Introduced and Invasive Species - Australia. v1.6. Invasive Species Specialist Group ISSG. Dataset/Checklist. https://cloud.gbif.org/griis/resource?r=griis-australia&v=1.6
