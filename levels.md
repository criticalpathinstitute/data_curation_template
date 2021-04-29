## Curation level definitions
### Basic 
All C-Path data receive basic curation upon ingest, before moving to the storage vault. Basic curation includes the following checks:

- Does the dataset match the manifest? 
- Are there data dictionaries for tabular data? 
- Are CRFs and protocols provided? 
- Do we have enough information to create a catalog entry in FAIR (DCAT+ disease specific metadata)?
- Make sure there is not PHI (data elements, master keys, etc.)  .
- Make sure the uploaded data matches project(s) in DCA.

At the end of basic curation, a receipt is automatically sent to Scientific Director and data contributor.

### Minimal 1
All DAP data receive minimal 1 curation before being moved to FAIR. The goal of minimal 1 is to provide rapid discovery of datasets, even in their raw form. Minimal 1 curation includes:
- Create a DCAT-compliant data catalog. 
- Create FAIR compliant data dictionaries for any data that are in a single table format and conform to postgres rules.
- Mark data status as "raw".

### Minimal 2
All data receive minimal 2 curation and update to FAIR, but priority rules may delay this step for some datasets. Minimal 2 curation includes:
- Separate Excel workbooks into single sheets and save as CSV.
- Make sure all data tables have dictionaries.
- Fix non-SQL compliant variable names
- Other tasks discovered during Minimal 1 assessment. 
- Mark data status as "minimally curated"

### Full 1
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

Map files to a common data model (CDM) 

 We are testing OMOP CDM for this purpose 

Convert variable name to standard name (from OMOP if available) 

Categorical variables: 

Map values to standard terminology from OMOP or ontology or internal if nothing exists. 

If internal, request terms in OMOP or ontology 

Ordinal variables: 

Map to standard terminology 

Continuous variables: 

Clean any obvious errors 

Check for and mark outliers (when possible) 

Requires a standard range or a large enough population 

Add column to mark outliers 

For all variable types: 

Keep original value and mark column as verbatum 

Add new columns for changed value and change reason 

Update data dictionary with status of variable (raw, curated, ontologized) 

Enforce naming conventions for data dictionaries 

### Full 2
Full 2 curation is the same as full 1, but it includes additional variables whose curation is requested after full 1.

