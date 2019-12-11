Build Instructions are provided on the hashcat-5.1.0 folder

The commands used t run the software is the followings:

"hashcat -m 0 -a 0 21232f297a57a5a743894a0e4a801fc3 rockyou.txt"

Options/Arguments Explanation:

"-m" Tells the software which hashing algorithm is going to used the list of all supported hashing algorithms can be found here: https://hashcat.net/wiki/doku.php?id=hashcat

"-a" Tells the software which attack type is going to used. This tells how the software will crack the word. The list of attacking types can be found here: https://hashcat.net/wiki/doku.php?id=hashcat

"21232f297a57a5a743894a0e4a801fc3" The word to be cracked, this case is "admin" and is hashed in MD5 (can be a file containing more than one hashed word). It has to be according the hashing algorithm specified on the first argument.

"rockyou.txt" Is the wordlist that the software will use to search and crack the hashed word. The list has to be really big in order to make the software work at its best. This particular list is not included on the repo because of size restrictions but can be downloaded here: http://downloads.skullsecurity.org/passwords/rockyou.txt.bz2
