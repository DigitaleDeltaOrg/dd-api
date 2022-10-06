# Digital Delta API Specification Version 2.0.2

This specification describes the Digital Delta API Version 2.0.2 (DD-API 2.0.2). It is meant for both implementers and consumers of the Digital Delta API specifications.  
See the [Digital Delta project](http://digitaledelta.org) for background information.

This version replaces version 2.0.1.  
The difference between DD-API 2.0.2 and DD-API 2.0.1 consists of **textual changes only** in the documentation of the specification.

The status of this specification is **final**.

## Getting started

The specification is written in [RAML 1.0](https://raml.org), a 'language' to define [REST](https://nl.wikipedia.org/wiki/Representational_state_transfer) (REpresentational State Transfer) service.

It is a _specification_. This means that there is no full implementation of this specification available in this repository.
There are, however, [response examples](https://github.com/DigitaleDeltaOrg/dd-api/tree/master/examples) available. Some [helper classes](https://github.com/DigitaleDeltaOrg/dd-api/wiki/C%23-Generic-Base-Classes-for-DD-API-2.0) in the [C# programming language](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/index) are available in the [Wiki](https://github.com/DigitaleDeltaOrg/dd-api/wiki).

To read the RAML specification, some [tools](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Tools) are recommended. Some tools are also capable of generating documentation, or code skeletons for both consumers and implementers.

The [HTML specifications](https://digitaledeltaorg.github.io/dd.v202.html) are generated from the RAML specification, and may be easier to read.

### Prerequisites
The easiest way to get the specification is to download the generated HTML files.
To be able to use the RAML files, please consult the [tools](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Tools) section. Knowledge of the [RAML language](https://raml.org) is then recommended.

## The DD-API 2.0.2 specification

The changes between version 1.0 and 2.0.* are described [here](https://github.com/DigitaleDeltaOrg/dd-api/blob/master/documentation/Changes_between_1.0_and_2.0.md).

Version 2.0. includes two specifications.
The [DD-API 2.0.2](dd.v202.raml) of the specification is the 'general purpose' specification, with Url's that facilitate both searching for and retrieving data. Hence it both for discovery and for getting data.

The OPERational extension ["DD-OPER-API"](oper/dd-oper.v202.raml) is an extension developed for/by Rijkswaterstaat, designed to retrieve data using a fixed strict Url-path. It only differs from the generic version in the Url-syntax. The DD-OPER-API provides a different set of endpoints for discovery.

Additional documentation can be found on [https://digitaledeltaorg.github.io](https://digitaledeltaorg.github.io), including readable version of the specification (HTML generated from the RAML):
* [dd.v202.html](https://github.com/DigitaleDeltaOrg/digitaledeltaorg.github.io/blob/master/Old%20files/dd.v202.html) (general DD-API)
* [dd-oper.v202.html](https://github.com/DigitaleDeltaOrg/digitaledeltaorg.github.io/blob/master/Old%20files/dd-oper.v202.html) (DD-OPER extension)

## Implementations
The [Current Implementations](https://github.com/DigitaleDeltaOrg/dd-api/wiki/Current-implementations) contains the most recent list of implementations of the Digital Delta Specifications.
