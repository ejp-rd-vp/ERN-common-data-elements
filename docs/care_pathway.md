### Semantic model figure

<p align="center">
    <a href="../images/rdf/4_Care_pathway.png" target="_blank">
        <img src="../images/rdf/4_Care_pathway.png">
    </a>
</p>



***

### Example RDF (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:person_ a sio:SIO_000498 ;
  sio:SIO_000228 :role_ .

:role_ a obo:OBI_0000093 ;
  sio:SIO_000356 :process_ .

:process_ a obo:NCIT_C142427, obo:NCIT_C159705, sio:SIO_000006 ;
    sio:SIO_000680 "2020-10-18T13:00:00"^^xsd:dateTime .
```

Mark's example

```ttl

@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

<http://example.org/process>
    sio:start-date "2020-10-18T13:00:00"^^<http://www.w3.org/2001/XMLSchema#dateTime> ;
    a obo:NCITC142427, obo:NCITC159705, sio:process .

obo:NCITC142427
    rdfs:label "clinical encounter"@en .

obo:NCITC159705
    rdfs:label "First confirmed visit"@en .

sio:process
    rdfs:label "process"@en .

```

***

### Validation artifacts 
##### ShEx figure

<p align="center">
    <a href="../images/shex/4_Care_pathway.png" target="_blank">
        <img src="../images/shex/4_Care_pathway.png">
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
  sio:SIO_000228 @:roleShape
}

:roleShape IRI {
  a [obo:OBI_0000093];
  sio:SIO_000356 @:processShape
}

:processShape IRI {
  a [sio:SIO_000006];
  a [obo:NCIT_C142427];
  a [obo:NCIT_C159705];
  sio:SIO_000680 xsd:dateTime
}
```
