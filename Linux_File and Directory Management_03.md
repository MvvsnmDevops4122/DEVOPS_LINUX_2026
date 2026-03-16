## 📂 File and Directory Management in Linux

---

## 1🔹 Listing & Checking Location of Files and Directories

| Command | Description |
|----------|-------------|
| `ls` | List files and directories |
| `ls -l` | Display detailed info (permissions, owner, size, etc.) |
| `ls -a` | Show hidden and normal files/folders (starting with `.`) |
| `ls -lh` | Human-readable sizes (KB, MB, etc.) |
| `ls -lr` | Show files in reverse order |
| `ls -lt` | Sort by modification time (newest to oldest) |
| `ls -i` | Show inode numbers |
| `ls -lrthai` | All-in-one view (detailed, reverse, time, human-readable, inode) |
| `pwd` | Show current working directory |

---

## 2🔹 Change Directories Commands

| Command | Description |
|----------|-------------|
| `cd /path` | Go to a specific directory |
| `cd` | Go to home directory |
| `cd -` | Go to previous directory |
| `cd ../` | Move one directory back |
| `cd ../../` | Move two directories back |

---

## 3🔹 Display Directory Structure

| Command | Description |
|----------|-------------|
| `tree` | Show directory structure in tree format |

---

## 4🔹 Creating Files & Directories Commands

| Command | Description |
|----------|-------------|
| `touch filename` | Create an empty file |
| `touch one two three` | Create multiple empty files |
| `mkdir -v foldername` | Create a directory (verbose output) |
| `mkdir folder1` | Create a single directory |
| `mkdir fold1 fold2 fold3` | Create multiple directories |
| `mkdir -p parent/child1/child2/child3` | Create nested directories |

---

## 5🔹 Removing Files & Directories Commands

| Command | Description |
|----------|-------------|
| `rm filename` | Remove an empty file |
| `rm *` | Remove all files in the current directory |
| `rm -rf` | Force remove non-empty files/directories |
| `rmdir foldername` | Remove an empty directory |
| `rmdir *` | Remove all empty directories |
| `rm -rf foldername` | Remove non-empty directories/files |

---

## 📋 Copy / Move / Rename Files and Directories

### 6🔹 Copy Files or Directories (`cp`)

| Command | Description |
|----------|-------------|
| `cp devops.txt DevOps/` | Copy file → directory |
| `cp -r Python DevOps/` | Copy directory → directory (recursively) |
| `cp file1.txt file2.txt` | Copy file → file |
| `cp *.java destination_dir/` | Copy all `.java` files to a directory |

---

### 7🔹 Move or Rename (`mv`)

| Command | Description |
|----------|-------------|
| `mv python.txt devops.txt` | Rename file |
| `mv DevOps/ Python/` | Move directory |

---

## 8.🔍 File Comparison

### 🔹 View Files Page-by-Page (`more`)

```bash
more file1 file2
````

**Example Output:**

```
::::::::::::::
file1
::::::::::::::
Hello file one
Thanks for joining
::::::::::::::
file2
::::::::::::::
Hello file two
Thanks for joining
```

---

### 🔹 Compare Files Line-by-Line (`diff`)

| Command               | Description                    |
| --------------------- | ------------------------------ |
| `diff file1 file2`    | Compare two files line-by-line |
| `diff -y file1 file2` | Show side-by-side comparison   |

**Example:**

```
diff file1 file2
< Hello file one
---
> Hello file two
```

---

## 9.🧾 View / Create / Append / Copy / Merge Files (cat Command)

| Command                       | Description                              |
| ----------------------------- | ---------------------------------------- |
| `cat file.txt`                | View contents of a file                  |
| `cat file1 file2`             | View multiple files                      |
| `cat > newfile.txt`           | Create a new file (press Ctrl+D to save) |
| `cat >> existingfile.txt`     | Append content to an existing file       |
| `cat file1 file2 > merge.txt` | Merge two files into a new file          |
| `cat -n file.txt`             | Show file content with line numbers      |
| `tac file.txt`                | Show file content in reverse order       |

---

## 10. Nullifying a file

```bash
> file.txt                         # clearing its content without deleting the file itself.
```
---

## 11. head (View First N Lines of a File)

Description: The head command displays the first few lines of a file.

Usage:
```bash
head file.txt  # Show first 10 lines
head -n 3 file.txt  # Show first 3 lines
head -3 file.txt  # Alternative syntax
```
Display Specific Line Range (35-50) from a 100-Line File:

```bash
head -50 file.txt | tail -15
```
---

 ## 12. tail (View Last N Lines of a File)
 
Description: The tail command displays the last few lines of a file.

Usage:

```bash
tail file.txt  # Show last 10 lines
tail -n 3 file.txt  # Show last 3 lines
tail -3 file.txt  # Alternative syntax
```
Multiple Files:

```bash
tail file1.txt file2.txt  # Show last 10 lines of both files
tail -q file1.txt file2.txt  # Suppress headers while displaying output
tail -f app.log         # Display live logs 
```
---
## 13. sort (Sort File Content)

Description: The sort command arranges lines of text in a specified order.

Usage:
```bash
sort file.txt  # Alphabetical sort
sort -r file.txt  # Reverse order sort
sort -k 2 data.txt  # Sort based on second column
sort -u file.txt  # Remove duplicate lines
```
---

## 14. grep (Search for Patterns in Files)

Description: The grep command searches for text patterns in a file.

Usage:
```bash
grep "UNIX" abc.txt  # Case-sensitive search
grep -i "UNIX" abc.txt  # Case-insensitive search
grep -c "UNIX" abc.txt  # Count occurrences
grep -l "UNIX" *  # Show files containing 'UNIX'
grep -w "UNIX" abc.txt  # Match whole words only
```

Advanced Searching:

```bash
grep -o "UNIX" abc.txt  # Show only matching content
grep -n "UNIX" abc.txt  # Show line numbers
grep -v "UNIX" abc.txt  # Show lines that do NOT match
```

Context Search:

```bash
grep -B5 "error" demo.txt  # Show 5 lines *before* match
grep -A5 "error" demo.txt  # Show 5 lines *after* match
grep -C5 "error" demo.txt  # Show 5 lines *before & after*
grep -iE "error | error1 " # Shows two text in same file.
```
---

## 15. wc (Word Count)

Description: The wc command counts lines, words, bytes, and characters in a file.

Usage:

```bash
wc file.txt  # Show line, word, and character count
wc -l file.txt  # Count number of lines
wc -w file.txt  # Count number of words
wc -c file.txt  # Count number of bytes/characters
```
---

## 16. id & groups (User & Group Information)

Description: The id command provides detailed user information (UID, GID, groups).

The groups command displays all groups a user belongs to.

Usage:

```bash
id
id username
groups
```
---
## 17.tr Command (Translate Characters)

```bash
cat demo.txt | sort | tr [a-z] [A-Z]  # Converts lowercase to uppercase

cat demo.txt | sort | tr [A-Z] [a-z]   # Converts Uppercase to Lowercase
```
---
## 18. nano Editor

A beginner-friendly text editor in Linux.

```bash
nano demo.txt
sudo yum install nano -y     # Install nano if not available
```
Commands
Ctrl+O → Save
Ctrl+X → Exit

----

## 19. find Command (Search Files & Directories)

The `find` command in Linux is used to **search for files and directories** based on different conditions like name, type, size, permissions, or modification time.

```bash
find . -name filename/foldername            -> Search by file or folder name current directory(Case-sensitive)

find . -name filename/foldername            -> Search by file or folder name current directory(Case-insensitive)

find . -type f                              -> Search list of the files in current directory

find . -type d                              -> Search list of the folder in current directory

find . -type f -empty                       -> Find empty files in current directory

find . -type f ! -empty                     -> Find non empty files in current directory

find . -type d -empty                       -> Find empty folders in current directory

find . -type d ! -empty                     -> Find non empty folders in current directory

find ~ -type f -empty                       -> Find empty files in home directory

find /tmp -type f -empty                    ->  Find empty files in /tmp

find . -perm 777                            -> search files or folders based on permission.

find . -mtime 1                             -> Modified exactly 1 day ago

find . -mtime -1                            -> Modified less than 1 day ago

find . -mtime +1                            -> Modified more than 1 day ago

find . -type f -empty -delete               -> Delete All Empty Files

touch -d "2 days ago"  filename             -> Modify file date
 
````
----

## 20.sed Command (Stream Editor): 

sed reads a file line-by-line and allows you to replace, delete, or print specific parts of text without opening the file manually

```bash
sed 's/unix/linux/' abc.txt                -> Replace first occurence(Every line)

sed 's/unix/linux/2' abc.txt               -> Replace 2nd occurence

sed 's/unit/linux/g' abc.txt               -> Replace all occurence

sed '3 s/unix/linux/' abc.txt              -> Replace on line 3

sed '1,3 s/unix/linux/' abc.txt            -> Replace in line range

sed '5d' filename.txt                      -> Delete line 5

sed '3,6d' filename.txt                    -> Delete lines 3 to 6

sed -n '60,80p' filename                   -> To display lines 60 to 80 of a file using sed

(-n prevents printing all lines.)

 sed -n '2 s/am/was/p' sample.txt          -> To replace word and display line no 2 only

 sed -n '1 s/unix/linux/gp' sample.txt     -> Replace all unix with linux on line and print line same.

```
---

