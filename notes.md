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

# navigating through directory history
- we use pushd to change to the directory instead of cd.
- using popd will then send you back to those directory.

# Working with files
## viewing files
* cat - Used for viewing files that are not very long; it does not provide any scroll-back.
* tac - Used to look at a file backwards, starting with the last line.
* less - Used to view larger files because it is a paging program. It pauses at each screen full of text, provides scroll-back capabilities, and lets you search and navigate within the file.
- NOTE: Use / to search for a pattern in the forward direction and ? for a pattern in the backward direction. An older program named more is still used, but has fewer capabilities: "less is more".
* tail - Used to print the last 10 lines of a file by default. You can change the number of lines by doing -n 15 or just -15 if you wanted to look at the last 15 lines instead of the default.
* head - The opposite of tail; by default, it prints the first 10 lines of a file.

## Searching Files
* stdin -> 0
* stdout -> 1
* stderr -> 2

## Wildcards and Matching Filenames
* ? -> Matches any single character
* * -> Matches any string of characters
* [set] -> Matches any character in the set of characters, for example [adf] will match any occurrence of a, d, or f
* [!set] -> Matches any character not in the set of characters

## Using advanced find option
- find is able to run commands on the files that match your search criteria.
- The -exec option is used for this purpose.
- To find and remove all files that end with .swp:
* $ find -name "*.swp" -exec rm {} ';'
- you have to end the command with either ';' (including the single-quotes) or \;. Both forms are fine.
- One can also use the -ok option, which behaves the same as -exec, except that find will prompt you for permission before executing the command. 

# Linux documentation Resources
## man pages
* man -f = whatis
* man -k = apropos
