# OverTheWire - Bandit

                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       
            More information on http://www.overthewire.org/wargames

		      ,----..            ,----,          .---.
		     /   /   \         ,/   .`|         /. ./|
		    /   .     :      ,`   .'  :     .--'.  ' ;
		   .   /   ;.  \   ;    ;     /    /__./ \ : |
		  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
		  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
		  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
		  .   |  ' ' ' : `----'  |  |  \   ;  `      |
		  '   ;  \; /  |     '   :  ;   .   \    .\  ;
		   \   \  ',  /      |   |  '    \   \   ' \ |
		    ;   :    /       '   :  |     :   '  |--"
		     \   \ .'        ;   |.'       \   \ ;
		  www. `---` ver     '---' he       '---" ire.org

The Bandit wargame is an online game offered by the OverTheWire community. It helps you to learn various Linux commands and understand some basic features of this system.

This is a quick write-up of my solutions for this challenge. I advise you do it yourself before looking at the solutions as you won’t learn anything without trying. My goal here is simply to show you how I did it and compare your solutions with mine.


## Level 0
The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

```sh
andy@pc:~$ ssh bandit0@bandit.labs.overthewire.org -p 2220
bandit0@bandit.labs.overthewire.org password: bandit0

bandit0@bandit:~$ ls
readme

bandit0@bandit:~$ cat readme 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

## Level 01 
The password for the next level is stored in a file called - located in the home directory

```sh
andy@pc:~$ ssh bandit0@bandit.labs.overthewire.org -p 2220
bandit0@bandit.labs.overthewire.org password: bandit0

bandit0@bandit:~$ ls
readme

bandit0@bandit:~$ cat readme 
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
```

## Level 02
The password for the next level is stored in a file called spaces in this filename located in the home directory

```sh
andy@pc:~$ ssh bandit2@bandit.labs.overthewire.org -p 2220
bandit2@bandit.labs.overthewire.org password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

bandit2@bandit:~$ ls -al
total 24
drwxr-xr-x  2 root    root    4096 Apr 23 18:04 .
drwxr-xr-x 70 root    root    4096 Apr 23 18:05 ..
-rw-r--r--  1 root    root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root    root    3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root    root     807 Jan  6  2022 .profile
-rw-r-----  1 bandit3 bandit2   33 Apr 23 18:04 spaces in this filename

bandit2@bandit:~$ cat ./spaces\ in\ this\ filename 
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

```
## Level 03
The password for the next level is stored in a hidden file in the *inhere* directory.

```sh

andy@pc:~$ ssh bandit3@bandit.labs.overthewire.org -p 2220
~ bandit3@bandit.labs.overthewire.org password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

bandit3@bandit:~$ ls -al
total 24
drwxr-xr-x  3 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
drwxr-xr-x  2 root root 4096 Apr 23 18:04 inhere
-rw-r--r--  1 root root  807 Jan  6  2022 .profile

bandit3@bandit:~$ cd inhere/

bandit3@bandit:~/inhere$ ls -al
total 12
drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
-rw-r----- 1 bandit4 bandit3   33 Apr 23 18:04 .hidden

bandit3@bandit:~/inhere$ cat ./.hidden 
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

```
## Level 04
The password for the next level is stored in the only human-readable file in the *inhere* directory. Tip: if your terminal is messed up, try the “reset” command.

```sh

andy@pc:~$ ssh bandit4@bandit.labs.overthewire.org -p 2220
~ bandit4@bandit.labs.overthewire.org password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

bandit4@bandit:~$ ls -al
total 24
drwxr-xr-x  3 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
drwxr-xr-x  2 root root 4096 Apr 23 18:04 inhere
-rw-r--r--  1 root root  807 Jan  6  2022 .profile

bandit4@bandit:~$ cd inhere/

bandit4@bandit:~/inhere$ ls -al
total 48
drwxr-xr-x 2 root    root    4096 Apr 23 18:04 .
drwxr-xr-x 3 root    root    4096 Apr 23 18:04 ..
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file00
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file01
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file02
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file03
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file04
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file05
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file06
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file07
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file08
-rw-r----- 1 bandit5 bandit4   33 Apr 23 18:04 -file09

bandit4@bandit:~/inhere$ file ./-*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators

bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

```
## Level 05

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

```sh
andy@pc:~$ ssh bandit4@bandit.labs.overthewire.org -p 2220
~ bandit4@bandit.labs.overthewire.org password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

bandit5@bandit:~$ ls -al
total 24
drwxr-xr-x  3 root root    4096 Apr 23 18:04 .
drwxr-xr-x 70 root root    4096 Apr 23 18:05 ..
-rw-r--r--  1 root root     220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root    3771 Jan  6  2022 .bashrc
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 inhere
-rw-r--r--  1 root root     807 Jan  6  2022 .profile

bandit5@bandit:~$ cd inhere/

bandit5@bandit:~/inhere$ ls -al
total 88
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 .
drwxr-xr-x  3 root root    4096 Apr 23 18:04 ..
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere00
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere01
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere02
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere03
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere04
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere05
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere06
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere07
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere08
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere09
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere10
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere11
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere12
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere13
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere14
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere15
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere16
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere17
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere18
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 maybehere19

bandit5@bandit:~/inhere$ find -type f -size 1033c
./maybehere07/.file2

bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

```
## Level 06

The password for the next level is stored somewhere on the server and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

```sh

andy@pc:~$ ssh bandit6@bandit.labs.overthewire.org -p 2220
~ bandit6@bandit.labs.overthewire.org password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

bandit6@bandit:~$ man find

bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password

// La syntaxe 2>/dev/null dans la commande find est une redirection de sortie qui redirige la sortie d'erreur standard (stderr) vers un fichier spécial /dev/null, qui est une sorte de trou noir qui ne stocke pas les données.

bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

```
## Level 07

The password for the next level is stored in the file data.txt next to the word millionth

```sh

andy@pc:~$ ssh bandit7@bandit.labs.overthewire.org -p 2220
~ bandit7@bandit.labs.overthewire.org password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

bandit7@bandit:~$ man grep

bandit7@bandit:~$ grep -n millionth ./data.txt 
8994:millionth	TESKZC0XvTetK0S9xNwm25STk5iWrBvP

```
## Level 08
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

```sh

andy@pc:~$ ssh bandit8@bandit.labs.overthewire.org -p 2220
~ bandit8@bandit.labs.overthewire.org password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t


```

## Level 09
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.


```sh

andy@pc:~$ ssh bandit9@bandit.labs.overthewire.org -p 2220
~ bandit9@bandit.labs.overthewire.org password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

bandit9@bandit:~$ strings data.txt | grep "=="
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

```

## Level 10
The password for the next level is stored in the file data.txt, which contains base64 encoded data

```sh

andy@pc:~$ ssh bandit10@bandit.labs.overthewire.org -p 2220
~ bandit10@bandit.labs.overthewire.org password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

bandit10@bandit:~$ ls -al
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit11 bandit10   69 Apr 23 18:04 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile

bandit10@bandit:~$ cat data.txt 
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==

bandit10@bandit:~$ echo VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg== | base64 --decode 
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM


```

## Level 11
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

```sh

andy@pc:~$ ssh bandit11@bandit.labs.overthewire.org -p 2220
~ bandit11@bandit.labs.overthewire.org password: 

bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi

bandit11@bandit:~$ cat data.txt | tr ‘A-Za-z’ ‘N-ZA-Mn-za-m’
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

```
## Level 12
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. 
For this level it may be useful to create a directory under /tmp in which you can work using mkdir. 
For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)


```sh
andy@pc:~$ ssh bandit12@bandit.labs.overthewire.org -p 2220
~ bandit12@bandit.labs.overthewire.org password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

bandit12@bandit:~$ cat data.txt 
00000000: 1f8b 0808 2773 4564 0203 6461 7461 322e  ....'sEd..data2.
00000010: 6269 6e00 0145 02ba fd42 5a68 3931 4159  bin..E...BZh91AY
00000020: 2653 597b 4f96 5f00 0018 ffff fd6f e7ed  &SY{O._......o..
00000030: bff7 bef7 9fdb d7ca ffbf edff 8ded dfd7  ................
00000040: bfe7 bbff bfdb fbff ffbf ff9f b001 3b56  ..............;V
00000050: 0400 0068 0064 3400 d341 a000 0680 0699  ...h.d4..A......
00000060: 0000 69a0 0000 1a00 1a0d 0034 0034 d3d4  ..i........4.4..
00000070: d1a3 d464 6834 6403 d469 b422 0d00 3400  ...dh4d..i."..4.
00000080: 1a68 068d 3403 4d06 8d00 0c80 00f5 0003  .h..4.M.........
00000090: 4031 3119 00d0 1a68 1a34 c86d 4640 00d0  @11....h.4.mF@..
000000a0: 0007 a80d 000d 00e9 a340 d034 0341 a000  .........@.4.A..
000000b0: 0699 07a9 881e a0d0 da80 6834 0c43 4068  ..........h4.C@h
000000c0: 6432 0340 0c80 6800 0346 8006 8000 d034  d2.@..h..F.....4
000000d0: 0001 f0e1 810e 1958 b7a4 92c7 640e 421a  .......X....d.B.
000000e0: a147 6142 a67e 3603 a756 3ba9 1b08 e034  .GaB.~6..V;....4
000000f0: 41fd 1247 661d b380 00b7 cd8c b23e b6b2  A..Gf........>..
00000100: 1947 e803 0be5 6077 a542 e9ea 7810 29f0  .G....`w.B..x.).
00000110: 429d e1d7 ad8b 0b78 056b e37c 06df 4917  B......x.k.|..I.
00000120: 9b46 f69d 4473 80b4 edc2 ee10 04e3 3e52  .F..Ds........>R
00000130: dd34 2244 08cb 5e64 9314 9521 505e e767  .4"D..^d...!P^.g
00000140: 9021 d029 85e7 9ce2 d1ce d44f 5ec5 f6d6  .!.).......O^...
00000150: d918 de31 f1f5 d149 4695 0937 d06b f046  ...1...IF..7.k.F
00000160: 789d 1bd0 ca69 11eb 2c9a 3290 3d9e 0511  x....i..,.2.=...
00000170: 6cad 205b edc8 c4b5 4691 379a 5978 58c3  l. [....F.7.YxX.
00000180: 4846 a4a0 3ba5 a89a a794 1f93 c588 8160  HF..;..........`
00000190: 016e 2504 2c74 643b 5046 4154 751c 33b1  .n%.,td;PFATu.3.
000001a0: c3e5 53d8 a959 5fdc 6c12 f2bd 02f3 2d83  ..S..Y_.l.....-.
000001b0: b965 3188 0d3c b097 4156 e950 9d49 64f6  .e1..<..AV.P.Id.
000001c0: da4a 2db5 a4ea 5365 27c0 1e79 8109 5f31  .J-...Se'..y.._1
000001d0: c184 46c9 74a5 f923 5ea1 6861 f058 226c  ..F.t..#^.ha.X"l
000001e0: 3df6 5d10 d11f d966 77c9 e488 448c 5a6f  =.]....fw...D.Zo
000001f0: 2c10 410b 4280 140a 0818 8afa 0cfa 8bf7  ,.A.B...........
00000200: ad34 3308 4077 6552 9849 378e 7d85 1fd8  .43.@weR.I7.}...
00000210: f287 1238 7639 11e2 f1e6 483b 7548 25e2  ...8v9....H;uH%.
00000220: 7de4 24ff 1a69 0b85 4b4c ebd0 1231 a512  }.$..i..KL...1..
00000230: f9fb 109c e7ea d932 98fd eb76 f4f8 fa29  .......2...v...)
00000240: 967c e152 9c69 c607 6207 eaef 2095 9441  .|.R.i..b... ..A
00000250: a64e 9ffc 5dc9 14e1 4241 ed3e 597c 9f2e  .N..]...BA.>Y|..
00000260: f0c8 4502 0000                           ..E...

// La commande xxd est un outil de la ligne de commande disponible sur les systèmes Unix/Linux qui permet de convertir un fichier binaire en une représentation hexadécimale ou l'inverse

bandit12@bandit:~$ mkdir /tmp/andy4645

bandit12@bandit:~$ cp data.txt /tmp/andy4645

bandit12@bandit:~$ cd /tmp/andy4645

bandit12@bandit:/tmp/andy4645$ xxd -r data.txt data2.bin

bandit12@bandit:/tmp/andy4645$ ls
data2.bin  data.txt

bandit12@bandit:/tmp/andy4645$ mv data2.bin data2.gz

bandit12@bandit:/tmp/andy4645$ file data2.gz
data2.gz: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 581

bandit12@bandit:/tmp/andy4645$ gzip data2.gz
gzip: data2.gz already has .gz suffix -- unchanged

bandit12@bandit:/tmp/andy4645$ gzip -d data2.gz

bandit12@bandit:/tmp/andy4645$ ls
data2  data.txt

bandit12@bandit:/tmp/andy4645$ file data2
data2: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/andy4645$ bzip2 -d -k data2
bzip2: Can't guess original name for data2 -- using data2.out

bandit12@bandit:/tmp/andy4645$ ls
data2  data2.out  data.txt

bandit12@bandit:/tmp/andy4645$ file data2.out 
data2.out: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 20480

bandit12@bandit:/tmp/andy4645$ mv data2.out data4.gz

bandit12@bandit:/tmp/andy4645$ ls
data2  data4.gz  data.txt

bandit12@bandit:/tmp/andy4645$ gzip -d data4.gz 

bandit12@bandit:/tmp/andy4645$ ls
data2  data4  data.txt

bandit12@bandit:/tmp/andy4645$ file data4
data4: POSIX tar archive (GNU)

bandit12@bandit:/tmp/andy4645$ tar -xvf data4
data5.bin

bandit12@bandit:/tmp/andy4645$ file data5.bin 
data5.bin: POSIX tar archive (GNU)

bandit12@bandit:/tmp/andy4645$ tar -xvf data5.bin
data6.bin

bandit12@bandit:/tmp/andy4645$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k

bandit12@bandit:/tmp/andy4645$ bzip2 -d data6.bin
bzip2: Can't guess original name for data6.bin -- using data6.bin.out

bandit12@bandit:/tmp/andy4645$ ls
data2  data4  data5.bin  data6.bin.out  data.txt

bandit12@bandit:/tmp/andy4645$ file data6.bin.out 
data6.bin.out: POSIX tar archive (GNU)

bandit12@bandit:/tmp/andy4645$ tar -xvf data6.bin.out
data8.bin

bandit12@bandit:/tmp/andy4645$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 49

bandit12@bandit:/tmp/andy4645$ mv data8.bin data8.gz

bandit12@bandit:/tmp/andy4645$ gzip -d data8.gz 

bandit12@bandit:/tmp/andy4645$ ls
data2  data2.bz2  data4  data5.bin  data6.bin.out  data8  data.txt

bandit12@bandit:/tmp/andy4645$ file data8
data8: ASCII text

bandit12@bandit:/tmp/andy4645$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

```
## Level 13
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

```sh

andy@pc:~$ ssh bandit13@bandit.labs.overthewire.org -p 2220
~ bandit13@bandit.labs.overthewire.org password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

bandit13@bandit:~$ ssh -i ./sshkey.private -p 2220 bandit14@localhost 

bandit14@bandit:~$ cat /etc/bandit_pass/bandit14
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

```
## Level 14
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

```sh

andy@pc:~$ ssh bandit14@bandit.labs.overthewire.org -p 2220
~ bandit14@bandit.labs.overthewire.org password: fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

// bandit14@bandit:~$ cat ./.ssh/authorized_keys 
// ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDGSQ4TzdbZw5PshaEVz1o9ppCZAN2DO5cK/6mlkdr75u5KQ36CDS1yvsXDw0sZrn5TN5zasSDRaZ568HXcAihinQxnIROrjq36OT2m43BnAi31eAFm58a1kTBZsVbD+9Us3A5cF7hRZK0ZFbOA+kR5K/lNvVWMtkgF0amFMgrbYCbPpltOEyyIyfIlp8TAn9Pw9A7ebJL3W9QcS6g4wDOhQgPiQ3QwRnf5dqHIrQclWrrwqxU5t59cbW+8DcYAnb2TElqq9F+BiepmvJY3vDcIeM1Thz/YmSn6fwvRKfFo0D5ZgDuOI/JMXSKzy7MyVhDiXUvOH/z8ym+EJAXyvbZ3 rudy@localhost


```
## Level 15
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL encryption.

Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…

```sh

andy@pc:~$ ssh bandit15@bandit.labs.overthewire.org -p 2220
~ bandit15@bandit.labs.overthewire.org password: 

bandit15@bandit:~$ ls -al
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r-----  1 bandit15 bandit15   33 Apr 23 18:04 .bandit14.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile

read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed

// bandit15@bandit:~$ cat .bandit14.password 
// fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

```
## Level 16
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

```sh
andy@pc:~$ ssh bandit16@bandit.labs.overthewire.org -p 2220
~ bandit16@bandit.labs.overthewire.org password: JQttfApK4SeyHwDlI9SXGR50qclOAil1

bandit16@bandit:~$ nmap -sV localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2023-05-07 11:54 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.000094s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/

bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
~ ...
~ ---
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

~ closed

// bandit16@bandit:~$ cat .bandit15.password 
// jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```
## Level 17
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

```sh
andy@pc:~$ nano sshkey17.private
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

andy@pc:~$ chmod 600 sshkey17.private 

andy@pc:~$ ssh -i sshkey17.private bandit17@bandit.labs.overthewire.org -p 2220

bandit17@bandit:~$ sort passwords.old passwords.new | uniq -u
glZreTEH1V3cGKL6g4conYqZqaEj0mte
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

bandit17@bandit:~$  cat passwords.new | grep glZreTEH1V3cGKL6g4conYqZqaEj0mte
bandit17@bandit:~$ cat passwords.new | grep hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

```
## Level 18
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

```sh

andy@pc:~$ ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
~ bandit18@bandit.labs.overthewire.org password: hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg

awhqfNnAbc1naukrpqDYcF95h7HoMTrC

Explanation: You can pass the command you want to execute directly to the ssh command to bypass the issue.


```
## Level 19
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

```sh

andy@pc:~$ ssh bandit19@bandit.labs.overthewire.org -p 2220
~ bandit19@bandit.labs.overthewire.org password: awhqfNnAbc1naukrpqDYcF95h7HoMTrC

bandit19@bandit:~$ ls -al
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rwsr-x---  1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile

bandit19@bandit:~$ ./bandit20-do 
Run a command as another user.
  Example: ./bandit20-do id

bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20 
VxCazJaVykI6W36BkBU0mJTCM8rR95XT

```
## Level 20
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

```sh

andy@pc:~$ ssh bandit20@bandit.labs.overthewire.org -p 2220
~ bandit20@bandit.labs.overthewire.org password: 

# Terminal1
bandit20@bandit:~$ nc -lp 31337 < /etc/bandit_pass/bandit20
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

# Terminal2
bandit20@bandit:~$ ./suconnect 31337
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password

```
## Level 21
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

```sh

andy@pc:~$ ssh bandit21@bandit.labs.overthewire.org -p 2220
~ bandit21@bandit.labs.overthewire.org password: NvEJF7oVjkddltPSrdKEFOllh9V1IBcq

```
