# CTPP/TPP to TP
In accordance to the AMT model, a Containerised Trade Product Pack (CTPP) is a Trade Product Pack (TPP) but in order to deduce the Trade Product (TP), the _has TP_ relationship has to be traversed.

## Example
In this example, we want to find the TP for _Panadeine Forte uncoated tablet, 20, blister pack_, which is _Panadeine Forte_.

The ECL for that query would be:

```
836001000168100|Panadeine Forte uncoated tablet, 20, blister pack| . 700000101000036108 |has TP|
```
This ECL query finds all concepts that matches the attribute _700000101000036108|has TP|_ for each concept matching _836001000168100|Panadeine Forte uncoated tablet, 20, blister pack|_.

A _TPP_ can be substituted for the _CTPP_ and this query will work as a CTPP is a TPP. 
