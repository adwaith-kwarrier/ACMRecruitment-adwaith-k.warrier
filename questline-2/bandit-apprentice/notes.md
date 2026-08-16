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


