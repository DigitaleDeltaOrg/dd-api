# Changes between version 1.0 and 2.0.x

## Introduction
This document describes the changes between versions 1.0 of the specification and version 2.0.x. These changes can be summarized as:
* Renaming of some attributes, e.g. for consistency reasons, or to clarify the content of the attribute
* Adjusting some resource object types in the response in order to let them adhere better to standards. For instance, the Location objects now is a GeoJSON object) and the paging information has been re-arranged according the DSO API guidelines.
* Adding attributes to the Timeseries object that facilitate the definition of computation results and ensemble runs.
* Adding interval information to the values in a Timeseries
* Adding the concept of aspect sets, a mechanism to group related time series, e.g. the minimum, maximum and average of a measured quantity, or the direction and amplitude of wave field.

_Due to the nature of the changes, versions 2.0.2 and 2.0.1 are not backwards compatible with version 1.0._  

## Type changes
(Almost) all types have changed in version 2.0.x, but may not require many changes to the implementing code.

### Generic to all types
##### UUIDs replaced by IDs
The requirement that every object must be identified by a fixed UUID, will be changed. Every object will now require an identifying id, which is a string. If providers want to keep using a UUID, they just need to change the name of the property to ID.

### New types in 2.0.x
##### AspectSet
Defines an aspect set.

##### AspectSetsListResponse
Defines a list response of aspect sets.

##### Provider
Defines the provider resource type for specifying provider-specific responses.

##### ProblemResponse
Defines error information.

### Generic to all list responses
The prev/next paging attributes of version 1.0 has been replaced by a paging resource object.
All list-responses, except for responses that are in GeoJSON format, **must** provide a paging resource object.
The paging resource object **must** contain the following properties:
- totalObjectCount: contains the number of records that satisfy the query requirements.
- prev: contains the Url for the previous page, if available, else null.
- next: contains the Url for the next page, if available, else null.
- maxPageSize: maximum page size as defined by the provider.
- minPageSize: minimum page size as defined by the provider.

The pages resource object **may** contain the following properties:
- first: contains the Url for the first page.
- last: contains the Url for the first page.
- self: contains the Url for the current request.

### Generic to all responses
All responses **may** provide a provider resource object. For the DD-OPEN specification, the provider resource **must** be specified.
The provider resource object contains the following properties:
- name: name of the provider (required)
- supportURL: URL of the provider used for support questions. (required)

The provider resource object **may** contain the following properties:
- apiVersion: the version of the API used to provide the response. (optional, may be required in a future version)
- responseType: the exact type of the response. (optional, may be required in a future version)

apiVersion plus responseType can be used to parse the response.

When a request encounters an error, a problem resource object **must** be returned.

The problem resource object **must** have the following properties:
- status: HTTP status code of the error

The problem resource object **may** have the following properties:
- type: Url specific for the error type.
- title: title of the error
- detail: details of the error
- instance: internal reference to the provider system (log?)

### Specific end-points
#### /datasources
The /datasources end-point will be renamed to /resources

#### /locations
- name will become locationName
- code will become locationCode
- node will become nodeId

#### /timeSeries (generic)
Changes to the filter options:
- start will become startTime
- end will become endTime
- observationType will become observationTypeId

New filter options:
- realization: optional, required for ensembles (future)
- aspectSet: optional, specifies the aspectSet

Discussion: the following, or filter syntax?
- includeMetaData: default true. if false, only data is returned, not the references.
-  quantity: optional, filters by quantity without needing to specify observationTypeId.
-  parameterCode: optional, filters by parameterCode without needing to specify the observationTypeId.
-  locationName: optional, filters on location name, instead of locationCode.
-  sourceName: optional, allows filtering on source.

#### /aspects
Aspects is a new, required end-point for DD-OPER only. Replaced in version 2.0.1 by new end-point /quantities/...
