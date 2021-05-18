# C-Path DAP Data Curation Template
Use this repository as a template to begin curation of a new dataset.

1. Click on the green **Use this template** button.
2. Choose the criticalpathinstitute organization.
3. Name the repository after the dataset.
4. Follow the SOPs below.

## Curation levels
Curation levels are defined in [levels.md](https://github.com/criticalpathinstitute/data_curation_template/blob/main/levels.md)

## Curation SOPs

### Basic 
All C-Path data receive basic curation upon ingest, before moving to the storage vault. Basic curation includes the following steps:

**Before submission:**

- Share dataset best practices document (in progress). Includes guidelines on how to best submit “tidy” data. 
- Clarify what data to expect from each source. If this is not specified in the DCA, it should be spelled out in some other communications. 
- Datasets should include a manifest (a list of all included files). We prefer that contributor create a manifest before uploading the data, but one could be created automatically. 

**Perform automated data checks:**

- Assign a dataset ID of the form RDCA##### 
- Does the dataset match the manifest? 
- Are there data dictionaries for tabular data? 
- Are CRFs and protocols provided? 
- Do we have enough information to create a catalog entry in FAIR (DCAT+ disease specific metadata) 

**Perform manual checks:** 

- Make sure there is not PHI (data elements, master keys, etc.)  
- Make sure the uploaded data matches project(s) in DCA 

**Send receipt:**
- Receipt automatically sent to Scientific Director and data contributor.
- Receipt includes: 
    - Manifest 
    - Summary of received files (names, size, number of columns and rows) 
    - Dataset Completeness (number of columns with binned percentages of complete observations) 

### FAIR Metadata 1 Curation
**Internal: FM1, External: raw**
All DAP data receive minimal 1 curation before being moved to FAIR. The goal of minimal 1 is to provide rapid discovery of datasets, even in their raw form.

 - Create new repository from the data_curation_template (this repo).
 - In the curation Workspace, create a folder hierarchy following naming conventions:
    - Top-level folder named for the dataset ID (e.g., RDCA#####)
        - *Subdirectories for:*
        - Original Data
        - Documentation
        - FAIR uploads (catalog, dictionaries, and metadata go here) 
          - *Subdirectories for versions:*
          - Beta 
          - V1 
          - V2 
          - ...
 - Copy the dataset into the curation Workspace in the appropriate folder under `Original data`.
 - Open a new issue using the template 'M1: Convert to dataset' and follow the steps on the template
     - **NOTE:** These datasets need to go into a relational database that connects to the workspace, but for now, they will be saved as single datasets in the workspace.
 - Open a new issue using the template 'FM1: Create data dictionaries' and follow the steps on the template.
 - Open a new issue using the template 'FM1: Metadata and data catalog' and follow the steps on the template.
 - Open a new issue using the template 'FM1: Manual checks' and follow the steps on the template.
 - Open a new issue using the template 'FM1: Scripts and upload' and follow the steps on the template.
     - Data files will go in the folder $datasetID/FAIR uploads/V1 
     - Data should be marked as "raw"

### FAIR Metadata 2 Curation
**Internal: FM2, External: non-standardized**
All data receive FAIR Metadata 2 curation and update to FAIR, but priority rules may delay this step for some datasets. The goal of FM2 is to have all data tables on FAIR, but not standardized or cleaned up.
- Open a new issue using the template 'FM2: Convert all tables to CSV' and follow the steps on the template. Separate Excel workbooks into single sheets and save as CSV.
- Open a new issue using the template 'FM2: Dictionaries for all tables' and follow the steps on the template.
- Open a new issue using the template 'FM2: Other tasks discovered during FM1 assessment' and follow the steps on the template. 
- Open a new issue using the template 'FM2: Scripts and upload' and follow the steps on the template.
     - Data files will go in the folder $datasetID/FAIR uploads/V2 
     - Data should be marked as "minimally curated"

### FAIR variables 1
**Internal: FV1, External: core variables standardized**
Datasets receive full curation in order of their priority. Full 1 includes only selected variables, which may differ among consortia and among  types of datasets.

The default set of variables to curate for Full 1 are (**for review**): 
- Timing 
- Trial level information 
- Demographics 
- Diagnosis variables 
- Study Medications (not concomitant medicatioons)
- Procedures  
- Lab results
- Imaging? – if the put it there, it is probably important  

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
FV 2 curation is the same as FV 1, but it includes additional variables whose curation is requested after full 1.
- Mark dataset as "additional variables standardized"

### FAIR variables 3
**Internal: FV3, External: all variables standardized**
FV3 curation is the same as FV 1 and 2, but it includes all variables. Some dataset may never reach this level.
- Mark dataset as "all variables standardized"


