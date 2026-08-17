# Hard Links
- created using "ln"
- Suppose that file1 already exists. A hard link, called file2, is created with the command:
* ln file1 file2
- listing the files together with an inode number:
* ls -li file1 file2
- the two files will have the same inode number
- Points directly to the raw data. 
- Cannot link to folders or cross over to different hard drives.
- Survives if the original file is deleted.

# Soft Links
- created using "ls -s"
* ln -s file1 file3
- file3 will not appear to be a regular and will point to file1 (file3 -> file1) when listed:
* ls -li file1 file3
- Points to a filename.
- Can link to folders and cross over to different hard drives/partitions.
- Breaks if the original file is deleted.
