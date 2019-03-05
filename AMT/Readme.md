# Australian Medicines Terminology (AMT)
The Australian Medicines Terminology is a SNOMED CT module created by the Australian Digital Health Agency that has been developed to unambiguously identify commonly used medicines for the treatment of human patients in Australia. The AMT, in conjunction with other products such as other terminologies, classifications and decision support engines, can be used to deliver various aspects of electronic medications management. The AMT can be implemented in clinical information systems to support the following activities:
 - Prescribe
 - Record
 - Review
 - Issue - including dispense
 - Administer
 - Transfer of information

National eHealth specifications also support the use of the AMT to describe medicines in the following clinical documents:
 - Prescription Record
 - Dispense Record
 - Shared Health Summary
 - Discharge Summary
 - Event Summary
 - eReferral
 - Specialist Letter

## Seven notable concepts
A substantial part of the AMT model comprises seven product classes, also known as the “seven notable concepts”, namely:
 - |Medicinal product| (MP)
 - |Medicinal product unit of use| (MPUU)
 - |Medicinal product pack| (MPP)
 - |Trade product| (TP)
 - |Trade product unit of use| (TPUU)
 - |Trade product pack| (TPP)
 - |Containered trade product pack| (CTPP)

These classes group concepts representing different abstractions of branded products and their generic product equivalents at various levels of granularity.
Classes prefixed with or containing the word “Trade” describe branded products, while classes with a prefix of “Medicinal” represent abstract products or the generic equivalent of branded products.

## Concept Model
The concept model for AMT can be downloaded directly from the [National Clinical Terminology Service website](https://www.healthterminologies.gov.au/docs/DH_2542_2017_AMT_Concept_Model_and_Business_Use_Cases_v2.1.pdf)

### Examples of concepts
 - MP -> amoxicillin
 - MPUU -> amoxicillin 500mg capsule
 - MPP -> amoxicillin 500mg capsule, 20
 - TP -> Amoxil
 - TPUU -> Amoxil 500mg hard capsule
 - TPP -> Amoxil 500mg hard capsule, 20
 - CTPP -> Amoxil 500mg hard capsule, 20, blister pack

## Traversing the model with ECL
ECL can be used to traverse the relationships between the seven notable concepts to allow, for example, the Medicinal Product (MP) to be found for a given Containerised Trade Product Pack (CTPP) (ie. amoxicillin is the medicinal product form of Amoxil 500mg hard capsule, 20, blister pack).  In addition to traversing between the seven notable concepts, ECL can also be used to query concepts based on attributes and relationships such as unit of use, manufactured dose form, intended active ingredient, container type and many others (see the concept model for the full list).
 
## ECL examples
 - [CTPP search by ingredient](CTPP_ingredient_search.md)
 - [Navigating to TP from CTPP or TPP](CTPP_or_TPP_to_TP.md)
 - [Retreive the MPUU for a given TPUU](MPUU for TPUU.md)
 - [MPUU search by ingredient, form, dose](MPUU_ingredient_qty_search.md)
 - [Retrive TPPs from TP and Unit of Use Quantity]
 - [Navigate from TPUU to MP](TPUU_to_MP.md)
