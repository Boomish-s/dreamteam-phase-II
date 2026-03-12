LEVEL 0:
       * LEARN SSH COMMAND AND MAKE THE HOST CONNECTION THE USERNAME AND PASSWORD WAS GIVEN DIRECTLY
LEVEL 0-1:
        * LEARNT THE CD,LS,CAT,FILE,FIND COMMANDS ,USED 'ls -a' to list out all the directory and files ,next there was an info the password is in readme.md
        file ,so i used the command "cat readme.md" to open the file and find the PASSWORD "ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If"
        and used the commmand  exit to leave and used " ssh bandit1@bandit.labs.overthewire.org -p 2220" to move to the next tasks
level 1-2:
        * The commands learned before is enough but we need to learn the extensions of the cat command ,here the the password is stored in dashed file
        so the terminal will get confused so we want to use "cat ./-" to denote as in the present directory and the filename is "-"
        and i got the PASSWORD  "263JGJPfgU6LtdEvgfWU1XP5yac29mFx"
        then move to the NEXT LEVEL using "ssh bandit2@bandit.labs.overthewire.org -p 2220"
level 2-3:
        * I have used "ls-la" to list out all the files with extended details
        then as the filename contained both "spaces" and special character "-"
        it will definetly confuse the terminal so we have used the command  cat "./--spaces in this filename--"
        here the first -- denotes that the next charcters are the part of the filename and no other keyword used and task the next entire string as a filename
        and i got the PASSWORD "MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx" FOR THE NEXT LEVEL
        and used  "ssh bandit3@bandit.labs.overthewire.org -p 2220" to move next level
level 3-4:
        * I have used "ls-la" to list out all the files with extended deatails
        there was a directory called "inhere" i used cd inhere to open it
        and again used "ls -a" to list out
        then i got to know that there is a file "...Hiding-From-You" as mentioned in the task
        so i used " cat ...Hiding-From-You"  to open the file
        the concept was learned in the last task
        I GOT THE PASSWORD "2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ"
        and used "ssh bandit4@bandit.labs.overthewire.org -p 2220"
        to move to the next task
level 4-5:
        * I have used ls -al to list out
        and used cd-inhere to move to the directory as given
        then a new concept "file ./*" which tells the type of a file
        and there was a info as ASCII TEXT in the file 07
        and rest was a data
        so i opened the file 07
        and got the password "4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw"
        then used "ssh bandit5@bandit.labs.overthewire.org -p 2220" to move to the next task
level 5-6:
        * I have used ls  to list out
        and used cd inhere to move to the directory as given
        i have learnt to use 'find' command to search a file with the conditons given
        i have used the commad "find  -type f -size 1033c ! -executable" to find a file with size of 1033 bytes
        where c- prefix of bytes -type f denotes the file
        and i got the path that the file is present in maybehere07 and .file2

level 6-7:
        here there is no specific directory mentioned so we want to search from the "root directory"
        i have learned the extensions of the find command which took hours to understand that single step
        i have used / instead . to search in root and mentioned the cases as given
        and the important step 2>/dev/null which was quit hard to understand
        when we use the command without this there will be lots of permission denied message
        to redirect the error message we use "2>"
        dev/null/ command is used to dissapper any message ,in this case  the error message (permission denied messages) is dissappered
        all as combined i have used the command "find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null"
        and got the path and used cat command to read it and GOT THE PASSWORD "morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj"
        and used "ssh bandit7@bandit.labs.overthewire.org -p 2220" to move on to the next task
level 7-8:
       here there is only one file that is data.txt
       and password is stored next to the word millionth so i used the command
       "grep millionth data.txt"
level 8-9:
        there was condition given as the password line was the only line which doesnt have a duplicate line
        i learnt sort command with extensions and used the command " sort data.txt | uniq -u "
        here we have used uniq -u which will return the line that came only one time
        and GOT THE PASSWORD "4CKMh1JI91bUIZZPXDqGanal4xvAg0JM"
        AND USED "ssh bandit9@bandit.labs.overthewire.org -p 2220" to move the next level
level 9-10:
        I have learned about string command ,it is used to extract only the human readble txt in the file
         I haveused "strings data.txt" then there where multiple lines ,so i added condition using grep command
        the final command i used is "strings data.txt | grep "=="  "
        then I GOT THE PASSWORD "FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey"
        and used "ssh bandit10@bandit.labs.overthewire.org -p 2220" to move to the next level 
level 10-11:
        i have learned about base64 ,it encodes a binary data into a text ,mostly it will end by "==" or without any special characters
        then i have used " cat data.txt" and opend the file ,there was a base64 code ending with == ,
        i have used the base64 command to convert into normal text ,the exact command was "base64 -d data.txt"
level 11-12:
        I have used " cat data.txt" and opend the file and there was an some unmeanigfull string
        as mentioned in the task the string was 13 character displaced
        i learned about the the command "tr"    which converts the string according to the condition given by the user
        the command i used is "cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'" where the "A-Za-z" denotes both upper and lower case
        and "N-ZA-Mn-za-m" this denotes 13 characters has been shifted
        AND I GOT THE PASSWORD "7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4"
        AND USED "ssh bandit12@bandit.labs.overthewire.org -p 2220" to move to the next level
level 12-13:
        In this level, no specific directory was mentioned, so I created a temporary working directory using mktemp -d and moved into it. I then copied the
        data.txt file into this directory. When I opened the file, it looked like a hexdump, so I learned about the xxd command which converts hexdump
        back into binary. I used xxd -r data.txt > newfile to reverse it. After that, I checked the file type using the file command, and it showed
        that the file was compressed. Since it was repeatedly compressed in different formats such as gzip, bzip2, and tar, I had to rename the file
        xtension each time (e.g., .gz, .bz2, .tar) and then use the correct command to extract it: gunzip for gzip, bzip2 -d for bzip2, and tar -xf
        or tar archives. I repeated this process of checking with file, renaming, and extracting multiple times until I finally got a plain ASCII text file.
        using cat on this file revealed the password, and with that, I connected to the next level using ssh bandit13@bandit.labs.overthewire.org -p 2220
level 13-14:
        * i have used ls -a to list out all the items , i found something as sshkey.private and used cat to open and i got permission denied
        and i learned about 'chmod' command which used to change the permision , the commmand i used is" chmod 600sshkey.private"
        where chmod used to change the permission , 6 - denotes permission for read and write ,0- denotes no permission for other group and other user
        and i got the key "ssh -i sshkey.private bandit14@localhost -p 2220" inside and used this key to login the bandit14 to find the password
        there was mentioned as the password is in /etc/bandit_pass/bandit14 so i have used cat /etc/bandit_pass/bandit14 to find the password
        and i got the PASSWORD "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS"
        and used "ssh bandit14@bandit.labs.overthewire.org -p 2220" to move on the next level
level 14-15:
        in this task they asked to connect to a different port and on a local host
        i learnt about the command netcat "nc" which is used to transfer the data along the ports
        the command i used is "nc localhost 30000"
        and submitted the previous password and GOT THE NEW PASSWORD "8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo"
        and used "ssh bandit15@bandit.labs.overthewire.org -p 2220" to move to the next task
level 15-16:
        in this task they asked to connect to a different port and on a local host and enter the password of the previous task which gives the next password
        i have tried to connect with nc but it didnt work because there are some encryptions so we wanted to use openssl s_client
        i learnt about the command the used this "openssl s_client -connect localhost:30001" the connect to the severe with all the encryption
        and i have entered the password of the 15 taks and GOT THE NEW PASSWORD "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx"
        AND USED "ssh bandit16@bandit.labs.overthewire.org -p 2220" to login the next level
level 16-17:
        In this level, the task was to find which port (between 31000 and 32000) was running a service that would accept the current password and return the
        next one. To start, I used the nmap command nmap -p31000-32000 localhost to scan the port range. This showed me which ports were open and
        listening. Next, I tested the open ports with openssl s_client -connect localhost:<port> to check which one was speaking SSL/TLS. Some ports rejected
        the connection or gave errors like “unexpected message,” but when I connected to port 31518, it successfully established a TLS connection. Inside this

level 17-18:
        I USED LS -A TO LIST OUT
        THERE IS AN INFO THAT THE PASSWORD IS THE LINE WHICH IS THE ONLY LINE DIFFERNT IN PASSWORD.OLD AND PASSWORDS.NE
        I USED DIFF COMMAND THE EXACT COMMAND WAS "diff passwords.old passwords.new"
        AND GOT THE PASSWORD "x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO"
        USED "ssh bandit18@bandit.labs.overthewire.org -p 2220" TO MOVE TO NEXT LEVEL
level 18-19:
        I HAVE SEEN THE "BYE BYE !"
        THEN I MEANS I HAVE COMPLETED THE TASK SUCCESSFULLY
        NOW IM NOVING TO THE TASK BANDIT19
level 19-20:
        i have used ls -a to list out all the items
        then i have use "./bandit20-do" to to read instruction without any arguments
        and used "./bandit20-do id" to find the id
        and used "./bandit20-do /bin/cat /etc/bandit_pass/bandit20" to read the password for the next level
        an used "ssh bandit20@bandit.labs.overthewire.org -p 2220"
        to move the next level
        
                        " succesfully completed upto level 20 "
