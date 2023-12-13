# 1. Навигация по файловой системе. 

## Попрактиковаться в перемещении между каталогами, используя полный и относительный путь.
```console
NataliKoren@ubuntuserver:~$ cd tmp1
NataliKoren@ubuntuserver:~/tmp1$
```
```console
NataliKoren@ubuntuserver:~/tmp1$ cd tmp2/tmp\ 3
NataliKoren@ubuntuserver:~/tmp1/tmp2/tmp 3$
```
```console
NataliKoren@ubuntuserver:~/tmp1/tmp2/tmp 3$ cd ../../tmp2_1
NataliKoren@ubuntuserver:~/tmp1/tmp2_1$
```
```console
NataliKoren@ubuntuserver:~/tmp1/tmp2_1$ cd ~
NataliKoren@ubuntuserver:~$
```
```console
NataliKoren@ubuntuserver:~/tmp1/tmp2_1$ cd ~
NataliKoren@ubuntuserver:~$ cd ..
NataliKoren@ubuntuserver:/home$ cd /home/NataliKoren/tmp1/tmp2
NataliKoren@ubuntuserver:~/tmp1/tmp2$ cd /home/NataliKoren/tmp1/tmp2
```

## Перечислить, какие параметры команды cd позволят быстро вернуться в домашний каталог, позволят перейти на уровень выше.
### быстро вернуться в домашний каталог
```console
NataliKoren@ubuntuserver:~/tmp1/tmp2_1$ cd ~
NataliKoren@ubuntuserver:~$
```
### позволят перейти на уровень выше.
```console
NataliKoren@ubuntuserver:~/tmp1/tmp2/tmp 3$ cd ..
NataliKoren@ubuntuserver:~/tmp1/tmp2$
```

# 2. Управление файлами и каталогами и текстовые редакторы. 
## Создать файл с наполнением, используя несколько способов. 
```console
NataliKoren@ubuntuserver:~/tmp1$ cat>file1
asd
qwe
^C
NataliKoren@ubuntuserver:~/tmp1$ cat file1
asd
qwe
```
```console
NataliKoren@ubuntuserver:~/tmp1$ echo asf wqe as dfa > file2
NataliKoren@ubuntuserver:~/tmp1$ cat file2
asf wqe as dfa
```
```console
NataliKoren@ubuntuserver:~/tmp1$ echo "lalala lalal" > file3
NataliKoren@ubuntuserver:~/tmp1$ cat file3
lalala lalal
```

## Использовать разобранные текстовые редакторы для наполнения файлов данными. 

### nano
```console
NataliKoren@ubuntuserver:~/tmp1$ nano file4
```
[![imageup.ru](https://imageup.ru/img200/3634267/snimok-ehkrana-2020-07-23-v-142846.jpg)](https://imageup.ru/img200/3634267/snimok-ehkrana-2020-07-23-v-142846.jpg.html)
```console
NataliKoren@ubuntuserver:~/tmp1$ cat file4
asffffwf
faafssfa
gasg
asg
waw

```

### vim
```console
NataliKoren@ubuntuserver:~/tmp1$ vim file5
```
[![imageup.ru](https://imageup.ru/img152/3634269/snimok-ehkrana-2020-07-23-v-143305.jpg)](https://imageup.ru/img152/3634269/snimok-ehkrana-2020-07-23-v-143305.jpg.html)
```console
NataliKoren@ubuntuserver:~/tmp1$ cat file4
lala
fasf
wr
```

## Создать копии созданных файлов, создать несколько каталогов с подкаталогами, перенести несколько файлов в созданные каталоги. 
```console
NataliKoren@ubuntuserver:~/tmp1$ cp file4 file4_copy
NataliKoren@ubuntuserver:~/tmp1$ cp file5 file5_copy
```
```console
NataliKoren@ubuntuserver:~/tmp1$ mkdir -p tmp3/tmp4
NataliKoren@ubuntuserver:~/tmp1$ mkdir /tmp/tmp5
```
```console
NataliKoren@ubuntuserver:~/tmp1$ mv file4_copy tmp3/tmp4
NataliKoren@ubuntuserver:~/tmp1$ ls tmp3/tmp4
file4_copy
NataliKoren@ubuntuserver:~/tmp1$ mv file5_copy /tmp/tmp5
NataliKoren@ubuntuserver:~/tmp1$ ls /tmp/tmp5
file5_copy
```
