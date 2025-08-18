`begin, Input` 
`Store myNum` 
`Load myNum` 
`Add topUp` 
`Store myNum` 
`Load myNum` 
`Output` 
`Jump begin` 
`Halt` 
`myNum, DEC 0` 
`topUp, DEC 3`

`begin, Input` 
`skipcond 400` 
`jump cont` 
`jump end cont,` 
`Store myNum` 
`Load myNum` 
`Add topUp` 
`Store myNum` 
`Load myNum` 
`Output` 
`Jump begin` 
`end, Halt`
`myNum, DEC 0 
`topUp, DEC 1

**Conditional Statements Marie**
`if-then-else if (X > Y)` 
	`Display X` 
`else` 
	`Display Y` 
-- 
`begin, Input` 
`Store myNumX` 
`Input 
`Store myNumY` 
`Load myNumX` 
`Subt myNumY` 

`skipcond 800` 
`jump else` 
`Load myNumX` 
`output` 
`Jump end` 

`else, Load myNumY` 
`output` 
`end, Halt` 
`myNumX, DEC 0` 
`myNumY, DEC 0` 
`One, DEC 1`

