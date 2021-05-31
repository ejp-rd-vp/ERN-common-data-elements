
# Semantic data model of the set of common data elements for rare disease registration
![GitHub](https://img.shields.io/github/license/ejp-rd-vp/CDE-semantic-model)
![GitHub tag (latest by date)](https://img.shields.io/github/v/tag/ejp-rd-vp/CDE-semantic-model)

> To make rare disease registry data Interoperable (the <b>I</b> in FAIR).

In this work we present a semantic data model for [the set of common data elements for rare diseases registration](https://eu-rd-platform.jrc.ec.europa.eu/sites/default/files/CDS/EU_RD_Platform_CDS_Final.pdf) recommended by the European commission Joint Research Centre. There are 16 data elements: ‘Pseudonym’, ‘Date of Birth’, ‘Sex’, ‘Patient’s status’, ‘Date of death’, ‘First contact with specialised centre’, ‘Age at onset’, Age at diagnosis’, ‘Diagnosis of the rare disease’, ‘Genetic diagnosis’, ‘Undiagnosed case’, ‘Agreement to be contacted for research purposes’, ‘Consent to the reuse of data’, ’Biological sample’, ‘Link to a biobank’, ‘Classification of functioning/disability’. We proposed a sematic data model for each of these data elements.

## CDE modules overview

The figure below gives an overview of upper level concepts and properties used in our cde models.

<p align="center"> 
	<img src="images/rdf/Annotated General model SIO.png"> 
</p> 

You can browse different CDE modules by visiting the links below.

* [Pseudonym](docs/pseudonym.md) - describes pseudonym ID
* [Personal information](docs/personal_information.md) - describes personal information of a subject
* [Patient status](docs/patient_status.md) - describes patient's status
* [Care pathway](docs/care_pathway.md) - describes care pathway
* [Disease history and diagnosis](docs/disease_history_and_diagnosis.md) - describes disease history and diagnosis of a subject
* [Genetic diagnosis](docs/genetic_diagnosis.md) - describes genetic diagnosis of a subject
* [Undiagnosed](docs/undiagnosed.md) - describes undiagnosed subjects
* [Consent](docs/Consent.md) - describes consent given by a subject
* [Biobanks](docs/biobanks.md) - describes availability of subject's samples in a biobank
* [Disability](docs/disability.md) - describes disability score of a subject

## Acknowledgement
This work is funded by [European Joint Programme on Rare Diseases (EJP RD)](https://www.ejprarediseases.org/)