### Semantic model figure

<p align="center">
    <a href="../images/rdf/6_Genetic_diagnosis.png" target="_blank">
        <img src="../images/rdf/6_Genetic_diagnosis.png">
    </a>
</p>


***
### Example RDF (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

:process_ a obo:NCIT_C15709 ;
    sio:SIO_000229 :variant_ .

:person_ a sio:SIO_000498 ;
    sio:SIO_000228 :role_ .

:role_ a obo:OBI_0000093 ;
    sio:SIO_000356 :process_ .

:variant_ a obo:VariO_0138;
    rdfs:label "NG_007148.2:g.146889G>A" . 
```

Mark's example

```ttl
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix dbsnp: <http://identifiers.org/dbsnp:> .
@prefix hgnc: <https://identifiers.org/hgnc:> .
@prefix bioass: <http://www.bioassayontology.org/bao#> .
@prefix rdcmeta: <http://rdf.biosemantics.org/ontologies/rd-connect/> .
@prefix ex: <http://example.org/> .

ex:geneX
    sio:has-role ex:generole ;
    a obo:NCIT_C16612 .

ex:generole
    sio:is-realized-in ex:geneticdiagnosticprocess ;
    a sio:role, bioass:BAO_0003064 ;
    rdfs:label "Target gene role" .

ex:geneticdiagnosticprocess
    sio:has-output :variant_ ;
    sio:start-date "2020-10-18T13:00:00"^^<http://www.w3.org/2001/XMLSchema#dateTime> ;
    a obo:NCIT_C15709 ;
    rdfs:label "genetic diagnostic process" .

:variant_ sio:SIO_000339 dbsnp:rs121909098 . # is specified by

ex:patientID
    sio:denotes ex:patientrole ;
    sio:has-value "123456"^^<http://www.w3.org/2001/XMLSchema#int> ;
    a rdcmeta:Pseudonym, sio:identifier ;
    rdfs:label "123456" .

ex:patientX
    obo:RO_0002162 ex:patienttaxon ;
    sio:has-role ex:patientrole ;
    a sio:patient .

ex:patientrole
    sio:is-realized-in ex:geneticdiagnosticprocess ;
    a sio:patient-role, sio:role ;
    rdfs:label "Patient role" .

ex:patienttaxon
    a obo:NCBITaxon_9606 ;
    rdfs:label "some taxon" .

#dbsnp:rs121909098
#    a obo:SO_0000694, obo:VariO_0138 ;
#    rdfs:label "rs121909098" .

obo:NCBITaxon_9606
    rdfs:label "Homo sapiens" .

obo:NCIT_C15709
    rdfs:label "Genetic Testing" .

obo:NCIT_C16612
    rdfs:label "Gene" .

obo:NCIT_C48664
    rdfs:label "Gene Identifier" .

obo:SO_0000694
    rdfs:label "SNP" .

obo:VariO_0138
    rdfs:label "Variant" .

rdcmeta:Pseudonym
    rdfs:label "Pseudonym" .

sio:identifier
    rdfs:label "identifier" .

sio:patient
    rdfs:label "Patient" .

sio:patient-role
    rdfs:label "Patient role" .

sio:role
    rdfs:label "Role" .

bioass:BAO_0003064
    rdfs:label "Target" .

<https://identifiers.org/hgnc:2928>
    sio:denotes ex:generole ;
    sio:has-value "HGNC 2928"@en ;
    a obo:NCIT_C48664, sio:identifier ;
    rdfs:label "HGNC:2928" .
```

### Validation artifacts 

##### ShEx figure

<p align="center">
    <a href="../images/shex/6_Genetic_diagnosis.png" target="_blank">
        <img src="../images/shex/6_Genetic_diagnosis.png">
    </a>
</p>


***

##### ShEx

``` ShEx
PREFIX : <http://purl.org/ejp-rd/cde/v020/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/> 
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

:processShape IRI { 
  a [obo:NCIT_C15709] ;
  sio:SIO_000229 @:variantShape 
}

:personShape IRI { 
  a [sio:SIO_000498] ;
  sio:SIO_000228 @:roleShape 
}

:roleShape IRI {
  a [obo:OBI_0000093] ;
  sio:SIO_000356 @:processShape
}

:variantShape IRI {
  a [obo:VariO_0138] ;
  rdfs:label xsd:string
}
```
