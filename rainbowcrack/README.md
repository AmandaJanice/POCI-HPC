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
> Also, Hash-Buster uses some APIs for hash lookups, check the source code if you are paranoid.

Hash-Buster can be run directly from the python script but I highly suggest you to install it with `make install`

After the installation, you will be able to access it with `buster` command.

### Cracking a single hash

You don't need to specify the hash type. Hash Buster will identify and *crack* it under 3 seconds.

**Usage:** `buster -s <hash>`
### Finding hashes from a directory

Yep, just specify a directory and Hash Buster will go through all the files and directories present in it, looking for hashes.

**Usage:** `buster -d /root/Documents`
### Cracking hashes from a file

Hash Buster can find your hashes even if they are stored in a file like this
```
simple@gmail.com:21232f297a57a5a743894a0e4a801fc3
{"json@gmail.com":"d033e22ae348aeb5660fc2140aec35850c4da997"}
surrondedbytext8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918surrondedbytext
```

**Usage:** `buster -f /root/hashes.txt`
