# Find command

The general syntax for the find command is:

    find [directory to search] [options] [expression]

#### simple example:

    find . -type f -name myfile

This command will run a search in the `current directory` and `its subdirectories` to find a file (not directory) named `myfile`. The option `-type f` asks it to look for `files only`. The single dot `.` means the `current directory`.

### Find files and directories by name

    find . -name SEARCH_NAME

### Find only files or only directories

If you only want to look for files, specify file type -f:

    find . -type f -name SEARCH_NAME

If you only want to search for directories, specify type -d:

    find . -type d -name SEARCH_NAME

### Run a case-insensitive search

    find . -type f -iname SEARCH_NAME

### Search files by their extension (important)

    find . -type f -name "*.txt"

### Search for multiple files with multiple extensions (or condition)

using the `-o` option that works as logical `OR` condition:

    find . -type f -name "*.cpp" -o -name "*.txt" 

### Look for files in specific directory

    find ./directoty_path -name mystuff 

### Search for files in multiple directories

    find ./location1 /second/location -type f -name "pattern"

### Find empty files and directories

    find . -empty
          or
    find . -empty -type f

### Find big files or small (Search based on file size)

Find files of exactly size:

    find . -size 50k

To search for files bigger than given size in the current directory:

    find . -size +1G

To find smaller than given size:

    find . -size -20c

To find files bigger than given size but smaller than other size:

    find . -size +100M -size -2G

You may also combine the size search with the name search. For example, to search for all files with name ending in .log but size greater than 500 MB in the root directory, you can use:

    find / -size +500M -name "*.log"

#### Size

```html
c : bytes
k: kilobytes
M: Megabytes
G: Gigabytes
```

### Find recently modified files (Search based on modify or creation time)

The concept of `mtime, atime and ctime`

    mtime: last modification time of file
    ctime: creation time of the file
    atime: last access time of the file


To find all the files modified within `3 days (3*24H)`, use:

    find . -type f -mtime -3

To find all the files created `at least 5 days (5*24H) ago`, use:
    
    find . -type f -ctime +5

Want to search for files that were modified only a few minutes ago? For that, you can use `mmin, amin and cmin`.

To find all the files that were modified in the last 5 minutes, use:

    find . -type f -mmin -5

You can specify upper and lower limits along with the search name. The command below will search for all the .java files that have been modified between last 20 to 30 minutes.

    find . -type f -mmin +20 -mmin -30 -name "*.java"

### Find files with specific file permissions

The find command allows you to search for files with specific file permission and access mode.

    find -perm mode

For example, to find all the files access mode 777 in the current directory;

    find . -perm 777

To find all files with access of read and write for all (exact match, it won't match if the file has execute permission for all):

    find . -perm a=r+w

### Find files owned by a user

to find files owned by the user John in the current directory, use:
    
    find . -type f -user John

You can also combine it with other options like size, time and name:

    find . -type f -user John -name "*.cpp"

### Don't find recursively, search only in current directory

    find . -maxdepth 1 -type f -name "*.txt"

### Exclude a directory from search

    find . -path "./directory_exclude/*" -prune -o -name SEARCH_NAME

### 