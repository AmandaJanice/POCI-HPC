# Project Rainbowcrack

Rainbowcrack is a general purpose implementation Phillipe Oechslin’s faster time-memory trade off technique that cracks hashes using rainbow tables. A time-memory tradeoff hash cracker needs a pre-computation stage, at the time all plaintext/hash pairs within the selected hash algorithm, charset, plaintext length are computed and these results are stored in the rainbow tables.


## Getting Started

First, download the Rainbowcrack software for the Operating System of your choice in:
* [Project Rainbowcrack](http://project-rainbowcrack.com/index.htm)

## Features
- Full time-memory tradeoff tool suites, including rainbow table generation, sort, conversion and lookup
- Support rainbow table of any hash algorithm
- Support rainbow table of any charset
- Support rainbow table in raw file format (.rt) and compact file format (.rtc)
- Computation on multi-core processor support
- GPU acceleration with NVIDIA GPUs (CUDA technology)
- GPU acceleration with AMD GPUs (OpenCL technology)
- GPU acceleration with multiple GPUs
- Runs on Windows operating systems
- Runs on Linux operating systems
- Unified rainbow table file format on all supported operating systems
- Command line user interface
- Graphics user interface

## Insallation & Usage

After downloading the project Rainbowcrack software, extract it to a desired folder. To start cracking some hashes, we need to generate some rainbow tables first, so navigate to the folder containing the source code and use the following command in a command line to generate the rainbow tables needed to store the different hash codes/plain text pairs: 
```
./rtgen <hash algorithm> <char set> <plain text minimum> <plain text maximum> <table index> <keyspace>
```
Running these command several times with different parameters will generate sufficient rainbow tables to carry out the hash cracking. Now we have to sort our rainbow tables with the following command:
```
./rtsort .
```
Now, we are ready to crack some hashes and to analyze the performance of different hash algorithms.

### Cracking a hash

To crack a hash code using the rainbow tables that were generated above, run the following command in a command line:
```
./rtcrack . -h <hash code>
```

