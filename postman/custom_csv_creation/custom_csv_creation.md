# Project Title

Loading CSV File to AEP using Custom Fields

## Getting Started

Loading a CSV file into platform and demonstrating how to query it is one of the most common questions we get from Onboarding.  In the attached Video and using the Postman collection here, you can walk through this process and get an idea of how this operation is conducted at the API level.

### Prerequisites

AEP Access via Stage - This is running against Stage environment which requires VPN access - https://ui-stage-va7.dev.cloud.adobe.io/ga/home

IMS Org setup including JWT Token or Service Token for API access to AEP - API Client ID, Secret, and Code will need to be substituted into the Global Environment file -Global Variables.postman_globals.json

Modify the Environment variable with your IMS Org ID within the IMS Org Environment file - values and variables within this file are being set via Javascript embedded within the Postman scripts - IMS Org Level Variables.postman_environment.json

Standalone Postman version 2.1 and greater is needed to run the Postman files Create Custom Class for CSV.postman_collection.json

Bootstrapper UI access is required https://bootstrapper-stg.corp.adobe.com/  Please create an account if you don't have one

PSQL is needed to execute the Queries in Query Service - Follow the instructions for installing Postgres and within the binary folder there is the psql executable that will allow you to execute queries from Terminal


## Following the Steps

* **Step 1: Creation of the Custom Class using the Time Series Class** - This involves interaction with Schemaregistry API's and the determination of when to create a Custom Class vs. Custom Mixin vs. Custom Datatype involves a discussion of how the data is planned to be used, considerations around evolution and mutability of the schema, and organization standards.  Creation of an appropriate set of Classes, Mixins, and Datatypes for an organization is a key part of the Data Modeling exercise.  This represents an approach that could be taken but may not be appropriate for all circumstances.

* **Step 2:** Creation of the Schema using the Custom Class** - Schemas are the basic building block for storing data in the system.  This is used for validation, landing the data, interpreting data that is read out of the system, identifying specific elements to be used for Profile/Identity.  In short, this is the master key for your data and modification of this in production requires consideration of the implications.  This is also done via the SchemaRegistry system.

* **Step 3: Creation of the Dataset using the Custom Class** - Datasets are manifestations of the Schema into which data is being fed and this is the step where we tell the system where to put it, how it is stored, how it should be processed by supporting systems, and accompanying meta-data.  This information is stored in Catalog which can be observed in the URL's for the Postman API Calls.

* **Step 4: Using Bootstrapper UI to map the values within the CSV file to the elements within the Custom Class** - Bootstrapper is being used here to translate the flat structure of a CSV into a hierarchical data structure necessary for ingestion into AEP.  The tool is able to read the schema from Catalog and expose an interface for the user to pick the CSV columns that they want associated with the XDM elements.  A sample of the structure is created in this mapping process, along with the ability to export the Parquet, export a mapping file useful for CLI/Automated mapping of data, as well as uploading the data to AEP via the UI.

* **Step 5: Using Bootstrapper UI to ingest the CSV and generation of a Parquet file using Bootstrapper for Ingestion via Postman** - Bootstrapper can ingest the sample file or a Parquet file can be generated and the Postman collection includes the steps for Bulk Ingestion via the API.  The basic ingestion is to create a Batch via a POST call to Catalog, PUT the file into AEP, than Complete the Batch indicating to AEP that the Batch is complete.  This process requires a Parquet file when executed via Postman and we will soon have CSV and JSON support as well.

* **Step 6: Using Platform UI to check the Batch ingestion** - Within the User Interface, ingestion activity is observed at the Dataset level.  From the UI, we are able to view the schema details, batches attempted to load, dataset volumes, samples of the data, and detailed error messages.  Understanding the Catalog API queries where we are able to issue HTTP GET commands for Batch ID and Dataset ID with the corresponding UI values is helpful to get more details on the ingestion.

* **Step 7: Using Terminal to work with Query Services to query data from the data loaded to AEP** - Querying the data is ultimately the goal we are working toward and the PSQL interface provides a convenient and standard interface into AEP.  It is necessary to familiarize with the Postgres CLI commands to leverage this and once comfortable here, provides an easily automated interface into the data being loaded.


## Authors

Tom Silverstrim Adobe Experience Platform On-boarding team silverst@adobe.com

## Acknowledgments

* Nikhil Belsare for the great work on Bootstrapper
* Chris Fraser and Chris De Groot for their patience and details on how to execute via API
* Ryan Wilkes and UI team for the amazing progress on increasing visibility and utility of the system
