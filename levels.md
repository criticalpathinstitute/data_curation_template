## Curation level definitions
### Level 0 
All C-Path data receive basic Ilevel 0) curation upon ingest, before moving to the storage vault. Level 0 curation includes the following checks:

- Does the dataset match the manifest? 
- Are there data dictionaries for tabular data? 
- Are CRFs and protocols provided? 
- Do we have enough information to create a catalog entry in FAIR (DCAT+ disease specific metadata)?
- Make sure there is not PHI (data elements, master keys, etc.)  .
- Make sure the uploaded data matches project(s) in DCA.

At the end of basic curation, a receipt is automatically sent to Scientific Director and data contributor and stored in our archival bucket.
Going forward, will automate the movement of level 0 data to workspace at the end of ingest.

### FAIR metadata
All DAP data receive FAIR metadata curation before being moved to FAIR. Some data will be ingested in a state that is already end of FM1 and will go directly to FM2.
#### FAIR metadata 1
**Internal: FM1, External: raw**
The goal of FAIR metadata 1 is to provide rapid discovery of datasets, even in their raw form. FAIR metadata 1 curation includes:
- Create a DCAT-compliant data catalog. 
- Create FAIR compliant data dictionaries for any data that are in a single table format and conform to postgres rules.
- Mark data status as "raw".

### FAIR metadata 2 (FM2)
**Internal: FM2, External: non-standardized**
All data receive FAIR metadata 2 curation and update to FAIR, but priority rules may delay this step for some datasets. Some datasets will be ready for FM 2 immediatly after ingestion. FAIR metadata 2 curation includes:
- Separate Excel workbooks into single sheets and save as CSVs.
- Make sure all data tables have dictionaries.
- Fix non-SQL compliant variable names
- Other tasks discovered during Minimal 1 assessment. 
- Mark data status as "non-standardized"

### FAIR variables 1
**Internal: FV1, External: core variables standardized**
Datasets receive full curation in order of their priority. Full 1 includes only selected variables, which may differ among consortia and among  types of datasets.

The default set of variables to curate for Full 1 are (**for review**): 
- Timing 
- Trial level information 
- Demographics 
- Diagnosis variables 
- Medications 
- Procedures  
- Labs? 
- Imaging? – if the put it there, it is probably important 
- Others? 

Full 1 curation includes, for selected variables:
- Clean and standardize data: 
   - Map files to a common data model (CDM). We are testing OMOP CDM for this purpose.
- Convert variable name to standard name (from OMOP if available) 
- Categorical variables: 
   - Map values to standard terminology from OMOP or ontology or internal if nothing exists. 
   - If internal, request terms in OMOP or ontology 
- Ordinal variables: 
   - Map to standard terminology 
- Continuous variables: 
   - Clean any obvious errors 
   - Check for and mark outliers (when possible) 
      - Requires a standard range or a large enough population 
   - Add column to mark outliers 
- For all variable types: 
   - Keep original value and mark column as verbatum 
   - Add new columns for changed value and change reason 
   - Update data dictionary with status of variable (raw, curated, ontologized) 
- Enforce naming conventions for data dictionaries 
- Mark dataset as "core variables standardized"

### FAIR variables 2
**Internal: FV2, External: additional variables standardized**
Full 2 curation is the same as full 1, but it includes additional variables whose curation is requested after full 1.

### FAIR variables 3
**Internal: FV3, External: all variables standardized**
FV3 curation is the same as FV 1 and 2, but it includes all variables. Some dataset may never reach this level.

