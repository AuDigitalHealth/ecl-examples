# Containered Trade Product Pack search by ingredient
This example shows how to find Containered Trade Product Pack (_CTPP_) concepts containing some ingredients but not others

# Example
We would like to find all the Containered Trade Product Pack concepts that contain codeine but not paracetamol. 

```
< 30537011000036101|containered trade product pack| : 30409011000036107|has TPUU| = 
(
  < 30425011000036101|trade product unit of use| : 
    (
      700000081000036101|has intended active ingredient| = 1978011000036103|codeine|,
      [0..0] 700000081000036101|has intended active ingredient| = 2442011000036104|paracetamol|
    )
)
```

This ECL restricts to descendants of CTPP which have a _has TPUU_ relationship to a TPUU concept which has an active ingredient of codeine, but no active ingredient "[0..0]" of paracetamol.

This same query can be modified to **only** return products that contain codeine _exclusively_ (no other active ingredients present).
```
< 30537011000036101|containered trade product pack| : 30409011000036107|has TPUU| = 
(
  < 30425011000036101|trade product unit of use| : 
    (
      700000081000036101|has intended active ingredient| = 1978011000036103|codeine|,
      [0..0] 700000081000036101|has intended active ingredient| = (ANY minus 1978011000036103|codeine|)
    )
)
```
