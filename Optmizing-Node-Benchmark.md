# Optimizing Node Benchmark

Usually, to run the full Node.js benchmark suite (benchmark/comapare.js) takes days
of execution. The plan is to find some gaps and reduce this time.

## Plan

* [ ] Identify how long each benchmark file takes
  * Multiples that by 30 - as we rely on a student t-test approach to compare results

* [ ] Identify the best N for each benchmark file
  * Run each benchmark with N=100
  * Calculate the CV (CV=STD/Mean)
  * If CV > 3%
  * Increase N -> Repeat
  * Otherwise, select N as the "correct" N

> Note: make sure to calculate N on a more realistic machine or
in several different machine and select the higest N. This should avoid, CV due to hardware
reasons.
