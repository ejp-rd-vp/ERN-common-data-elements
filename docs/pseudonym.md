### Semantic model figure

This module describes the data element pseudonym which is CDE 1.1'Pseudonym'.
These elements, defined by the JRC, can be found on the EU RD Platform at [this link](https://eu-rd-platform.jrc.ec.europa.eu/sites/default/files/CDS/EU_RD_Platform_CDS_Final.pdf). 

<p align="center">
    <a href="../images/rdf/1_Pseudonym.png" target="_blank">
        <img src="../images/rdf/1_Pseudonym.png">
    </a>
</p>

***

### Example RDF (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v1/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:person_ a sio:SIO_000498 ;
  sio:SIO_000228 :role_ .

:role_ a obo:OBI_0000093 .

:identifier_ a sio:SIO_000115 ; 
  sio:SIO_000020 :role_ ;
  sio:SIO_000300 "uid_000008"^^xsd:string .
```

***
### Validation artifacts 
##### ShEx figure

<p align="center">
    <a href="../images/shex/1_Pseudonym.png" target="_blank">
        <img src="../images/shex/1_Pseudonym.png">
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

:personShape IRI {
  a [sio:SIO_000498] ;
  rdfs:label xsd:string? ;
  sio:SIO_000228 @:personRoleShape
}

:personRoleShape IRI {
  rdfs:label xsd:string? ;
  a [obo:OBI_0000093]
}

:identifierShape IRI {
  a [sio:SIO_000115] ;
  rdfs:label xsd:string? ;
  sio:SIO_000020 @:personRoleShape ;
  sio:SIO_000300 xsd:string
}
```