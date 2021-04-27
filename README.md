# C-Path DAP Data Curation Template
Use this repository as a template to begin curation of a new dataset.

1. Click on the green **Use this template** button.
2. Choose the criticalpathinstitute organization.
3. Name the repository after the dataset.
4. Follow the SOPs below.

## Curation levels
Curation levels are defined in $doc


## Curation SOPs

### Basic 
All C-Path data receive basic curation upon ingest, before moving to the storage vault. Basic curation includes the following steps:

**Before submission:**

- Share dataset best practices document (in progress). Includes guidelines on how to best submit “tidy” data. 
- Clarify what data to expect from each source. If this is not specified in the DCA, it should be spelled out in some other communications. 
- Datasets should include a manifest (a list of all included files). We prefer that contributor create a manifest before uploading the data, but one could be created automatically. 

**Perform automated data checks:**

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

### Minimal 1 Curation
All DAP data receive minimal 1 curation before being moved to FAIR. The goal of minimal 1 is to provide rapid discovery of datasets, even in their raw form.

1. Create new repository from the data_curation_template.
2. 
files in manifest are present 

Files are typed. This will probably have to be done manually. How do we store this? As a spreadsheet in GH? As GH comments? 

Are data dictionaries present and ready to go into FAIR? 

One-off datasets are more likely to be small. Larger datasets are more likely to be tabular. (We hope.) 

Add tickets as needed. Some of them will go into Minimal 2 

Methods: 

Metadata would go into an actual database 

In the workspace, we could work with tables, but they would be stored externally in a relational database 

Workaround is to just use tables in in workspace, like Will did for beta 

Need tables for: 

Dataset 

Catalog 

Data dictionaries 

Lookups 

Manifest 

Files  

Tasks for curator would be to open manifest table and add missing types and notes on quality 

Open catalog, dictionary, and lookup tables to make sure they make sense. 

