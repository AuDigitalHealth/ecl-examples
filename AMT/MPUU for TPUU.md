# Retreive the MPUU for a given TPUU

This example shows how to find the corresponding Medicinal Product Unit of Use (_MPUU_) concept for a given Trade Product Unit of Use (_TPUU_)0

# Example
Focus TPUU : 1109861000168100|Calcium 600 mg plus Vitamin D3 1000 IU (Health Plus Vitamins) film-coated tablet|

The simplest approach would appear to be retrieving all ancestors for the TPUU that are members of MPUU reference set
```
>1109861000168100|Calcium 600 mg plus Vitamin D3 1000 IU (Health Plus Vitamins) film-coated tablet| 
AND ^929360071000036103|MPUU reference set|
```

However, for many products, particularly multi-ingredient products they might have several MPUU ancesstors.
For example:

```
>53658011000036100 |Nurofen Plus film-coated tablet| AND ^929360071000036103|MPUU reference set|
```
Returns two MPUUs.
* 61870011000036102 | ibuprofen 200 mg + codeine phosphate hemihydrate 12.8 mg tablet |
* 22754011000036103 | ibuprofen 200 mg tablet |

To limit the results to the most distal MPUU in this set, exclude ancestors of members of this set.
```
(>53658011000036100 |Nurofen Plus film-coated tablet| AND ^929360071000036103|MPUU reference set|)
MINUS
>(>53658011000036100 |Nurofen Plus film-coated tablet| AND ^929360071000036103|MPUU reference set|)
```
