### Semantic model figure

This module describes the data elements in the module 'Patient's status'. It specifically covers the CDE elements 3.1.'Patient's status' and 3.2.'Date of death'. 
These elements, defined by the JRC, can be found on the EU RD Platform at [this link](https://eu-rd-platform.jrc.ec.europa.eu/sites/default/files/CDS/EU_RD_Platform_CDS_Final.pdf).

<p align="center">
    <a href="../images/rdf/3_Patient_status.png" target="_blank">
        <img src="../images/rdf/3_Patient_status.png">
    </a>
</p>


***

### Example RDF (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v1/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

:identifier_ a sio:SIO_000115 ;
    sio:SIO_000020 :status_role_ ;
    sio:SIO_000300 "uid_000008"^^xsd:string .

:person_ a sio:SIO_000498;
    sio:SIO_000228 :status_role_ ;
    sio:SIO_000008 :status_attribute_ ;
    sio:SIO_000008 :death_information_attribute_ .

:status_role_  a obo:OBI_0000093, sio:SIO_000016;
    rdfs:label "Patient for status recording"^^xsd:string;
    sio:SIO_000356 :status_process_ ;
    sio:SIO_000356 :death_information_process_ .

:status_process_ a sio:SIO_000006, sio:SIO_001052 ;
    rdfs:label "status process"^^xsd:string ;
    sio:SIO_000229 :status_output_ .

:status_output_ a sio:SIO_000015;
    rdfs:label "dead"^^xsd:string ;
    sio:SIO_000300 "dead"^^xsd:string ;
    sio:SIO_000628 :status_attribute_ .

:status_attribute_ a sio:SIO_000614, sio:SIO_010059 ;
    rdfs:label "Patient status"^^xsd:string .

:death_information_process_ a sio:SIO_000006 ;
    rdfs:label "death information recording process"^^xsd:string;
    sio:SIO_000680 :death_information_startdate_ ;
    sio:SIO_000229 :death_information_output_ .

:death_information_output_ a sio:SIO_000015;
    rdfs:label "patient death information"^^xsd:string ;
    sio:SIO_000300 "2010-06-08"^^xsd:date ;
    sio:SIO_000628 :death_information_attribute_ .

:death_information_attribute_ a sio:SIO_000614, obo:NCIT_C70810 ;
    rdfs:label "Date of death"^^xsd:string .

:death_information_startdate_ a sio:SIO_000031 ;
    sio:SIO_000300 "2010-06-09"^^xsd:date .
```

***

### Validation artifacts 
##### ShEx figure

<p align="center">
    <a href="../images/shex/3_Patient_status.png" target="_blank">
        <img src="../images/shex/3_Patient_status.png">
    </a>
</p>

***


##### ShEx


``` ShEx
TODO
```


