
![[Miller rabin generation.png]]
Miller rabin Test algorithm
```
Input #1 : _n_ > 2, an odd integer to be tested for primality
Input #2: _k_, the number of rounds of testing to perform
Output: “_composite_” if _n_ is found to be composite, “_probably prime_” otherwise

let _s_ > 0 and _d_ odd > 0 such that _n_ − 1 = 2_s__d_  # by factoring out powers of 2 from _n_ − 1
repeat _k_ times:
    _a_ ← random(2, _n_ − 2)  # _n_ is always a probable prime to base 1 and _n_ − 1
    _x_ ← _a__d_ mod _n_
    repeat _s_ times:
        _y_ ← _x_2 mod _n_
        if _y_ = 1 and _x_ ≠ 1 and _x_ ≠ _n_ − 1 then # nontrivial square root of 1 modulo _n_
            return “_composite_”
        _x_ ← _y_
    if _y_ ≠ 1 then
        return “_composite_”
return “_probably prime_”
```


