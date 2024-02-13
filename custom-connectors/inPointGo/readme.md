# inPoint.Go Dossier connector

This connector can manage all inPoint.Go Dossier - Companies, Contacts, Contracts and OtherDossier.

## Publisher: H&S Heilig und Schubert Software AG

## Prerequisites

You will need the following to proceed:

- an inPoint.Cloud instance host
- an API username/password

## Supported Operations

All existing Dossier are available and used as prefixes

- Companies
- Contacts
- Contracts
- OtherDossiers

The same operations (albeit with different properties and document types) are available for all Dossiers, either referencing existing ones by their internal inPoint.Cloud Id or with the dossier's external Id.

### Companies

#### Get All Companies

#### Create Company

Following properties define a Company:

- Company External Id (reference from Master source data) (_required_)
- Company Name (_required_)
- Company Type (Lookup)
- Company Status (Lookup)
- Company Street
- Company City
- Company Zipcode
- Company Country (Lookup)
- Company Uid Number
- Company Domain
- Company Supervisor (Lookup)

#### Get Company (by Internal Id)

#### Update Company (by Internal Id)

#### Get Company by External Id

#### Upsert Company (by External Id)

Will either create a new Company or update an existing one based on it's External Id.

#### Get All Company's documents (by Internal Id)

#### Get Company's GeneralDocuments (by Internal Id)

#### Get Company's Messages (by Internal Id)

#### Get Company's Outgoing Invoices (by Internal Id)

#### Get Company's Incoming Invoices (by Internal Id)

#### Get Company's Protocols (by Internal Id)

#### Upload Document to Company (by Internal Id)

You can upload multiple files and specify one ContentTypeName.

#### Upload Document to Company by External Id

You can upload multiple files and specify one ContentTypeName.

#### Upload GeneralDocument to Company by External Id

You can upload multiple files and specify one ContentTypeName as well as Direction and Remarks.

#### Upload Document to Companies pool

You can upload multiple files and specify one ContentTypeName for the IDP processes to pick it up and classify/assign it to the appropriate Company.

### Contacts

#### Get All Contacts

#### Create Contact

Following properties define a Contact:

- Contact External Id (reference from Master source data) (_required_)
- Contact Name (_required_)
- Contact First Name
- Contact Last Name
- Contact Prefix (Lookup)
- Contact Phone
- Contact Mobile
- Contact E-Mail
- Contact Address
- Contact Zipcode
- Contact City
- Contact Country (Lookup)
- Contact Status (Lookup)
- Contact Companies (Lookup)
- Contact Function
- Contact Supervisor (Lookup)

#### Get Contact (by Internal Id)

#### Update Contact (by Internal Id)

#### Get Contact by External Id

#### Upsert Contact (by External Id)

Will either create a new Contact or update an existing one based on it's External Id.

#### Get All Contact's documents (by Internal Id)

#### Get Contact's GeneralDocuments (by Internal Id)

#### Upload Document to Contact (by Internal Id)

You can upload multiple files and specify one ContentTypeName.

#### Upload Document to Contact by External Id

You can upload multiple files and specify one ContentTypeName.

#### Upload GeneralDocument to Contact by External Id

You can upload multiple files and specify one ContentTypeName as well as Direction and Remarks.

### Contracts

#### Get All Contracts

#### Create Contract

Following properties define a Company:

- Contract External Id (reference from Master source data) (_required_)
- Contract Name (_required_)
- Contract Description
- Contract Category (Lookup)
- Contract Conclusion
- Contract Begin
- Contract End
- Contract Unlimited
- Contract Min Duration
- Contract Companies (Lookup)
- Contract Contacts (Lookup)
- Contract Validity (Lookup)
- Contract Payment target
- Contract Supervisor (Lookup)
- Contract Remarks
- Contract Links (Lookup)

#### Get Contract (by Internal Id)

#### Update Contract (by Internal Id)

#### Get Contract by External Id

#### Upsert Contract (by External Id)

Will either create a new Contract or update an existing one based on it's External Id.

#### Get All Contract's documents (by Internal Id)

#### Get Contract's GeneralDocuments (by Internal Id)

#### Get Contract's Messages (by Internal Id)

#### Get Contract's GeneralContracts (by Internal Id)

#### Upload Document to Contract (by Internal Id)

You can upload multiple files and specify one ContentTypeName.

#### Upload Document to Contract by External Id

You can upload multiple files and specify one ContentTypeName.

#### Upload GeneralDocument to Contract by External Id

You can upload multiple files and specify one ContentTypeName as well as Direction and Remarks.

#### Upload Document to Contracts pool

You can upload multiple files and specify one ContentTypeName for the IDP processes to pick it up and classify/assign it to the appropriate Contract.

### OtherDossiers

#### Get All OtherDossiers

#### Create OtherDossier

Following properties define a Company:

- OtherDossier External Id (reference from Master source data) (_required_)
- OtherDossier Name (_required_)
- OtherDossier Description
- OtherDossier Deadline
- OtherDossier Status (Lookup)
- OtherDossier Companies (Lookup)
- OtherDossier Contacts (Lookup)
- OtherDossier Supervisor (Lookup)
- OtherDossier Remarks

#### Get OtherDossier (by Internal Id)

#### Update OtherDossier (by Internal Id)

#### Get OtherDossier by External Id

#### Upsert OtherDossier (by External Id)

Will either create a new OtherDossier or update an existing one based on it's External Id.

#### Get All OtherDossier's documents (by Internal Id)

#### Get OtherDossier's GeneralDocuments (by Internal Id)

#### Get OtherDossier's Messages (by Internal Id)

#### Get OtherDossier's Outgoing Invoices (by Internal Id)

#### Get OtherDossier's Incoming Invoices (by Internal Id)

#### Get OtherDossier's Offers (by Internal Id)

#### Get OtherDossier's Orders (by Internal Id)

#### Get OtherDossier's OrdersConfirmations (by Internal Id)

#### Get OtherDossier's Protocols (by Internal Id)

#### Upload Document to OtherDossier (by Internal Id)

You can upload multiple files and specify one ContentTypeName.

#### Upload Document to OtherDossier by External Id

You can upload multiple files and specify one ContentTypeName.

#### Upload GeneralDocument to OtherDossier by External Id

You can upload multiple files and specify one ContentTypeName as well as Direction and Remarks.

#### Upload Document to OtherDossier pool

You can upload multiple files and specify one ContentTypeName for the IDP processes to pick it up and classify/assign it to the appropriate OtherDossier.

## Obtaining Credentials

Currently only a pre-defined API username/password combination can be used to connect to the inPoint.Cloud instance. Please contact your administrator to setup one.

## Getting Started

Check out the [inPoint.Cloud Documentation](https://serviceportal.hs.ag/docs/inPoint.cloud) for all details.

## Known Issues and Limitations

- custom connectors require a Power Automate license for Premium connectors
- custom properties are not currently supported
- no return schemas currently defined in swagger file
- not all operations are possible with external ids
- although all API operations support standard OData paging/filtering/sorting, it is currently limited in the Connector configurations
- the connector is not yet certified so wont be available as an 'AI Plugin' nor in the 'New custom connector from Github'

## Deployment Instructions

Either you import the provided sample Dataverse solution, or you manually import the connector directly in your Dataverse by choosing `Custom connectors` in your left panel then `New Custom Connector`/`Import an OpenAPI from URL` specifying the URL to the `apiDefinition.swagger.json` file in this repository.

In both cases you will need to adjust the Connector's `Host` to point to your inPoint.Cloud instance.
