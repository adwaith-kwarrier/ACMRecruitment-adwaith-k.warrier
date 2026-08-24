Level 0 -> Level 1
ssh bandit0@bandit.labs.overthewire.org -p 2220
ls, cat
Password: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR

Level 1 -> Level 2
cat./- [./ means current directory]
If a file has - as the name, specify current directory using ./ This acts like an escape sequence here.
Password: PK8fYLZg2hnHSz83plBL1iEPKdD3QToB

Level 2 -> Level 3
If the filename consists of spaces, specify it in double quotes. If it contains -- (double dashes), use a -- before the file name. This tells the terminal to look for filenames only after that point.
Password: 7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME

Level 3 -> Level 4
To view all hidden files, use ls -a The . and .. shown with the file name indicate the current directory and parent directory respectively.
Password: xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq

Level 4 -> Level 5
To view the types of each file use 'find *' command. Since the file names star with -f, the terminal mistakes it as a a part of a command, so to run it properly, use './*'. Then use 'cat -- <file_name>' to display the contents of the file.
Password: 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

Level 5 -> Level 6
To search through the entire directory, use 'find . -size 1033c ! -executable' command. The '.' checks every file in the current directory, 1033c checks for files having exactly 1033 bytes (c means bytes) and ! -executable looks for non-executable files (! means not). Also used 'file <output_file>' to ensure that the file given was ASCII, human readable.
Password: pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

Level 6 -> Level 7
Used the command 'find / -size 33c -user bandit7 -group bandit6' to check the requirement. A lot of hidden files with denied permission popped up. Found the pathname '/var/lib/dpkg/info/bandit7.password'. USed the cd command with the path name to find the password.
Password: Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

Level 7 -> Level 8
Used the command 'grep "millionth' data.txt' to print the line containing the word 'millionth'.
Password: VR1ljMayciFxbnUokuQmJFw6QC9VKtub



