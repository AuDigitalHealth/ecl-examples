# Retreive the MPUU for a given TPUU

This example shows how to find the corresponding Medicinal Product Unit of Use (_MPUU_) concept for a given Trade Product Unit of Use (_TPUU_). To retreive all the immediate parents for a concpet the **>!** `ParentOf` function.

# Example - All parents of a concept
```
>!1109861000168100|Calcium 600 mg plus Vitamin D3 1000 IU (Health Plus Vitamins) film-coated tablet|
```
Returns 3 concepts:
* 1109771000168103	Calcium 600 mg plus Vitamin D3 1000 IU (Health Plus Vitamins) (trade product)
* 30425011000036101	trade product unit of use (trade product unit of use)
* 1109851000168102	calcium carbonate 1.5 g + colecalciferol 25 microgram tablet (medicinal product unit of use)

Every TPUU in AMT has 3 supertype concepts.

# Example - Only the MPUU parent
To limit the set of parents returned to just the MPUU use **^** `MemberOf` function.

```
>!1109861000168100|Calcium 600 mg plus Vitamin D3 1000 IU (Health Plus Vitamins) film-coated tablet|
AND ^929360071000036103|MPUU reference set|
```
Every TPUU in AMT has exactly 1 immediate MPUU parent.
