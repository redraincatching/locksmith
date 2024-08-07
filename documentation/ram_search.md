# ram search
----
scribblings for what notes i take thanks to ram search

## memory 
----
`0x021BD194` - player's current source, 2-byte value (maybe larger)

## dissassembler
`0x0202A580` - comparison for buying towers

so first we load from r0 at offset `#0x84` to r2
then `adds r2, r2, r1`
we move 0 into r1 (i think, still not sure of the mi suffix)
then store the value from r1 into the palce where we loaded from r0 into r2, `strmi r1, [r0, #0x84]`
and branch if negative/zero to `0x0202A590`
otherwise
we load from `0x0202A598` into r1
compare r2, r1
-> note that r2 contains our current source balance, and r1 contains `0x021BD110`, which i think may be the address at which the value of the current wall piece
we then `strgt r1, [r0, #84]`
and  `strle r2, [r0, #84]`
then load from `0x0202A59c` to r12 and `bx` r12
then the code gets a bit too confusing for me

this code is under the label `LAB_0202a56c`, which is referenced by `FUN_0200e6f0`, at `0200e704`
remember that r2 is a function parameter register
