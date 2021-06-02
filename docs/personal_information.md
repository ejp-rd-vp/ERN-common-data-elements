### Semantic model figure

<p align="center">
    <a href="../images/rdf/2_Personal_information.png" target="_blank">
        <img src="../images/rdf/2_Personal_information.png">
    </a>
</p>


***

### Example RDF (turtle)

An example RDF of person's birthdate

```ttl
@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

:person_ a sio:SIO_000498 ; # person
  sio:SIO_000228 :role_ ; # has role
  sio:SIO_000217 :quality_ . # has quality

:quality_ a obo:NCIT_C68615 ; # Birth Date
  sio:SIO_000642  :output_ . # is base for

:role_ a obo:OBI_0000093 ; # patient role
  sio:SIO_000356 :process_ . # is realized in

:process_ a sio:SIO_000006 ; # process
  sio:SIO_000229 :output_ . # has output

:output_ a sio:SIO_000340 ; # realizable entity
  sio:SIO_000300 "2020-02-31T12:00:00"^^xsd:dateTime . # has value
```

An example RDF of person's gender

```ttl

@prefix : <http://purl.org/ejp-rd/cde/v020/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix snomedct: <http://purl.bioontology.org/ontology/SNOMEDCT/> .

:person_ a sio:SIO_000498 ; # sio:person
  sio:SIO_000228 :role_ ; # sio:has role
  sio:SIO_000217 :quality_ . # sio:has quality

:role_ a obo:OBI_0000093 ; # obo:patient role
  sio:SIO_000356 :process_ . # sio:is realized in

:quality_ a obo:NCIT_C17357 ; # obo:Gender
  sio:SIO_000642 :output_ . # sio:is base for

:process_ a sio:SIO_000006 ; # sio:process
  sio:SIO_000229 :output_ . # sio:has output

:output_ a sio:SIO_000340, snomedct:703118005 . # sio:realizable entity, snomedct:Feminine gender
```

***

### Validation artifacts 
##### ShEx figure

Date of birth

<p align="center">
    <a href="../images/shex/2_Personal_information_birthdate.png" target="_blank">
        <img src="../images/shex/2_Personal_information_birthdate.png">
    </a>
</p>

***
Gender

<p align="center">
    <a href="../images/shex/2_Personal_information_gender.png" target="_blank">
        <img src="../images/shex/2_Personal_information_gender.png">
    </a>
</p>


***

##### ShEx
Date of birth

```
PREFIX : <http://purl.org/ejp-rd/cde/v020/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/>
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

:personShape IRI {
  a [sio:SIO_000498];
  sio:SIO_000228 @:personRoleShape;
  sio:SIO_000217 @:birthDateQualityShape
}

:personRoleShape IRI {
  a [obo:OBI_0000093];
  sio:SIO_000356 @:birthDateProcessShape
}

:birthDateProcessShape IRI {
  a [sio:SIO_000006];
  sio:SIO_000229 @:birthDateOutputShape
}

:birthDateQualityShape IRI {
  a [obo:NCIT_C68615];
  sio:SIO_000642 @:birthDateOutputShape
}

:birthDateOutputShape IRI {
  a [sio:SIO_000340];
  sio:SIO_000300 xsd:dateTime
}
```

Gender

```
PREFIX : <http://purl.org/ejp-rd/cde/v020/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/>
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX snomedct: <http://purl.bioontology.org/ontology/SNOMEDCT/>

:personShape IRI {
  a [sio:SIO_000498];
  sio:SIO_000228 @:personRoleShape;
  sio:SIO_000217 @:genderQualityShape
}

:personRoleShape IRI {
  a [obo:OBI_0000093];
  sio:SIO_000356 @:genderProcessShape
}

:genderQualityShape IRI {
  a [obo:NCIT_C17357];
  sio:SIO_000642 @:genderOutputShape
}

:genderProcessShape IRI {
  a [sio:SIO_000006];
  sio:SIO_000229 @:genderOutputShape
}

:genderOutputShape IRI {
  a [sio:SIO_000340];
  a [snomedct:703118005 snomedct:394743007 snomedct:394744001 snomedct:703117000]
}
```
