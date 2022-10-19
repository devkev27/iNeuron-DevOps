### Linux Basic Commands Assignment

1. Create a file like nano **file1.txt**
	* edit some data and then save the file

```bash
nano file1.txt
ls
file1.txt
```

```nano
This a new file
```

2. Now we will copy data from file1 to a new file2
	* ``cp file1.txt file2.txt``
	* Then see the output of file2.txt, ``cat file2.txt``

```bash
cp file1.txt file2.txt
cat file2.txt
This is a new file
```

3. Now we will move the file2.txt to a new folder ``/home``
	* ``mv file2.txt /home``
	* Then go to **home** directory and check **ls**, does the file exist or not?

```bash
$ mv file2.txt /home
mv: cannot move 'file2.txt' to '/home/file2.txt': Permission denied
$ sudo mv file2.txt /home
[sudo] password for kev:
$ cd /home
$ /home$ ls
file2.txt
```

4. Create a new **file3.txt and file4.txt** in **home directory** and add content in it.
	* Now do ``echo "Hello I am a new line">file3.txt`` and provide the output of file3.txt

```bash
sudo touch file3.txt file4.txt
sudo nano file3.txt
```

```nano
This is the first line
```

```bash
sudo nano file4.txt
```

```nano
This is the first line
```

```bash
$ sudo echo "Hello I am a new line" > file3.txt
bash: file3.txt: Permission denied
```

echo as expected led to a permission denied error, however surprisingly ``sudo echo 'Hello I am a new line' > file3.txt`` also will not work. I came to find out this is because the redirection ``> or >>`` is not executed by sudo echo but by the current user's shell. As we are not running as root user, permission will be denied. One way to address this is become root user however another way is to use ``echo "Hello I am a new line" | sudo tee file3.txt`` instead.

```bash
$ echo "Hello I am a new line" | sudo tee file3.txt
Hello I am a new line
$ cat file3.txt
Hello I am a new line
```

This gives us the output of file3.txt that we were looking for

* now do ``echo "Hello I am a new line" >> file4.txt`` and provide the output of file4.txt
Instead of this we shall use ``echo "Hello I am a new line" | sudo tee -a file4.txt``

```bash
$ echo "Hello I am a new line" | sudo tee -a file4.txt
Hello I am a new line
$ cat file4.txt
This is the first line
Hello I am a new line
```

The difference between using >  (``tee``) and using >> (``tee -a``) 
- With ``>`` you overwrite data of an existing file or create a new file when it isn't already there in the directory. Whereas with
- With ``>>`` you append to existing data already on the file or you create a new file if that file does not already exist in the directory
- These operators are often used together when modifying files in Linux

5. Remove a file or directory using the two commands below
	* To delete a file ``-rm <any_filename>``
	* To delete a directory ``-rmdir <any_directoryname>``

```bash
$ sudo rm file2.txt file3.txt file4.txt
$ sudo mkdir test
$ sudo rmdir test
```

All text files created have been removed and a test directory created also got removed
