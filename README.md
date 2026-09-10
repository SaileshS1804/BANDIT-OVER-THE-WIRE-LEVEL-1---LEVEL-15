# BANDIT-OVER-THE-WIRE-LEVEL-1-TO-LEVEL-15
Bandit is the standard entry-level wargame for learning Linux command-line navigation, system administration fundamentals, basic privilege escalation, and shell scripting.


Level 0:

    1. The goal of the level 0 is to make you to login to the game server using SSH.
    2. You need to connect to the host.
    3. It is the first step for the bandit over the wire game.
    4. Password: bandit0
   
code:

ssh bandit0@bandit.labs.overthewire.org -p 2220

Expansion Of Code:

  1. ssh:

    It is the program this creates a secure, encrypted terminalsession over a network.

  2. bandit0:

    It is the user account name in the remote server.

  3. @:

    Delimiter that separates the user from host server.
  
  4. bandit.labs.overthewire.org:

    Target servers domain adddress.

  5.-p 2220:

    Specifies the port 2220.

Result Of Level 0:

  1. It login's into the game server.


<img width="1047" height="885" alt="level 0 to 1" src="https://github.com/user-attachments/assets/223f9e6c-6a79-44a1-b6fe-eb5367020f59" />



Level 0 --> Level 1:

    1. This levels helps you find the password to open the next level.
     
    2. it uses simple line of code.

Code:
  
  ls:
  
    Display all non-hidden files and folder in current directory.


  cat readme:

    Reads the readme file and prints its raw text content into terminal window.


Result:

  1. Give the password for the next level.


     <img width="1192" height="305" alt="level 1" src="https://github.com/user-attachments/assets/4f954ab1-09e9-4e87-92e2-2f07335f3f82" />



Level 1 --> Level 2:

    1. The password for the next level is stored in a file called - located in the home directory.
    
    2. it uses simple line of code.

Code:

  ssh bandit1@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH terminal connection as user bandit1 on port 2220.

  ls:

    Lists the files in the home directory. The output shows a single file whose name is literally -.

  cat ./-:

    Reads the contents of the - file.

    Running cat - causes the command to wait for keyboard input because - represents standard input (stdin). Adding ./ forces cat to recognize - as a file in the current folder.

  exit:

    Disconnects from the bandit1 remote server session.

Result:

    1. It give the password of the next level.


<img width="1092" height="817" alt="level 1 to 2" src="https://github.com/user-attachments/assets/49867034-0dcf-4f7f-8f12-34ceeaed4163" />


<img width="545" height="165" alt="level 2" src="https://github.com/user-attachments/assets/29cda134-63e4-4bbb-af7a-58f7babc0d9c" />


Level 2 --> Level 3:

    1. The password for the next level is stored in a file called --spaces in this filename-- located in the home directory.

Code:

  ssh bandit2@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH terminal connection as user bandit2 on port 2220.

  ls:

    Lists directory contents, displaying the file named --spaces in this filename--.

  cat -- "--spaces in this filename--":

    Reads the contents of the file.

  Quotes ("..."):
  
    Keep words separated by spaces treated as a single filename rather than separate arguments.

  Double Dash (--): 

    Signals the end of command-line flags. Without --, cat tries to interpret --spaces as an invalid command option and throws an error.

  exit:

    Disconnects from the bandit2 remote server session.


Result:

    1. It give the password of the next level.


<img width="960" height="816" alt="level 2 to 3" src="https://github.com/user-attachments/assets/c1990323-85d4-418b-be69-87edc26c6bf5" />


<img width="960" height="816" alt="level 2 to 3" src="https://github.com/user-attachments/assets/38fd764d-acad-4c51-b259-2da8a14e30d1" />


Level 3 --> Level 4:
      
    1. The password for the next level is stored in a hidden file in the inhere directory.


Code:
  ssh bandit3@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH connection as user bandit3 on port 2220.

  ls -a inhere:

    Lists all contents inside the inhere folder.

  -a (all): 
  
    Reveals hidden files. In Linux, any file or directory starting with a dot (.) is hidden by default.

  cat inhere/...Hiding-From-You:

    Reads and displays the contents of the hidden file ...Hiding-From-You located in the inhere directory.

  exit:

    Disconnects from the bandit3 remote server session.

Result:

    1. It give the password of the next level.


<img width="960" height="702" alt="level 3 to 4" src="https://github.com/user-attachments/assets/70a9ae49-c186-4e52-aa65-33805651e490" />


<img width="687" height="160" alt="level 4" src="https://github.com/user-attachments/assets/bb6746d0-54d9-4940-99b4-9139b2104b4c" />


Level 4 --> Level 5:

    1. The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

Code:

  ssh bandit4@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH terminal session as user bandit4 on port 2220.

  file inhere/*:

    Inspects the file type of every file in the inhere folder.

  file: 
  
    Scans the file contents to tell you what type of data it holds, rather than relying on file extensions.

    The command output identifies inhere/-file07 as ASCII text (human-readable), while the rest are binary data or keys.

  cat inhere/-file07:

    Reads and displays the contents of the readable text file (-file07), revealing the password.

  exit

    Disconnects from the bandit4 remote server session.


Result:
    
    1. It give the password of the next level.


<img width="1047" height="895" alt="level 4 to 5" src="https://github.com/user-attachments/assets/fc0017b0-2736-499c-8c23-9137d2f00218" />


<img width="732" height="312" alt="level 5" src="https://github.com/user-attachments/assets/4891227d-4776-4110-8a33-d902de7d44f4" />


Level 5 --> Level 6:

    1. The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

                                human-readable
                                1033 bytes in size
                                not executable


Code:

  ssh bandit5@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH connection as user bandit5 on port 2220.

  find -readable -size 1033c

      Recursively searches all folders starting from your current location for files matching specific criteria.

  -readable:
  
      Filters for files your current user account has permission to read.

  -size 1033c:
  
      Filters for a file size of exactly 1033 bytes (the c suffix specifies bytes in find).

  Output points directly to ./inhere/maybehere07/.file2.

  cat ./inhere/maybehere07/.file2:

      Reads and displays the password stored inside .file2.


Result:
    
    1. It give the password of the next level.


<img width="1031" height="896" alt="level 5 to 6" src="https://github.com/user-attachments/assets/f6ac66af-38be-47f4-8e4d-04f4b75ee9cb" />


<img width="482" height="80" alt="level 6" src="https://github.com/user-attachments/assets/ed0b0197-48dd-4864-8109-6d1813e0a2a4" />



Level 6 --> Level 7:

    1. The password for the next level is stored somewhere on the server and has all of the following properties:

                                          owned by user bandit7
                                          owned by group bandit6
                                          33 bytes in size


Code:
  ssh bandit6@bandit.labs.overthewire.org -p 2220:

      Opens an encrypted SSH connection as user bandit6 on port 2220.

  find / -user bandit7 -group bandit6 -size 33c 2>/dev/null -exec cat {} +:

      Searches the entire file system and automatically prints the contents of the matching file.

  /: 

      Starts the search at the root directory.

  -user bandit7: 

      Filters for files owned by user bandit7.

  -group bandit6:
  
      Filters for files belonging to group bandit6.

  -size 33c:
      
      Filters for a file size of exactly 33 bytes (c specifies bytes).

  2>/dev/null:
      
      Mutes "Permission denied" errors by redirecting standard error (2>) to the black hole device (/dev/null).

  -exec cat {} +:
    
      Automatically runs cat on any matching file found without needing to copy the path manually.

  exit:

    Disconnects from the bandit6 remote server session.



Result:
    
    1. It give the password of the next level.


<img width="827" height="646" alt="level 6 to 7" src="https://github.com/user-attachments/assets/0219dc56-f8f6-4182-a0c7-a3813088d53d" />


<img width="881" height="67" alt="level 7" src="https://github.com/user-attachments/assets/e666dffc-2488-4c4f-b226-157375bd3078" />


Level 7 --> Level 8:

    1. The password for the next level is stored in the file data.txt next to the word millionth

Code:
  ssh bandit7@bandit.labs.overthewire.org -p 2220:

    Opens an encrypted SSH terminal connection as user bandit7 on port 2220.

  grep "millionth" data.txt:

    Searches the file data.txt line-by-line and prints only the lines containing the target word.

  grep: 
  
      A standard command-line utility used to search plain-text datasets for matching string patterns or regular expressions.

  "millionth":
  
      The specific search term supplied to match the text pattern.

  data.txt:
  
      The target file containing thousands of data entries.

  exit:

      Disconnects from the bandit7 remote server session.


Result:
    
    1. It give the password of the next level.


<img width="1082" height="832" alt="level 7 to 8" src="https://github.com/user-attachments/assets/43e6234a-937a-4668-91ce-91053c2bd15e" />


<img width="522" height="66" alt="level 8" src="https://github.com/user-attachments/assets/1edc7684-5931-4c7e-b548-f80e70dcc812" />



Level 8 --> Level 9:
    
    1. The password for the next level is stored in the file data.txt and is the only line of text that occurs only once.

Code:
  ssh bandit8@bandit.labs.overthewire.org -p 2220:

      Opens an encrypted SSH connection as user bandit8 on port 2220.

  ls:

      Lists directory contents, confirming data.txt is present.

  sort data.txt | uniq -u:

      Sorts the text file and filters out all repeated lines to display the single unique line.

  sort data.txt: 
  
      Alphabetizes all lines in data.txt. This step is mandatory because uniq only compares adjacent lines.

  | (Pipe):
  
      Passes the sorted stream from sort directly into the uniq command.

  uniq -u: 
  
      Filters the stream to display only lines that are non-repeated.


Result:
    
    1. It give the password of the next level.


<img width="772" height="642" alt="level 8 to 9" src="https://github.com/user-attachments/assets/41519a22-5c79-4580-bfa1-ba6e431ee47e" />


<img width="445" height="87" alt="level 9" src="https://github.com/user-attachments/assets/1f5ed8eb-afb6-419b-86a1-e90e814fed50" />



Level 9 --> Level 10:

    1. The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

Code:
  ssh bandit9@bandit.labs.overthewire.org -p 2220:

      Opens an encrypted SSH terminal connection as user bandit9 on port 2220.

  ls:

      Lists directory contents, confirming data.txt is present.

  strings data.txt | grep "=":

      Scans the binary file for readable text strings and filters the output for lines containing equals signs.

  strings data.txt:
  
      Extracts printable ASCII character sequences from non-text or binary files.

  | (Pipe):
  
      Sends the output stream from strings directly into grep.

  grep "=":
      
      Filters the string stream to display only lines containing =, exposing the phrase R========== B0s2khmbT9u0geKuOoVGW3JZKhndE3BG.


Result:
    
    1. It give the password of the next level.


<img width="752" height="616" alt="level 9 to 10" src="https://github.com/user-attachments/assets/6c2744da-d4f0-4576-8395-f432b0311426" />


<img width="455" height="267" alt="level 10" src="https://github.com/user-attachments/assets/b49c7639-1dc4-4666-a93e-60cb296cac63" />


Level 10 --> Level 11:

    1. The password for the next level is stored in the file data.txt, which contains base64 encoded data.

Code:
  ssh bandit10@bandit.labs.overthewire.org -p 2220:

      Opens an encrypted SSH connection as user bandit10 on port 2220.

  base64 -d data.txt:

      Decodes the Base64 data stored in data.txt and prints the original plain text to standard output.

  base64:
  
      A CLI utility used for encoding binary/text data into ASCII strings and decoding them back.

  -d (decode): 
  
      Instructs base64 to decode the target file rather than encoding it.

  data.txt:
      
      The target file containing the Base64 string.


Result:
    
    1. It give the password of the next level.


<img width="717" height="667" alt="level 10 to 11" src="https://github.com/user-attachments/assets/c39884a5-4c72-4bf1-9b38-77fba735386b" />


<img width="587" height="50" alt="level 11" src="https://github.com/user-attachments/assets/3a0a9c6a-7e92-46ad-bf81-72cf5ebb5140" />



Level 11 --> Level 12:

    1. The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.


Code:
  ssh bandit11@bandit.labs.overthewire.org -p 2220:

      Opens an encrypted SSH connection as user bandit11 on port 2220.

  cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m':

      Reads data.txt and translates each letter by shifting it 13 positions forward in the alphabet (ROT13 cipher).

  tr (Translate):
  
      A CLI utility used to translate or delete characters from standard input.

  'A-Za-z':
      
      Specifies the source character set (all upper and lower case letters).

  'N-ZA-Mn-za-m':
      
      Specifies the target replacement character set, where A maps to N, B maps to O, a maps to n, etc.

  exit:

      Disconnects from the bandit11 remote server session.


Result:
    
    1. It give the password of the next level.


<img width="852" height="660" alt="level 11 to 12" src="https://github.com/user-attachments/assets/d5ee6896-9549-4d78-abc5-4cf80b1e17a3" />


<img width="736" height="105" alt="level 12" src="https://github.com/user-attachments/assets/3a5bb937-adf3-442f-8e4b-d1e9ad1e0f7e" />


Level 12 --> Level 13:

    1. The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

Code:

  mkdir /tmp/sailesh && cp data.txt /tmp/sailesh && cd /tmp/sailesh:

      Creates a temporary directory in /tmp to safely work and rename files without permission restrictions in the home directory.

  xxd -r data.txt data1:

      Reverses (-r) the ASCII hex dump in data.txt back into its raw binary format saved as data1.

  file <filename>:

      Determines the exact file format (e.g., gzip, bzip2, or tar) regardless of the file extension.

  gzip -d <filename>.gz:

      Decompresses a gzip file. Requires renaming the file with a .gz extension first using mv.

  bzip2 -d <filename>.bz2:

      Decompresses a bzip2 file. Requires renaming the file with a .bz2 extension first using mv.

  tar -xvf <filename>

      Extracts files from a tar archive (-x: extract, -v: verbose, -f: file name).

  cat data9

      Displays the contents of the final uncompressed text file containing the password.


Result:

    1. It give the password of the next level.


<img width="895" height="627" alt="level 12 to 13" src="https://github.com/user-attachments/assets/e10c8b8b-8e80-43a6-99c5-57baacaff4d8" />


<img width="1747" height="942" alt="level 13" src="https://github.com/user-attachments/assets/2ff6076a-b5f8-4267-9371-2d6673b38ee9" />


Level 13 --> Level 14:
  
    1. The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.

Code:





    


















  





    


    




  

