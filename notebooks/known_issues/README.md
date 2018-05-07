# Known Issues


### Asset Management
https://github.com/ooi-integration/asset-management

* The cycle to load changes to asset information into the system is slow. Pull Request -> Release Tag -> Redmine Ticket -> Load onto Test -> Verification on Test -> Load onto Production -> Verification on Production. Could automated Pull Request to Load onto Production with DevOps tools similar to GitOps.
* If a operator with the right permissions uses the OOI user interface (ooinet.oceanobservatories.org) to update asset information in the system, these changes are not recorded and version controlled through this GitHub repository.

### Preload
https://github.com/oceanobservatories/preload-database

* This is a poorly formatted sheet that contains parameters that are no longer produced by the system. It is tricky to propose updates without affecting the formatting of the sheet. It needs to be cleaned up. 
* Unclear what the process is to integrate proposed changes into the system. 
* Preload information should be available for query via an organized m2m endpoint.

### OOI Raw Data Parsers
https://github.com/oceanobservatories/mi-instrument  

* Cannot run data ingestion on Cabled Port Agent Log files, only raw data stored on the UW archive.


### OOI Data Product Algorithms
https://github.com/oceanobservatories/ion-functions/  

* This is OK. Could be cleaned up to invite contribution from the user community.
* Could develope a M2M endpoint that allows users to specify a custom algorithm for data processing during on-demand data requests.


### QC Algorithm Values
https://github.com/ooi-integration/qc-lookup

* Global Range Test: Missing some values.
* Local Range Test: Does not work.
* Spike Test: Does not work reliably.
* Trend Test: Does not work.
* Gradient Test: Does not work.


### Annotations
* Annotations at the parameter level are referenced by PD number, instead of parameter name. This makes it hard for users to know which parameters are affected, unless they parse preload off GitHub (there is no preload m2m endpoint) or a data evaluator includes the affected parameter name in the annotation.
* Annotation time stamps are returned as milliseconds since 1970, which data time stamps are returned as seconds since 1900.

