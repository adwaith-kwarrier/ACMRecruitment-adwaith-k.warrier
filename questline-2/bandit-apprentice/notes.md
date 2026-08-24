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
Used the command 'find / -size 33c -user bandit7 -group bandit6' to check the requirement. A lot of hidden files with denied permission popped up. Found the pathname '/var/lib/dpkg/info/bandit7.password'. Used the cd command with the path name to find the password.
Password: Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3

Level 7 -> Level 8
Used the command 'grep "millionth' data.txt' to print the line containing the word 'millionth'.
Password: VR1ljMayciFxbnUokuQmJFw6QC9VKtub

Level 8 -> Level 9
To find unique lines, use the 'uniq -u' command. This command takes an input and checks if the lines are unique, if so, the lines will be in the output. The problem with 'uniq -u' is that it only checks if the line is a duplicate of the immediate previous or next line. So to use this function properly, we have to sort the given data.txt first. For that, we use the 'sort data.txt | uniq -u' command. The pipe (|) symbol takes the output of the sort and gives it to the uniq -u command
Password: EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl

Level 9 -> Level 10
The file contains a mix of binary and human readable characters. The 'strings data.txt' command outputs the human readble part. This as the input to the grep '===' gives the password as the ouput. Connecring those two with pipe (|) maintains the logical flow in a single command.
Password: B0s2khmbT9u0geKuOoVGW3JZKhndE3BG

Level 10 -> Level 11
The given text file is encrypted in base64. Used the 'base64 -d <file_name>' command to decrypt it and get the password as output.
Password: pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro

Level 11 -> Level 12
The given file is encrypted using ROT13. To read the entire file and translate it, "cat <file_name> | tr 'a-zA-Z' 'n-za-mN-ZA-M'" is used.  The tr command stands for translate. The first parameter of the command is the actual set of letters to be translated, that is all alphaets uppercase and lowercase. It is translated to 'n-za-mN-ZA-M', which means all the letters from n to m through z and a, including uppercase letters. The password is obtained as the output.
Password: GROozWPO8QyN0mGrjUkID0WCYkZiQxrN


Level 12 -> Level 13
The given file was compressed several times. Used gzip -d, bzip2 -d, tar xf alogng with .gz, .bz2 and .tar extensions.
Password: qQYQiHOBPR8zR61qxYqX45quvihF2uzk



