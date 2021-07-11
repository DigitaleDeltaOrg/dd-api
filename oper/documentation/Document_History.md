
| Date | Author | Changes |
| --- | --- | --- |
| 2018-04-01 | RWS   | New version created based on DD API 1.0 and MKK-DL API 1.0 |
| 2018-04-20 | RWS   | End-points and request parameters finalised. Naming conventions aligned with DD API 1.9 proposal. |
| 2018-07-07 | RWS   | Changed to dd-oper version 2.0 and now as Extension of DD-API 2.0 raml. |
| 2018-07-18 | RWS   | Change to error/problem response due to DD API 2.0 change. |
| 2018-09-11 | RWS   | References to '/Libraries' changed to 'libraries'. |
| 2018-12-11 | RWS   | Added additional discovery endpoint /quantities/... |
| 2018-12-21 | RWS   | Removed obsolete endpoint /aspectsetlist. |
| 2019-01-14 | RWS   | Changed response structure of a single quantity resource request (../quantities/{quantityName}). |
| 2019-01-14 | RWS   | QuantityName and LocationName values are used as url parameters and will always be in lower-case. |
| 2019-01-14 | RWS   | Attribute crsName added to Location (GeoJSON) properties.   |
| 2019-06-19 | DD team | Split DD-API and DD-OPER-API specifications. |  
| 2019-11-10 | DD team | Further splitting of DD-API and DD-OPER. |
| 2020-10-08 | RWS   | Added queryParameter 'extendScope' on endpoints /quantity/{}/locations and /locations/{}/quantity.  
| 2020-10-08 | RWS   | Added queryParameter 'timeseriesFilter' on DD-OPER endpoint /location{}/quantities/{}/timeseries via a TRAIT.  


