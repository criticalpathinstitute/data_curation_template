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
- Mark data status as "uncurated".

### Minimal 2
All data receive minimal 2 curation and update to FAIR, but priority rules may delay this step for some datasets. 
