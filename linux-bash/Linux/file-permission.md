# File-permission

### Introduction - Why is file permission required?

In general, many people can connect to one Linux server and work on their own tasks or work together. If all user shares the same files and directories, it's a potential risk of data loss or changes due to others' needs. Although the user may not have intended it, it can seriously interfere with their work by fixing or erasing files that are important to others, and in severe cases, it can move the location of some of the files needed by the system, preventing the system from locating them, causing the system to stop completely. Thus, our system needs a barrier system that blocks others from disturbing others' jobs. This is why file permission is required

### Linux File Permission

To check File permission, the easiest way is to list files within the current directory.

```bash
ls -lh
```

<pre><code><strong>-rw-r--r--   12   BJKIM   KIMGROUP     12.0K   Nov 29  10:10 my_File
</strong>|[-][-][-]- [-]   [----]  [-------]    [----]  [----]  [---] [------]
| |  |  | |  |    |       |            |       |       |     |
| |  |  | |  |    |       |            |       |       |     +-> 12. File Name
| |  |  | |  |    |       |            |       |       +-------> 11. time
| |  |  | |  |    |       |            |       +---------------> 10. date
| |  |  | |  |    |       |            +----------------------->  9. File Size
| |  |  | |  |    |       +------------------------------------>  8. Group
| |  |  | |  |    +-------------------------------------------->  7. Owner
| |  |  | |  +------------------------------------------------->  6. # links
| |  |  | +---------------------------------------------------->  5. Alternate Access Method
| |  |  +------------------------------------------------------>  4. Others Permissions
| |  +--------------------------------------------------------->  3. Group Permissions
| +------------------------------------------------------------>  2. Owner Permissions
+-------------------------------------------------------------->  1. File Type</code></pre>

The output of each line of `ls -l` gave us information about each file within your current directory. The first column consisting of 10 letters, `-rw-r--r--` is file type and file permission and followed by Alternative access method, #link, ower user id, group, file size, date, time, and file name.

#### 1. File type

The file type is literally the type that indicates that a given file is a directory, regular file, or link.

* `d`: directory
* `-`: regular file
* `l`: Symbolic link -&#x20;

2\. Ower/Group/Others permission

