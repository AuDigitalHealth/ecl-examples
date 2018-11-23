# TPUU to MP
In accordance to the AMT model, to deduce the Medicinal Product (_MP_) from the Trade Product Unit of Use (_TPUU_), simple heirarchial traversal is needed.

## Example
For example, we want to find that _paracetamol + codeine_ is the Medicinal Product of _Rapideine uncoated tablet_.

```
((>> 54016011000036103|Rapideine uncoated tablet| AND ^ 929360061000036106|Medicinal product reference set|)
MINUS
(>(>> 54016011000036103|Rapideine uncoated tablet| AND ^ 929360061000036106| Medicinal product reference set |)))
```

In this example, _Rapideine_ is a multi-component substance and contains paracetamol and codeine.  The first query returns all ancestors of _Rapideine uncoated tablet_ that are members of the _MP_ reference set.  The issue with simply executing thie query is that in addition to _paracetamol+codeine_ being returned, both _paracetamol_ and _codeine_ are returned as individual concepts as they are also ancestors.

In order to eliminate these other ancestors and only return the *most proximal* result to _Rapideine_, a _MINUS_ constraint is used.  It works by removing the second result set from the first result set. 
