# TPP's from TP and Unit of Use
In this example, we will find all Trade Product Packs (_TPP_) from a Trade Product (_TP_) and a Unit of Use Quantity.

# Example
We would like to find all trade product packs for _Panadeine_ that have a size of _24_ units. 

```
(
 (^ 929360041000036105|Trade product pack reference set| : 700000101000036108|has TP| = 13481000168104|Panadeine|) 
 AND 
 (^ 929360041000036105|Trade product pack reference set| : 700000131000036101|UoU.Quantity.Refset|= #24)
)
```
The result of this query is formed from the intersection of two queries - the first query finds all members of the _TPP_ reference set that have the trade product _Panadeine_.  The second query finds all members of the _TPP_ refset that have a Unit of Use quantity of 24.

This would be easily modified to return CTPPs using the _Containered trade product pack reference set_ in the ECL instead of the _TPP_ reference set.
