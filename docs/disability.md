### Semantic model figure

This module describes the data element 8.1'Classification of functioning/disability' which is part of the group 'Disability'. These elements, defined by the JRC, can be found on the EU RD Platform at [this link](https://eu-rd-platform.jrc.ec.europa.eu/sites/default/files/CDS/EU_RD_Platform_CDS_Final.pdf).

<p align="center">
    <a href="../images/rdf/10_Disability.png" target="_blank">
        <img src="../images/rdf/10_Disability.png">
    </a>
</p>


***

### Example RDF (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v1/example-rdf/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

:identifier_ a sio:SIO_000115 ;
    sio:SIO_000020 :disability_role_ ;
    sio:SIO_000300 "uid_000008"^^xsd:string .

:person_ a sio:SIO_000498 ;
    sio:SIO_000228 :disability_role_ .

:disability_role_ a obo:OBI_0000093, sio:SIO_000016 ;
   rdfs:label "Patient"^^xsd:string ;
   sio:SIO_000356 :assessment_test_ .

:assessment_test_ a sio:SIO_000006, obo:NCIT_C20993, obo:NCIT_C1212693 ;
   rdfs:label "Behavior Assessment system for Children"^^xsd:string ;
   sio:SIO_000680 :disability_startdate_ ;
   sio:SIO_000230 :question_answering_input_ ;
   sio:SIO_000229 :test_output_ .

:test_output_ a sio:SIO_000015 ;
    rdfs:label "disability score"^^xsd:string ;
    sio:SIO_000300 "3"^^xsd:string .

:question_answering_input_ a sio:SIO_000015, obo:NCIT_C17048 ;
    rdfs:label "information content entity"^^xsd:string .

:disability_startdate_ a sio:SIO_000031 ;
    sio:SIO_000300 "2010-04-06"^^xsd:date .
```

***

### Validation artifacts 
##### ShEx figure

<p align="center">
    <a href="../images/shex/10_Disability.svg" target="_blank">
        <img src="../images/shex/10_Disability.svg">
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
    sio:SIO_000020 @:disabilityRoleShape ;
    sio:SIO_000300 xsd:string
}

:personShape IRI { 
  a [sio:SIO_000498] ;
  rdfs:label xsd:string? ;
  sio:SIO_000228 @:disabilityRoleShape
}

:disabilityRoleShape IRI {
  a [obo:OBI_0000093] ;
  a [sio:SIO_000016] ;
  rdfs:label xsd:string? ;
  sio:SIO_000356 @:disabilityProcessShape
}

:disabilityProcessShape IRI {
  a [sio:SIO_000006] ;
  a [obo:NCIT_C20993] ;
  a IRI /^http:\/\/purl.obolibrary.org\/obo\// ;
  rdfs:label xsd:string? ;
  sio:SIO_000680 @:disabilityStartDateShape ;
  sio:SIO_000230 @:questionInputShape ;
  sio:SIO_000229 @:testOutputShape
}

:testOutputShape IRI {
  a [sio:SIO_000015] ;
  rdfs:label xsd:string? ;
  sio:SIO_000300 xsd:string
}

:questionInputShape IRI {
  a [sio:SIO_000015] ;
  a [obo:NCIT_C17048] ;
  rdfs:label xsd:string? 
}

:disabilityStartDateShape IRI {
    a [sio:SIO_000031] ;
    rdfs:label xsd:string? ;
    sio:SIO_000300 xsd:date
}
```
