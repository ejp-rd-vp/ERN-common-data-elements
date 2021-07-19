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
PREFIX : <http://purl.org/ejp-rd/cde/v1/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/> 
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

:identifierShape IRI {
    a [sio:SIO_000115] ;
    rdfs:label xsd:string? ;
    sio:SIO_000020 @:statusRoleShape ;
    sio:SIO_000300 xsd:string
}

:personShape IRI { 
    a [sio:SIO_000498] ;
    rdfs:label xsd:string? ;
    sio:SIO_000228 @:statusRoleShape ;
    sio:SIO_000008 @:statusAttributeShape ;
    sio:SIO_000008 @:deadDateAttributeShape
}

:statusRoleShape IRI {
    a [obo:OBI_0000093] ;
    a [sio:SIO_000016] ;
    rdfs:label xsd:string? ;
    sio:SIO_000356 @:statusProcessShape ;
    sio:SIO_000356 @:deadDateProcessShape
}

:statusProcessShape IRI {
    a [sio:SIO_000006] ;
    a [sio:SIO_001052] ;
    rdfs:label xsd:string? ;
    sio:SIO_000229 @:statusOutputShape
}

:statusOutputShape IRI {
    a [sio:SIO_000015] ;
    rdfs:label xsd:string? ;
    sio:SIO_000300 xsd:string ;
    sio:SIO_000628 @:statusAttributeShape
}

:statusAttributeShape IRI {
    a [sio:SIO_000614] ;
    a [sio:SIO_010059 sio:SIO_010058 obo:NCIT_C70740 obo:NCIT_C124784] ;
    rdfs:label xsd:string?   
}

:deadDateProcessShape IRI {
    a [sio:SIO_000006] ;
    rdfs:label xsd:string? ;
    sio:SIO_000680 @:deathDateStartDateShape ;
    sio:SIO_000229 @:deadDateOutputShape
}

:deadDateOutputShape IRI {
    a [sio:SIO_000015] ;
    rdfs:label xsd:string? ;
    sio:SIO_000300 xsd:date ;
    sio:SIO_000628 @:deadDateAttributeShape
}

:deadDateAttributeShape IRI {
    a [sio:SIO_000614] ;
    a [obo:NCIT_C70810] ;
    rdfs:label xsd:string? 
}

:deathDateStartDateShape IRI {
    a [sio:SIO_000031] ;
    rdfs:label xsd:string? ;
    sio:SIO_000300 xsd:date
}
```


