# 4.2 System Architecture

## CPU performance
- clock speed (measured in Hz = cycles per second)
	- a given number of instructions is executed every cycle
- Cache Size
	- having to access slower RAM takes longer, having more cache is beneficial
- Cache Type: there is a trade-off between latency and the hit rate
	- hit-rate: how fast data is found -> highly dependent on size
	- speed vs. size tradeoff
	- solution: multiple levels of cache
- Number of cores: today's chips have multiple processing units (PUs)
	- double cores doesn't quite mean double the actions/speed, it's more complicated
	- multiple cores share a larger cache, but each also has their own

## System Bus
- parallel transmission component
	- many parallel wires transmit an array of bits (at the same time)
- there are other busses than the system bus located inside the CPU
- System bus connects the CPU to memory and input-output devices:
	- address bus -> memory address
	- data bus -> actual data
	- control bus -> e.g. timing of the system
*I/O = input output

