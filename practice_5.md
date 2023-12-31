# 1. 
### Создать файл file1 и наполнить его произвольным содержимым.
```console
NataliKoren@ubuntuserver:~$ cat > file1
dsadasd
asfasf
asfasf
```
### Скопировать его в file2.
```console
NataliKoren@ubuntuserver:~$ cp file1 file2
NataliKoren@ubuntuserver:~$ cat file2
dsadasd
asfasf
asfasf
```

### Создать символическую ссылку file3 на file1. 
```console
NataliKoren@ubuntuserver:~$ ln -s file1 file3
```

### Создать жёсткую ссылку file4 на file1. 
```console
NataliKoren@ubuntuserver:~$ ln file1 file4
```

### Посмотреть, какие inode у файлов. 
```console
NataliKoren@ubuntuserver:~$ ls -li
total 12
397260 -rw-rw-r-- 2 duckluckbreakout duckluckbreakout 22 Aug  3 11:20 file1
397375 -rw-rw-r-- 1 duckluckbreakout duckluckbreakout 22 Aug  3 11:20 file2
397429 lrwxrwxrwx 1 duckluckbreakout duckluckbreakout  5 Aug  3 11:52 file3 -> file1
397260 -rw-rw-r-- 2 duckluckbreakout duckluckbreakout 22 Aug  3 11:20 file4
```

### Удалить file1.
```console
NataliKoren@ubuntuserver:~$ rm file1
```

### Что стало с остальными созданными файлами?
```console
NataliKoren@ubuntuserver:~$ ls -li
total 8
397375 -rw-rw-r-- 1 NataliKore NataliKore 22 Aug  3 11:20 file2
397429 lrwxrwxrwx 1 NataliKore NataliKore  5 Aug  3 11:52 file3 -> file1
397260 -rw-rw-r-- 1 NataliKore NataliKore 22 Aug  3 11:20 file4
```

`file2` остался без изменений

`file3 -> file1` остался, но выделен красным

`file4` остался без изменений

### Попробовать вывести их на экран.

Для `file2`
```console
NataliKoren@ubuntuserver:~$ cat file2
dsadasd
asfasf
asfasf
```

Для `file3`:
```console
NataliKoren@ubuntuserver:~$ cat file3
cat: file3: No such file or directory
```

Для `file4`:
```console
NataliKoren@ubuntuserver:~$ cat file4
dsadasd
asfasf
asfasf
```

# 2. 
### Дать созданным файлам другие, произвольные имена. 
```console
NataliKoren@ubuntuserver:~$ mv file2 lalala_file2
NataliKoren@ubuntuserver:~$ mv file3 lalala_file3
NataliKoren@ubuntuserver:~$ mv file4 lalala_file4
```
### Создать новую символическую ссылку. 
```console
NataliKoren@ubuntuserver:~$ ln -s lalala_file2 file2_link
```

### Переместить ссылки в другую директорию.
```console
NataliKoren@ubuntuserver:~$ mv file2_link /tmp/
NataliKoren@ubuntuserver:~$ mv lalala_file3 /tmp/
NataliKoren@ubuntuserver:~$ mv lalala_file4 /tmp/
```

# 3. 
### Создать два произвольных файла. 
```console
NataliKoren@ubuntuserver:~$ echo dasdasd > file1
NataliKoren@ubuntuserver:~$ echo das dasd > file2
NataliKoren@ubuntuserver:~$ ls -l
total 8
-rw-rw-r-- 1 NataliKoren NataliKoren 8 Aug  3 12:05 file1
-rw-rw-r-- 1 NataliKoren NataliKoren 9 Aug  3 12:05 file2
```

### Первому присвоить права на чтение и запись для владельца и группы, только на чтение — для всех.
#### Сделать это в численном виде.
```console
NataliKoren@ubuntuserver:~$ chmod 664 file1
NataliKoren@ubuntuserver:~$ ls -l
total 8
-rw-rw-r-- 1 NataliKoren NataliKoren 8 Aug  3 12:05 file1
-rw-rw-r-- 1 NataliKoren NataliKoren 9 Aug  3 12:05 file2
```

#### Сделать это в символьном виде.
```console
NataliKoren@ubuntuserver:~$ chmod ugo=r file1
NataliKoren@ubuntuserver:~$ chmod ug+w file1
NataliKoren@ubuntuserver:~$ ls -l
total 8
-rw-rw-r-- 1 NataliKoren NataliKoren 8 Aug  3 12:05 file1
-rw-rw-r-- 1 NataliKoren NataliKoren 9 Aug  3 12:05 file2
```


### Второму присвоить права на чтение и запись только для владельца.
#### Сделать это в численном виде.
```console
NataliKoren@ubuntuserver:~$ chmod 600 file2
NataliKoren@ubuntuserver:~$ ls -l
total 8
-rw-rw-r-- 1 NataliKoren NataliKoren 8 Aug  3 12:05 file1
-rw------- 1 NataliKoren NataliKoren 9 Aug  3 12:05 file2
```

#### Сделать это в символьном виде.
```console
NataliKoren@ubuntuserver:~$ chmod ugo-rwx file2
NataliKoren@ubuntuserver:~$ chmod u=rw file2
NataliKoren@ubuntuserver:~$ ls -l
total 8
-rw-rw-r-- 1 NataliKoren NataliKoren 8 Aug  3 12:05 file1
-rw------- 1 NataliKoren NataliKoren 9 Aug  3 12:05 file2
```

# 4. Создать пользователя, обладающего возможностью выполнять действия от имени суперпользователя.
```console
NataliKoren@ubuntuserver:~$ sudo adduser testsudouser
Adding user `testsudouser' ...
Adding new group `testsudouser' (1006) ...
Adding new user `testsudouser' (1005) with group `testsudouser' ...
Creating home directory `/home/testsudouser' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for testsudouser
Enter the new value, or press ENTER for the default
	Full Name []: 
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] y
NataliKoren@ubuntuserver:~$ sudo usermod -aG sudo testsudouser
```
