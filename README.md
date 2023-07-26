# RMI Aluminum Emissions Reporting Guidance
This repository holds RMI's Aluminum Emissions Reporting Guidance, along with licensing and related documents.

## Product Level Accounting Guidance
The aluminum accounting guidance can be found [here:](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

### Emissions Reporting Requirements
There are four key requirements for reporting steel sector emissions using this Steel Emissions Reporting Guidance:

#### 1. Product level
Emissions must be reported at the product level for an individual site.

#### 2. Fixed boundary
All emissions from a set of processes must be reported irrespective of whether the company has
ownership or control of these processes.

#### 3. Supply chain transparency
Additional context about the scrap-based inputs, total carbon emissions intensity position relative to the 1.5C trajectory and abatement technology (refer to section 2.4 of the [accounting guidance](https://github.com/RMI/steel-guidance/blob/main/RMI%20Horizon%20Zero%20Steel%20Guidance.pdf)) to assist in understanding the overall emissions footprint.

## Pathfinder Network Data Model Extension
In addition to the Product Level Accounting Guidance, this repository contains supporting documents for a [Pathfinder Network](https://www.carbon-transparency.com/) Data Model Extension for Aluminum, which is designed to be used in concert with RMI's Aluminum Emissions Reporting Guidance.

The Pathfinder Data Model is designed to enable the use of machine-readable sharing of product level information. Extensions to the model allow for sector specific information to be added to the data model. Technical guidance on the Pathfinder Network data model can be found [here.](https://wbcsd.github.io/data-exchange-protocol/v2/)

### Key Terms
Some key terms for understanding the data model extension:

#### Benchmarking
  Emissions associated with all relevant processes from bauxite mining to final cast-house. For more information see Sec 2.2 Fixed System Boundary of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

#### Mine to Smelter
  The ore-based or mine-to-smelter portion of aluminum production. For more information, please refer Secs 2.3 and 3.2 of RMI's [Aluminum Emissions Reporting Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

#### Value Added Product
  Final cast-house products such as slabs, billets, foundry alloys, wire rods, and other specialty products. For more information, please refer to Sec 2.3 of RMI's [Aluminum Emissions Reporting Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)
  
#### Full Boundary
  Emissions associated with all relevant processes from bauxite mining to semi-fabrications. For more information see Sec 2.2 Fixed System Boundary of RMI's [Aluminum Emissions Reportings Guidance.](https://rmi.org/wp-content/uploads/dlm_uploads/2023/05/aluminum_guidance_public_consultation.pdf)

### Techical Guidance
For full techical guidance on RMI's Aluminum Data Model Extension, see [here.](https://github.com/RMI/aluminum-guidance/blob/main/specs/aluminum_technical_specification.md)

### Sample and Schema Files
A sample file of the data model extension can be found [here.](https://github.com/RMI/aluminum-guidance/blob/main/samples/aluminum_sample.json) Note: this sample file includes the required fields for the Pathfinder Data Model file as well as RMI's Aluminum Extension.

A json schema file for the data model extension can be found [here.](https://github.com/RMI/aluminum-guidance/blob/main/specs/aluminum_schema.json)

## Contacts

### RMI
For questions please contact ghgtransparency@rmi.org
