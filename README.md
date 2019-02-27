# Digital Delta API Specification Version 2.0.1
__A note on version numbers: As of the final state of this specification, the version number has changed from 2.0 to 2.0.1, to harmonize the version numbers between the regular DD-API and the DD-OPER-API.__

This specification describes the Digital Delta API Version 2.0.1 (DD-API 2.0.1). It is meant for both implementers and consumers of the Digital Delta API specifications.

## About the Digital Delta 2.0.1 specification

Version 2.0.1 of the DD-API builds on the foundation as specified in [version 1.0](https://github.com/DigitaleDeltaOrg/dd-api-spec/blob/master/README.md).

See the [Digital Delta project](http://digitaledelta.org) for background information.

The changes in version 2.0.1 compared to 1.0 can be summarized as:

* Renaming of some attributes, e.g. for consistency reasons, or to clarify the content of the attribute
* Adjusting some resource object types in the response in order to let them adhere better to standards. For instance, the Location objects now is a GeoJSON object) and the paging information has been re-arranged according the DSO API guidelines.
* Adding attributes to the Timeseries object that facilitate the definition of computation results and ensemble runs.
* Adding interval information to the values in a Timeseries
* Adding the concept of aspect sets, a mechanism to group related time series, e.g. the minimum, maximum and average of a measured quantity, or the direction and amplitude of wave field.

_Due to the nature of the changes, version 2.0.1 is not backwards compatible with version 1.0._  

The status of this specification is **final**.

## Getting started

The specification is written in [RAML 1.0](https://raml.org), a 'language' to define [REST](https://nl.wikipedia.org/wiki/Representational_state_transfer) (REpresentational State Transfer) service.

It is a _specification_. This means that there is no full implementation of this specification available in this repository.
There are, however, [result samples](https://github.com/DigitaleDeltaOrg/dd-api/tree/master/examples) available. Some [helper classes](https://github.com/DigitaleDeltaOrg/dd-api/wiki/C%23-Generic-Base-Classes-for-DD-API-2.0) in the [C# programming language](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/index) are available in the [Wiki](https://github.com/DigitaleDeltaOrg/dd-api/wiki).

To read the RAML specification, some [tools](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Tools) are recommended. Some tools are also capable of generating documentation, or code skeletons for both consumers and implementers.

The [HTML specifications](http://htmlpreview.github.com/?https://github.com/DigitaleDeltaOrg/dd-api/blob/master/dd.v201.html) can also be used and may be easier to read.

### Prerequisites
The easiest way to get the specification is to download the generated HTML files.
To be able to use the RAML files, please consult the [tools](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Tools) section. Knowledge of the [RAML language](https://raml.org) is then recommended.

## The specification
Version 2.0. includes two specifications.
The [DD-API 2.0.1](dd.v20.raml) of the specification is the 'general purpose' specification, with Url's that facilitate both searching for and retrieving data. Hence it both for discovery and for getting data.

The Operational extension ["DD-OPER-API"](dd-oper.v20.raml) is an extension developed for/by Rijkswaterstaat, designed to retrieve data using a fixed strict Url-path. It only differs from the generic version in the Url-syntax. The DD-OPER-API does not support discovery.

The changes between version 1.0 and 2.0.1 are described [here](https://github.com/DigitaleDeltaOrg/dd-api-spec/blob/2.0/Documentation/Changes_between_1.0_and_2.0.md).

## Implementations
The [Current Implementations](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Current-implementations) contains the most recent list of implementations of the Digital Delta Specifications.
