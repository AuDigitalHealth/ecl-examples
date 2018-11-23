# SNOMED CT Expression Constraint Language (ECL)
The SNOMED CT Expression Constraint Language is a formal language for defining bounded sets of clinical meanings represented by either precoordinated or postcoordinated expressions (https://confluence.ihtsdotools.org/display/SLPG/SNOMED+CT+Expression+Constraint+Language).  The specification is published by SNOMED Internationally and allows for rich querying of SNOMED CT by allowing relationship traversal between concepts and refinement based on attributes. 

# ECL Examples
The aim of this repository is to provide a collection of SNOMED CT Expression Constraint Language (ECL) examples that have been compiled to assist users in writing ECL queries to perform common use cases (where help requests have been received by the Agency)

## Repo Structure
ECL examples for each SNOMED module have been put within their respective folder.
 - The [AMT](AMT/) folder within this repository contains ECL examples relating to the AMT concept model. 

# Getting started with ECL
The easiest way to get started using ECL is to use [OntoServer](http://ontoserver.csiro.au) and it's associated tooling.  Within Australia, OntoServer is provided free of charge to the broader healthcare industry as a result of a licencing agreement between the Australian Digital Health Agency and CSIRO.  OntoServer is a product of the Australian eHealth Research Centre (AEHRC), a division of the CSIRO, and is distributed as a Docker container. 

Part of the tooling for OntoServer is [Shrimp](http://ontoserver.csiro.au/shrimp/) which allows browsing through the various code systems within OntoServer.  Shrimp also contains an ECL builder which assists in the query-building process.  By default, Shrimp points to CSIRO's public OntoServer but can also be configured to point to a private server if you would like to run your own. 

## ECL Reference
There are a few ECL reference guides available online.  Shrimp has a concise ECL reference page that includes example queries as well as explanations relating to the operators and their use.  The guide can be access directly [here](https://ontoserver.csiro.au/shrimp/ecl_help.html)

## Executing ECL against OntoServer
OntoServer implements the [FHIR Terminology API](https://www.hl7.org/fhir/STU3/terminology-module.html).  An ECL query can be provided as a parameter to the _$expand_ function:

```
<<SERVER BASE URL>>/ValueSet/$expand?url=http://snomed.info/sct?fhir_vs=ecl/(<ECL QUERY>)
```
The full documentation for OntoServer's current API implementation is available via the [OntoServer documentation site](https://ontoserver.csiro.au/docs/).