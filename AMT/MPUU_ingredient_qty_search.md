# Medicinal Product Unit of Use search by ingredient, form, dose
This example shows how to find Medicinal Products Unit of Use (_MPUU_) concepts containing minimum doses of individual ingredients.  It uses attribute groups to restrict the results to a refset and to group the constraints for each ingredient together.

# Example
We would like to find all the Medicinal Products Unit of Use concepts that are tablets and contain at least 10mg codeine and 250mg of paracetamol. 

```
(
 (^929360071000036103|Medicinal product unit of use refset| : 
  {
   700000111000036105|Strength reference set| >= #10000,
   177631000036102|has unit| = 700000881000036108|microgram/each|,
   700000081000036101|has intended active ingredient| = 1978011000036103|codeine|
  },
  {
   700000111000036105|Strength reference set| >= #250,
   177631000036102|has unit| = 700000801000036102|mg/each|,
   700000081000036101|has intended active ingredient| = 2442011000036104|paracetamol|
  },
  30523011000036108|has manufactured dose form| = 154011000036109|tablet|
 )
) 
```

This ECL query firstly constrains the results returned to those within the _MPUU_ refset and then any concept containing
 - codeine with at least 10000ug/each
 - paracetamol with at least 250mg/each

The results are further restricted using the _has manufactured dose form_ relationship to constrain the resultset to only being tablets. 
