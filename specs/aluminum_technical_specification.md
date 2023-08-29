# Technical Specifications for RMI Aluminum PCF Data Exchange
## Updated 17 August 2023

-------------------------
## 1. Introduction
This document contains the necessary technical foundation for an aluminum data model extension to the [Pathfinder Network,](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network) developed by [RMI.](https://rmi.org/) For full documentation of the Pathfinder Network, refer to the link above.

The goal of this document is to enable the interoperable exchange of aluminum Product Carbon Footprints, in accordance with the RMI's
[Aluminum Emissions Reporting Guidance](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)
, across conforming host systems.

## 2. Terminology
For a full list of terminology, please refer to the [Terminology](https://wbcsd.github.io/data-exchange-protocol/v2/#terminology) section of the Pathfinder techical specification.

### Benchmarking
  Emissions associated with all relevant processes from bauxite mining to final cast-house. For more information see Sec 2.2 Fixed System Boundary of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

### Mine to Smelter
  The ore-based or mine-to-smelter portion of aluminum production. For more information, please refer Secs 2.3 and 3.2 of RMI's [Aluminum Emissions Reporting Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

### Value Added Product
  Final cast-house products such as slabs, billets, foundry alloys, wire rods, and other specialty products. For more information, please refer to Sec 2.3 of RMI's [Aluminum Emissions Reporting Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)
  
### Full Boundary
  Emissions associated with all relevant processes from bauxite mining to semi-fabrications. For more information see Sec 2.2 Fixed System Boundary of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

## 3. Conformance
For conformance with the Pathfinder Network, please refer to the [Conformance](https://wbcsd.github.io/data-exchange-protocol/v2/#conformance) section of the Pathfinder technical specification.

## 4. Data Model Extension
This section specifices a [data model extension](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-datamodelextension) for steel product footprints conforming with the [Pathfinder Network.](https://wbcsd.github.io/data-exchange-protocol/v2/#pathfinder-network)

The data model extension contains additional information for aluminum products, beyond what is specified in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#data-model)

The data model extension consists of the following:

1. BenchmarkingFootprint: Contains information related to the benchmarking boundary.
2. FullFootprint: Contains information related to the full boundary.

### 4.1. Data Type: BenchmarkingFootprint
Contains information related to the benchmarking boundary.

#### 4.1.1. Properties
The properties of a BenchmarkingFootprint are listed in the table below.

| **Property**                              | **Type**  | **Req** | **Specification**                                                               |
|-------------------------------------------|-----------|---------|---------------------------------------------------------------------------------|
| referencePeriodStart                      | date-time | O       | Start date-time for the benchmarking footprint <br>calculation                  |
| referencePeriodEnd                        | date-time | O       | End date-time for the benchmarking footprint<br>calculation                     |
| mineToSmelter:<br>_mineToSmelter_         | Object    | M       | Contains information related to the production of <br>primary aluminum          |
| valueAddedProduct:<br>_valueAddedProduct_ | Object    | O       | Contains information related to the production of <br>final cast-house products |

### 4.2. Data Type: MineToSmelter
Contains information related to the production of primary aluminum. For more information see Sec 3.3.2 of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

#### 4.2.1. Properties
The properties of a MineToSmelter are listed in the table below.

| **Property**                     | **Type** | **Req** | **Specification**                                                                                                            |
|----------------------------------|----------|---------|------------------------------------------------------------------------------------------------------------------------------|
| productDescription               | String   | O       | The free-form description of the product plus other<br>information related to it such as production technology or packaging. |
| productAmount                    | Number   | O       | The unit of analysis of the product                                                                                          |
| productDeclaredUnit              | String   | O       | The amount of productDeclaredUnits contained within the product                                                              |
| mineToSmelterGhgEmissions        | Number   | M       | The emissions intensity for primary aluminum, in ton C02e per ton of <br>primary aluminum                                    |
| geographyCountrySubdivision      | String   | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                |
| goegraphyCountry:<br>_ISO3166CC_ | String   | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                |
| geographyRegionOrSubregion       | String   | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                |
### 4.3. Data Type: ValueAddedProduct
Contains information related to the production of final cast-house products. For more information see Sec 3.3.3 of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

#### 4.3.1. Properties
The properties of a ValueAddedProduct are listed in the table below.

| **Property**                              | **Type** | **Req** | **Specification**                                                                                                                                                    |
|-------------------------------------------|----------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| productDescription                        | String   | O       | The free-form description of the product plus other<br>information related to it such as production technology or packaging.                                         |
| productAmount                             | Number   | O       | The unit of analysis of the product                                                                                                                                  |
| productDeclaredUnit                       | String   | O       | The amount of productDeclaredUnits contained within the product                                                                                                      |
| ghgEmissionsCutoff                        | Number   | M       | The overall emissions footprint for the aluminum product as per the<br>benchmarking footprint, using the cut-off method, in ton CO2e per ton<br>of aluminum semis    |
| ghgEmissionsAllocation                    | Number   | M       | The overall emissions footprint for the aluminum product as per the<br>benchmarking footprint, using the allocation method, in ton CO2e per ton<br>of aluminum semis |
| scrapBasedShare:<br>_Percent_             | Number   | M       | The share of scrap-based input used to generate the product as per the<br>benchmarking boundary                                                                      |
| postConsumerScrapBasedShare:<br>_Percent_ | Number   | O       | The share of post-consumer scrap used to generate the product as per the<br>benchmarking boundary                                                                    |

### 4.4. Data Type: FullBoundary
A geographical field for the ore-based or mine-to-smelter portion of the aluminum production. The requirements for this field corresponds to the GeographyCountry field in the [Pathfinder Data Model.](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)

#### 4.4.1. Properties
The properties of a FullBoundary are listed in the table below.

| **Property**                     | **Type**  | **Req** | **Specification**                                                                                                                                                     |
|----------------------------------|-----------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| referencePeriodStart             | date-time | O       | Start date-time for the full boundary footprint calculation                                                                                                           |
| referencePeriodEnd               | date-time | O       | End date-time for the full boundary footprint calculation                                                                                                             |
| productDescription               | String    | O       | The free-form description of the product plus other<br>information related to it such as production technology or packaging.                                          |
| productAmount                    | Number    | O       | The unit of analysis of the product                                                                                                                                   |
| productDeclaredUnit              | String    | O       | The amount of productDeclaredUnits contained within the product                                                                                                       |
| ghgEmissionsCutoff               | Number    | M       | The overall emissions footprint for the aluminum product as per the<br>full reporting boundary, using the cut-off method, in ton CO2e per ton<br>of aluminum semis    |
| ghgEmissionsAllocation           | Number    | M       | The overall emissions footprint for the aluminum product as per the<br>full reporting boundary, using the allocation method, in ton CO2e per ton<br>of aluminum semis |
| geographyCountrySubdivision      | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                                                         |
| geographyCountry:<br>_ISO3166CC_ | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                                                         |
| geographyRegionOrSubregion       | String    | O       | See [Pathfinder Data Model](https://wbcsd.github.io/data-exchange-protocol/v2/#dt-carbonfootprint-properties)                                                         |
