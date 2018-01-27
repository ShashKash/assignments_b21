Level 0 :

"ssh bandit0@bandit.labs.overthewire.org -p 2220"
"ls" to find a file named "readme"
"cat" to read the file
Found the password to level1 as boJ9jbbUNNfktd78OOpsqOltutMc3MY1.

Level 1 :

"ssh bandit1@bandit.labs.overthewire.org -p 2220"
cat interprets "-" as stdin.
Used the whole directory name to distinguish it as a file.
"cat ./- " to read the file.
Password is CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9.

Level 2 :

Used "cat spaces\ in\ the\ filename" to read the password.
Password for next level: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK.

Level 3 :

Used "cd inhere" to navigate to inhere directory,
then "ls -a" to list the hidden files.
used "cat .hidden" to read the password
Password: pIwrPrtPN36QITSp3EQaw936yaFoFgAB

Level 4 :

found a bunch of files in the inhere directory, all starting with "-"
password was in a "human-readable only" file so,

used "cat ./file00" then "./cat01" and so on to read all the files
The only readable one was -file07 which had the readable Password
Password: koReBOKuIDDepwhWk7jZC0RTdopnAYKh

Level 5 :

used "cd inhere"
used "ls -l -h -a *" to list all files with size and whether they are hidden or shown and executable
checked and found file as .file2 in maybehere06 satisfying all conditions
Used "cat .file2" to read the password
Password: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

Level 6 :

Used "find /* -size 33c -group bandit6 -user bandit7" to check the whole system for a file with
size 33 bytes, group owner as bandit6, and user as bandit7
All the files where denied permission except /var/lib/dpkg/info/bandit7.password
used "cd /var/lib/dpkg/info" to get into the folder
used "cat bandit.password" to read the file
Password: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

Level 7 :

used "grep millionth data.txt" to find the word millionth and next to it was the password
Password: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

Level 8 :

used "sort data.txt | uniq -c" to find the line
Password: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

Level 9 :

used "strings data.txt" to list the human readable characters and found the Password
Password: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

Level 10 :

in order to decode the base64 code i used "man base64" to search about it
then finally used "base64 -d data.txt" to get the password.

Password: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

Level 11 :

Searched in google about rot13 and found about the syntax to decode it
used "cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'" to get the Password
Here A-Za-z represents first set of uppercase and lowercase alphabets,
and N-ZA-Mn-za-m represents the second set from N-Z then A-M and similarily for lower case.
Password: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

Level 12 :

I am not using detailed explaination here as the method is too long...

mkdir /tmp/wowawesome/
cp data.txt /tmp/wowawesome/ 
cd /tmp/wowawesome/
xxd -r data.txt > c.gz
file c.gz
gzip -d c.gz
file c
mv c c.bz2
bzip2 -d c.bz2
file c
mv c c.gz
gzip -d c.gz
file c
tar -xf c
file data5.bin
tar -xf data5.bin
file data6.bin
mv data6.bin c.bz2
bzip2 -df c.bz2
file c
tar -xf c
file data8.bin
mv data8.bin c.gz
gzip -df c.gz
file c
Finally used "cat c" to read the file and password to get to level 13
Password: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL


