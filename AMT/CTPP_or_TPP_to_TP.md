# CTPP/TPP to TP
In AMT, a Containerised Trade Product Pack (CTPP) is a concept inherits a _has TP_ relationship to a Trade Product concept from its parent Trade Product Pack (TPP) concept.

## Example - pack's Trade Product
In this example, we want to find the TP for _Panadeine Forte uncoated tablet, 20, blister pack_, which is _Panadeine Forte_. For any given pack (TPP or CTPP) there is exactly one TP identified by a _has TP_ relationship.

The ECL for that query would be:

```
836001000168100|Panadeine Forte uncoated tablet, 20, blister pack| . 700000101000036108 |has TP|
```
This ECL query finds all concepts that matches the attribute _700000101000036108|has TP|_ for each concept matching _836001000168100|Panadeine Forte uncoated tablet, 20, blister pack|_.

A _TPP_ can be substituted for the _CTPP_ and this query will work as a CTPP is a TPP.

## Example - pack's components' Trade Product(s)
The Trade Product concept(s) referenced by the Trade Product Unit of Use (TPUU) concept(s) contained in a TPP or CTPP may differ from the Trade Product referenced by its _has TP_ relationship. That is, a component in a pack (e.g. a tablet) may have a different Trade Product to a pack it is contained in.

A good example of this is _Nexium Hp7 (14 x Nexium tablets, 28 x Amoxil capsules, 14 x Klacid tablets), 1 pack_, where the pack's Trade Product is _Nexium Hp7_. However the CTPP subpacks it contains, and then the TPUUs contained within them have three different Trade Product parents, _Nexium_, _Amoxil_, and _Klacid_.

```
>> (21062011000036103 | Nexium Hp7 (14 x Nexium tablets, 28 x Amoxil capsules, 14 x Klacid tablets), 1 pack | . 30409011000036107 | has TPUU |) AND ^ 929360021000036102 | Trade product reference set |
```
This ECL query finds all ancestor concepts of the TPUUs referenced by _Nexium Hp7 (14 x Nexium tablets, 28 x Amoxil capsules, 14 x Klacid tablets), 1 pack_, and filters that set to only those concepts that are Trade Products using the _Trade product reference set_

Similarly a _TPP_ can be substituted for the _CTPP_ in this query and it will function as expected.
