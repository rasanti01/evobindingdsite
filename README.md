# Evolution of overlapping binding sites

Consider the following scenario: A gene needs to be turned on under some condition and off under different con-
ditions. This is implemented with a binding site for an activator and an overlapping binding site for a repressor,
so that either one or the other can be bound, but not both at the same time. Develop a model for the evolution
of such overlapping sites.


## Initiation

one gene, has to be turned on under condition 1 (c1) & turned off under condition 2 (c2)
we got activator and repressor proteins, both able to bind sequences (b_a and b_r)
the ‘perfect sequences’ b_a & b_r (with hamming distance = 0) prescribed by the proteins do not change over time
the prob. of act./rep. binding to a sequence is dependent on the hamming distance
we got a pool of random sequences s_i with length l < b_a+b_r

## Simulation

select c1 or c2 -> low/high concentration of activator/repressor or other way round
iterate through sequences and determine hamming distances to b_a & b_r

let the repressor bind with prob. p_r depending on hamming distance(s) and concentration of repressor
if repressor did not bind: let activator bind with p_a depending on hamming distance(s) and concentration of activator
else: nothing bound to sequence

death: cells die with prob. p_d. but: in-/ decreased chance of survival if rep./act. is bound during c1 (/other way round for c2), p_d without act./rep. somewhere in between

## Output

some variable v measuring the min hamming distance to repressor and activator (or plot both separately) + how it changes over time

## Questions

how does v change if we vary the length of our sequence (and sequence has to decide between mutating towards activator/repressor)
what if we vary survival chances in an asymmetric way
are we able to mathematically account for our results?
