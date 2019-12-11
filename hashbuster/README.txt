Hash Buster Features:
	1) Automatic hash type identification
	2) Supports MD5, SHA1, SHA256, SHA384, SHA512
	3) Can extract & crack hashes from a file
	4) Can find hashes from a directory, recursively
	5) Multi-threading

Installation Guide:
	1) Access Hash Buster folder from terminal
	2) Once inside the folder, run the "make install" command
	3) Verify that an "Installation Succesful!!" message appears.

Usage Guide:
	1) Crack a single hash: buster -s <hash>
	2) Crack hashes inside a file: buster -f /root/hashes.txt
	3) Crack hashes inside all files in directory: buster -d /root/Documents
	4) Crack a single hash indicating thread number: buster -s <hash> -t 12

