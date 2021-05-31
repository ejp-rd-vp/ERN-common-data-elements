### Semantic model figure

<p align="center">
    <a href="../images/rdf/8_Consent.png" target="_blank">
        <img src="../images/rdf/8_Consent.png">
    </a>
</p>


***
### Example rdf (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:person_ a sio:SIO_000498 ;
    sio:SIO_000228 :role_1, :role_2 .

:role_1 a obo:OBI_0000093 ;
    sio:SIO_000356 :process_1 .

:process_1 a obo:ICO_0000149 ;
    sio:SIO_000229 :output_1 ;
    sio:SIO_000680 "2020-10-18T13:00:00"^^xsd:dateTime .    
    
:role_2 a obo:OBI_0000093 ;
    sio:SIO_000356 :process_2 .

:process_2 a obo:ICO_0000181 ;
    sio:SIO_000229 :output_2 ;
    sio:SIO_000680 "2020-10-18T13:03:00"^^xsd:dateTime .
    
:output_1 a sio:SIO_000340, obo:OPMI_0000023 .

:output_2 a sio:SIO_000340, obo:OPMI_0000024 .
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

ex:consentingprocess
    sio:has-output <http://example.org/my_consent_document.pdf> ;
    sio:000680 "2020-10-18T13:00:00"^^<http://www.w3.org/2001/XMLSchema#dateTime> ;  # has start time
    a obo:ICO_0000196 ;
    rdfs:label "Consenting process" .

<http://example.org/my_consent_document.pdf>
    a obo:OBIB_0000488 ;
    rdfs:label "Consent Document" .

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
    sio:is-realized-in ex:consentingprocess ;
    a sio:patient-role, sio:role ;
    rdfs:label "Patient role" .

ex:patienttaxon
    a obo:NCBITaxon_9606 ;
    rdfs:label "some taxon" .

obo:ICO_0000196
    rdfs:label "Act of informed consenting" .

obo:NCBITaxon_9606
    rdfs:label "Homo sapiens" .

obo:OBIB_0000488
    rdfs:label "Willingness to be contacted for a research study" .

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
```

### Validation artifacts 
##### ShEx figure

<p align="center">
    <a href="../images/shex/8_Consent.png" target="_blank">
        <img src="../images/shex/8_Consent.png">
    </a>
</p>


***
##### ShEx
``` ShEx
PREFIX : <http://purl.org/ejp-rd/cde/v020/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/> 
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

:personShape IRI { 
  a [sio:SIO_000498];
  sio:SIO_000228 @:roleShape+
}

:roleShape IRI {
  a [obo:OBI_0000093];
  sio:SIO_000356 @:processShape
}

:processShape IRI {
  a [obo:ICO_0000149 obo:ICO_0000181];
  sio:SIO_000680 xsd:dateTime;
  sio:SIO_000229 @:outputShape
}

:outputShape IRI {
  a [sio:SIO_000340];
  a [obo:OPMI_0000023 obo:OPMI_0000024]
}
```

