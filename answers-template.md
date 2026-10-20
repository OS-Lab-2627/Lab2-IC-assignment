# Lab 2: Answers

Name:
Student ID:

> For each question write **the command you used** and **its output**.
> Use code blocks like this:
>
> ```
> $ pwd
> /home/student/lab2/techcorp
> ```

## Part A: Navigation and inspection

**A1.**
```
$ pwd
/home/zeynep/lab2/techcorp
```


**A2.**
```
$ mkdir -p projects/2026/{alpha,beta,gamma}
```

**A3.**
```
$ touch projects/2026/alpha/README.md
$ ls -la projects/2026/alpha/
total 8
drwxr-xr-x 2 zeynep zeynep 4096 Oct 20 11:25 .
drwxr-xr-x 5 zeynep zeynep 4096 Oct 20 11:23 ..
-rw-r--r-- 1 zeynep zeynep    0 Oct 20 11:25 README.md
```

**A4.**
```
$ cp -r hr/policies projects/2026/beta/
$ ls -l projects/2026/beta/policies/
total 8
-rw-rw-r-- 1 zeynep zeynep 13 Oct 20 10:46 leave.txt
-rw-rw-r-- 1 zeynep zeynep 14 Oct 20 10:46 remote.txt
```

**A5.**

```
$mv projects/2026/gamma projects/2026/delta
$ ls projects/2026
alpha  beta  delta
```

**A6.**
```
$ln -s ../engineering/docs/api.md shared/api_link
$ ls -l shared/api_link
lrwxrwxrwx 1 zeynep zeynep 26 Oct 20 10:49 shared/api_link -> ../engineering/docs/api.md
```

**A7.**
```
$ cat shared/api_link
api reference
```

## Part B: Creating and organising

**B1.**

```
$ id
uid=1000(zeynep) gid=1000(zeynep) groups=1000(zeynep),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),100(users),111(lpadmin),114(lxd)
```

**B2.**

```
$ sudo groupadd engineering
$ sudo groupadd finance
```

**B3.**

```
$ sudo useradd -m alice
$ sudo useradd -m bob
```

**B4.**

```
$ sudo usermod -aG engineering alice
$ sudo usermod -aG finance bob
$ sudo usermod -aG finance alice
```

**B5.**

```
$ groups alice
alice : alice engineering finance
$ groups bob
bob : bob finance
```


## Part C — Users and groups

**C1.**

```
$ ./engineering/src/build.sh
bash: ./engineering/src/build.sh: Erişim engellendi
$ chmod u+x engineering/src/build.sh
$ ./engineering/src/build.sh
building
```

**C2.**

```
$ find . -type f -perm -o=w 2>/dev/null
./engineering/src/mod_7.c
./hr/records/anna.txt
./finance/invoices/inv_103.csv
```

**C3.**

```
$ chmod o-w engineering/src/mod_7.c hr/records/anna.txt finance/invoices/inv_103.csv
```

**C4.**

```
$ touch shared/team.txt
$ sudo chgrp engineering shared/team.txt
$ ls -l shared/team.txt
-rw-rw-r-- 1 zeynep engineering 0 Oct 20 11:00 shared/team.txt
```
