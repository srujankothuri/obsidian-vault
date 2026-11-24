
**Your original list**

1. ls - lists the files and folders in the current directory
2. pwd - prints the current directory you are in
3. mkdir - creates a new directory
4. rmdir - removes an empty directory
5. cd - changes directory
6. mv - moves a file elsewhere (also used to rename)
7. cp - copies a file
8. touch - creates a new empty file (or updates a file's timestamp)
9. man - manual pages
10. ps - shows which processes are running
11. echo - prints a line of text
12. whoami - prints which user you are logged in as
13. sort - sorts lines of text
14. cat - concatenates files and prints them to standard output
15. nl - outputs a file with line numbers
16. cut - removes sections from each line of a file
17. grep - prints lines that match a pattern

**Viewing and inspecting files**  
18. less - scrolls through a file page by page (`q` to quit)  
19. more - older, simpler pager than less  
20. head - shows the first lines of a file (`head -n 20 file`)  
21. tail - shows the last lines of a file; `tail -f` follows it live  
22. wc - counts lines, words, and bytes (`wc -l file`)  
23. file - tells you what type a file is  
24. diff - compares two files line by line  
25. stat - shows detailed file info (size, permissions, timestamps)

**Text processing**  
26. uniq - removes or counts duplicate adjacent lines (use after sort)  
27. tr - translates or deletes characters  
28. sed - stream editor, mostly for find-and-replace  
29. awk - processes text by columns and fields  
30. xargs - builds arguments for another command from input

**Finding things**  
31. find - searches for files by name, type, size, or date  
32. which - shows the path of a command  
33. type - shows whether something is a builtin, alias, or program  
34. locate - fast filename search using an index

**Permissions and ownership**  
35. chmod - changes file permissions  
36. chown - changes file owner  
37. sudo - runs a command as the superuser  
38. umask - sets default permissions for new files

**Files, links, and archives**  
39. rm - deletes files (`rm -r` for directories, use carefully)  
40. ln - creates links (`ln -s` for symbolic links)  
41. tar - bundles files into an archive (and extracts them)  
42. gzip / gunzip - compresses and decompresses files  
43. zip / unzip - creates and extracts .zip archives

**Processes and system**  
44. top - live view of processes and CPU/memory use  
45. htop - friendlier, interactive version of top  
46. kill - sends a signal to a process (usually to stop it)  
47. pkill / killall - kills processes by name  
48. jobs - lists background jobs in the current shell  
49. bg / fg - moves a job to the background or foreground (`Ctrl+Z` suspends)  
50. df - shows disk space per filesystem (`df -h`)  
51. du - shows disk usage of files and directories (`du -sh`)  
52. free - shows memory usage (`free -h`)  
53. uname - prints system and kernel info (`uname -a`)  
54. history - lists your previous commands

**Networking and remote work**  
55. ssh - logs into a remote machine  
56. scp - copies files between machines  
57. rsync - syncs files efficiently, locally or remotely  
58. curl - transfers data from or to a URL  
59. wget - downloads files from the web  
60. ping - checks if a host is reachable

**Shell environment**  
61. env - shows environment variables  
62. export - sets an environment variable for child processes  
63. alias - creates shortcuts for commands  
64. clear - clears the terminal screen

**Development and systems**  
65. gcc - compiles C programs  
66. make - runs build rules from a Makefile  
67. gdb - debugs programs step by step  
68. valgrind - finds memory leaks and invalid memory access  
69. objdump - disassembles compiled binaries  
70. strace - traces the system calls a program makes