# Project-One
The goal of this internship project is to create an exploratory prototype that will enable folks to pull subsets of our private company datasets (initially focused on DatabaseUSA) to support ad-hoc analyses. The final artifact should be a python notebook (ideally distributed as a stand-alone executable) 
We will be writing programs to parse, analyze, and generate reports for enterprise datasets. 

STEP 1: Generate CSV Sheets for Ad-Hoc Analyses 	
  For a specified industry group (defined by a Functional Marker, a.k.a. FM)
    Additionally filtered by zip code or lat/long
      -All the HQs that match the industry group
      -All the parent-less businesses that match the industry group
      -All the children of HQ that match the industry group
      -All the children of HQs that match the industry group where the child and HQ have different NAICS codes
      -All the children of HQs that match the industry group where the child is considered a research facility 
      -It should be possible to export a CSV for any view
STEP 2: Packaging for Distribution
Develop a mechanism for distributing the python notebooks developed for the initial ad-hoc analyses as a stand-alone executable. We should not be building this on our own, we should leverage existing projects such as Nteract or Voila. Additional research is needed for Project A. Tyemill will propose and build the initial container to support this effort.
STEP 3: Expanding Ad-Hoc Boxed Queries
  Develop a python notebook, embedded in the stand-alone executable, that allows us to interactively apply a set of standard queries to our facilities datasets.
    For a specific industry (fm) or grid location (functional location)
      -How many HQs are there? 
      -What is the geographic distribution of the HQs?
      -How many children are there? 
      -What is the (functional) distribution of the children? 
      -What is the (geographic) distribution of the children?
      -How many SINK (Single Income No Kid) companies are there? 
    For geographic locations, same questions
    Generate visuals (charts, maps) for these standard queries
    Note: The full list of queries, views are not finalized. 
    
PROJECT DELIVERABLES:
  -Dynamic Workbook to make it easy to generate tables of data for inspection and ad-hoc analyses.
  -Documentation so anyone can open and run the notebook to replicate the results.
  -A stand-alone executable that allows anyone to get their hands on the query results for ad-hoc analysis with minimal overhead.

HOW THIS WILL BE USED:
Enable the team to surface data for ad-hoc analysis quickly and easily. The goal is to enable more people to look at the available data and help propose additional analyses and utility of functionally tagged datasets. 
Prototype views that can impact the design and analysis for data dashboards.

OTHER NOTES:
WHAT IS A BUSINESS?
For this project, a business is an entry in DBUSA where the business_type_code is not I (Individual).
WHAT IS AN INUDSTRY GROUP?
For this project, an Industry Group is defined by one or more related business risks (RBRs). These groups are defined as records in the locus_rbrs table in datastore.
WHAT IS AN HQ?
For this project, an HQ is any company record in DatabaseUSA where the DBUSA_Business_ID is the same as the HQ_ID. These attributes are defined in the business table from DatabaseUSA, uploaded to datastore here.  
WHAT IS A CHILD?
For this project, a child is any company record in DatabaseUSA where the HQ_ID is not empty and the record is not considered an HQ. These attributes are defined in the business table from DatabaseUSA, uploaded to datastore here.   (A child has an HQ_ID)
WHAT IS A RESEARCH FACILITY?
A research facility is an FM called “research and designed” in activity taxonomy


