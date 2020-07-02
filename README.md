# covid-configuration

This repository contains demo data and preconfiguration settings for covid reference instance.

Some examples of configuration are described below.

## Valid Sources
Valid Sources table consists of facilityTypeCode and facilityCode/organizationName.

In facilityTypeCode column there should be all codes of facility types which are to be supplied by warehouses or organizations.

In facilityCode column there should be codes of facilities which supply other facilities. Most often it will be a warehouse. 

In organizationName column there should be a name of a supplying organization if there is such.

Exemplar facility types and facility codes:

| facilityType     | facilityTypeCode | facilityCode |
|------------------|------------------|--------------|
| Clinic           | privC            | FAC01        |
| Private Hospital | privH            | FAC02        |
| Warehouse        | warehouse        | FAC03        |
| Clinic           | privC            | FAC04        |
| Private Hospital | privH            | FAC05        |
| Warehouse        | warehouse        | FAC06        |

In this example there are three facility types (Clinic, Private Hospital and Warehouse) and six facilities of each type.

The Valid Sources table for these configuration is created below:

| facilityTypeCode | facilityCode | organizationName |
|------------------|--------------|------------------|
| privC            | FAC03        |                  |
| privH            | FAC03        |                  |
| privC            | FAC06        |                  |
| privH            | FAC06        |                  |

In the table there are warehouses’ facility codes (FAC03, FAC06) in the facilityCode column. It means that these facilities supply facilities of privC and privH facility types.

## Valid Destinations
Valid Destinations table consists of facilityTypeCode and destination columns.

In facilityTypeCode column there should be all codes of facility types which are able to supply other facilities.
In destination column there should be facility codes of facilities which are supplied by a facility of type indicated in facilityTypeCode column.

The Valid Destinations table for these configuration is created below:

| facilityTypeCode | destination |
|------------------|-------------|
| warehouse        | FAC01       |
| warehouse        | FAC02       |
| warehouse        | FAC04       |
| warehouse        | FAC05       |
| privC            | FAC01       |
| privC            | FAC04       |
| privH            | FAC02       |
| privH            | FAC05       |