# Postman Samples

This folder contains a series of Postman collections intended to be used in training technical users on the details of creating solutions using AEP.  The samples walk-through. a number of different common scenarios and are intended to educate users on the implementation details in order to accelerate Automation and Developer efforts. 

## Getting Started

Before diving into the Postman samples, it is helpful to refer to the intent of each sample.  In our experience, these samples become templates of sorts as we encounter specific use cases within IMS Orgs and the samples are combined and customized accordingly.  The Swagger documentation is the ultimate source of truth that we are referring to and these samples are built on that foundation.  Where there are questions, this is the source that is to be referred to.

### Prerequisites

There are a number of systems that you need access to in order to fully leverage the samples.  This represents a list of the most commonly used resources.

**AEP Access via Stage** - This is running against Stage environment which requires VPN access - https://ui-stage-va7.dev.cloud.adobe.io/ga/home

**IMS Org setup including JWT Token or Service Token for API access to AEP** - API Client ID, Secret, and Code will need to be substituted into the Global Environment file -Global Variables.postman_globals.json

**Modify the Environment variable with your IMS Org ID within the IMS Org Environment file** - values and variables within this file are being set via Javascript embedded within the Postman scripts - IMS Org Level Variables.postman_environment.json

**Standalone Postman version 2.1 and greater** - We are leveraging Postman extensively and it is needed to run the Postman files Create Custom Class for CSV.postman_collection.json There are a number of different tools for interacting with API's and this is the current standard for our efforts.

**Bootstrapper UI access** https://bootstrapper-stg.corp.adobe.com/  Please create an account if you don't have one

**PSQL** is needed to execute the Queries in Query Service - Follow the instructions for installing Postgres and within the binary folder there is the psql executable that will allow you to execute queries from Terminal


## Following the Steps

Uploading the samples to Postman involves the Import capabilities.  Once a collection and variables are imported, the common changes that need to be done within your Postman instance are:
**IMS Org ID** - this variable is necessary to customize for the system to which you have access
**Client ID** - service tokens are commonly used and instructions for using the JWT tokens are contained within the top level Adobe Experience Platform collection in this directory.
**Client Secret** - This value is needed to retrieve a Bearer token and cannot be shared publicly.
**Client Code** - This values is also needed and cannot be shared publicly. 


## Authors

Tom Silverstrim Adobe Experience Platform On-boarding team silverst@adobe.com

## Acknowledgments

* Nikhil Belsare for the great work on Bootstrapper
* Chris Fraser and Chris De Groot for their patience and details on how to execute via API
* Ryan Wilkes and UI team for the amazing progress on increasing visibility and utility of the system
