### Semantic model figure

<p align="center">
    <a href="../images/rdf/1_Pseudonym.png" target="_blank">
        <img src="../images/rdf/1_Pseudonym.png">
    </a>
</p>

***

### Example rdf (turtle)

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix edam: <http://edamontology.org/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:person_ a sio:SIO_000498 ;
  sio:SIO_000228 :role_ .

:role_ a obo:OBI_0000093 .

:identifier_ a edam:data_0842 ;
  sio:SIO_000020 :role_ ;
  sio:SIO_000300 "1234567890"^^xsd:string .
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
PREFIX : <http://purl.org/ejp-rd/cde/v020/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/>
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX edam: <http://edamontology.org/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

:personShape IRI {
  a [sio:SIO_000498];
  sio:SIO_000228 @:personRoleShape
}

:personRoleShape IRI {
  a [obo:OBI_0000093]
}

:identifierShape IRI {
  a [edam:data_0842];
  sio:SIO_000020 @:personRoleShape;
  sio:SIO_000300 xsd:string
}
```