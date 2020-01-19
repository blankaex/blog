---
layout: post
title:  "Over The Wire - Bandit"
date:   2019-08-25
excerpt: "Writeups for OverTheWire - Bandit"
tag:
- CTF
- Security
---

A friend of mine who goes by the name "reed" apparently started uni last week. He joined his uni's security society, where he was tasked to play the challenges on [OverTheWire](http://overthewire.org/wargames/). He challenged me to see how far I could get on Bandit, since he made it to level 20. Little did he know, the students I teach typically get through Narnia by the end of semester.

That being said, I realised that I don't have any posts on my blog about cyber security. Everyone knows CTF writeups are the bona fide security blog, so it's probably a good way to get started. I've actually never played OverTheWire, but I'm expecting Bandit to be fairly trivial based on word of mouth. Let's hope I don't eat my words.

# Writeups

## Level 0
```
$ ssh bandit0@bandit.labs.overthewire.org -p 2220
bandit0
```

## Level 1
```
$ cat readme
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
```

## Level 2
```
$ cat ./-
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9
```

## Level 3
```
$ cat spaces\ in\ this\ filename
dQclWmgdLOKQ3YNgjWxGoRMb5luK
```

## Level 4
```
$ cat inhere/.hidden
pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```

## Level 5
```
$ file inhere/*
inhere/-file06: data
inhere/-file07: ASCII text
inhere/-file08: data
$ cat inhere/-file07
koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```

## Level 6
```
$ find inhere -type f -print0 | xargs -0 ls -l | grep 1033
-rw-r----- 1 root bandit5 1033 Oct 16  2018 inhere/maybehere07/.file2
$ cat inhere/maybehere07/.file2
DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

## Level 7
```
$ find / -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
$ cat /var/lib/dpkg/info/bandit7.password
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```

## Level 8
```
$ grep millionth data.txt | cut -d$'\t' -f2
cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```

## Level 9
```
$ sort data.txt | uniq -u
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```

## Level 10
```
$ strings -n20 data.txt | grep '=' | cut -d' ' -f2
truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```

## Level 11
```
$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```

## Level 12
```
$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```

## Level 13
Rebuild the binary using `xxd`:
```
$ xxd -rp data.txt out
```
Then it's just a lot of nested compressed files. Extract as appropriate.
```
$ gunzip [FILE]
$ bunzip2 [FILE]
$ tar -xaf [FILE]
```
And get the password.
```
$ cat data8
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```

## Level 14
```
$ scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private .
$ chmod 600 sshkey.private
$ ssh bandit14@bandit.labs.overthewire.org -p 2220 -i sshkey.private
$ cat /etc/bandit_pass/bandit14
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e
```

## Level 15
```
$ echo "4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" | nc localhost 30000
Correct!
BfMYroe26WYalil77FoDi9qh59eK5xNr
```

## Level 16
```
$ openssl s_client -connect localhost:30001
BfMYroe26WYalil77FoDi9qh59eK5xNr
Correct!
cluFn7wTiGryunymYOu4RcffSxQluehd
```

## Level 17
Use `nmap` to find the open ports within the specified range.
```
$ nmap localhost -p 31000-32000
Starting Nmap 7.40 ( https://nmap.org ) at 2019-08-25 15:40 CEST
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00023s latency).
Not shown: 999 closed ports
PORT      STATE SERVICE
31518/tcp open  unknown
31790/tcp open  unknown
```
Just try both and see which one gives a key.
```
$ openssl s_client -connect localhost:31790
cluFn7wTiGryunymYOu4RcffSxQluehd
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
```

## Level 18
```
$ diff passwords.old passwords.new | grep ">" | cut -d' ' -f2
kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```

## Level 19
```
$ scp -P 2220 bandit18@bandit.labs.overthewire.org:~/readme .
$ cat readme
IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```

## Level 20
```
$ ./bandit20-do cat /etc/bandit_pass/bandit20
GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```

## Level 21
```
$ echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l -p 9447
^Z
$ ./suconnect 9447
^Z
$ fg 1
echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l -p 9447
^Z
$ fg 2
./suconnect 9447
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password
$ fg 1
echo "GbKksEFF4yrVs6il55v6gwY5aVje5f0j" | nc -l -p 9447
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr
```

## Level 22
```
$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
Yk7owGAcWjwMVRwrTesJEwB7WVOiILLI
```

## Level 23
```
$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
$ cat /tmp/$(echo I am user bandit23 | md5sum | cut -d ' ' -f 1)
jc1udXuA1tiHqjIsL8yaapX5XIAI6i0n
```

## Level 24
```
$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname
echo "Executing and deleting all scripts in /var/spool/$myname:"
for i in * .*;
do
	if [ "$i" != "." -a "$i" != ".." ];
	then
	echo "Handling $i"
	timeout -s 9 60 ./$i
	rm -f ./$i
	fi
done
$ cat > /var/spool/solve.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/sairuiu/pass
$ chmod +x /var/spool/solve.sh
$ cat /tmp/9447/pass
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ
```

## Level 25
```
$ for i in {0000..9999}; do echo "UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i" >> dict; done
$ cat dict | nc localhost 30002
Wrong! Please enter the correct pincode. Try again.
Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is uNG9O58gUE7snukf3bvZ0rxhtnjzSGzG
```

## Level 26
Find the program being used as `bandit26`'s login shell.
```
$ getent passwd bandit26
bandit26:x:11026:11026:bandit level 26:/home/bandit26:/usr/bin/showtext
$ cat /usr/bin/showtext
#!/bin/sh

export TERM=linux

more ~/text.txt
exit 0
```
`more` can launch `vi` which can launch `bash`. Resize the terminal window so that `more` stays in interactive mode and `ssh`, then escape to a real shell and read the password.
```
$ ssh bandit26@localhost -i bandit26.sshkey
v
:!/bin/bash
$ cat /etc/bandit_pass/bandit26
5czgV9L3Xx8JPOyRbXh6lQbmIOWvPT6Z
```
