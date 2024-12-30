# Journey to Cloud - Linux CTF Challenge

Hello! This is my journey through 7 CTF Challenges, testing my skills with Linux commands. Flags are presented in this format ``` CTF{some_text_here} ```

# Set-up Environment

To get started I had to set-up the lab environment. **NOTE** _I was using VSCode to do all of the following_.

I cloned the ltc-linux-challenge repo and ran terraform in the /aws directory.

``` git clone https://github.com/learntocloud/ltc-linux-challenge ```

``` cd aws/ ```

``` terraform init ```

``` terraform apply ```
_Take note of this IP!!!_

Once this was done I needed configure the CLI with my AWS credentials which were found in my AWS Console > Security Credentials. I created the key and ran ``` aws configure ``` and input the needed values. Now I needed to set up an ssh session within connecting me to the virtual environment.

We are soooo in!!

# Challenge!

- Find a hidden file

- Locate a file with "secret" in its name

- Find the largest file in a specific directory

- Identify a user with a specific UID

- Locate a file with specific permissions

# 1. Hidden File
**Objective:** Find a hidden file in the ctf_challenges directory and read its contents.

Here I used the command ``` ls -la ``` to show all the files. I then moved to the directory ctf_challenges using ```cd ``` then used my  ``` cat ```... command _pun intended_ 
![image](https://github.com/user-attachments/assets/ca43d086-58d8-4f7d-9374-a33c5b9bd9f2)


# 2. Secret File
**Objective:** Locate a file with the word "secret" in its name anywhere in the /home/ctf_user directory.

Here I used the previous command ``` ls -la ``` and saw the **very_secret_file.txt** and ran ``` cat very_secret_file.txt ``` 
![image](https://github.com/user-attachments/assets/59203fcf-2f49-421d-8e3d-8492f027b2af)

# 3. Large file
**Objective:** Find the largest file in the /var/log directory and retrieve the flag from it.

I ran the command ``` du -hs /var/log* | sort -h ``` this helped tidy things up a bit so I could sort by the size of the file. After I saw the **large_log_file.log** and used ``` cat /var/log/large_log_file.log | more ``` to show a the contents in smaller secctions. 
![image](https://github.com/user-attachments/assets/5c1926d6-bfdf-41a6-ac32-859508765ea6)

# 4. Specific UID
**Objective:** Identify the user with UID 1001 and find the flag in their home directory.

Here I found the user ID 1001 by heading to the home directory and use ``` id ``` I tried to get into the **ctf_user** directory but was denied. I then used ``` sudo ``` to try and enter the directory but this didn't do anything. After I tried to list any files in the user directory with ``` sudo ls /home/ctf_user ``` I found the **flag.txt** I then used ``` sudo cat ``` to extract the contents.
![image](https://github.com/user-attachments/assets/cb095979-3e66-4a3b-8fe1-c165ab9c3589)

# 5. Special permissions 
**Objective:** Locate the file owned by root with permissions 777 and read its contents.
I first needed to find theh permissions for files so I used ``` find / -type f -perm 777 ``` this slammed my console with a lot of files but I saw the /root directory and used ``` sudo ls /root ``` to get the **everyone_can_access_me** file and used ``` sudo cat /root/everyone_can_access_me ``` to get the flag.
![image](https://github.com/user-attachments/assets/3ac122ee-30de-4e42-ac4a-290dde5c437a)


# 6. Hidden Service

Using ``` netstat ``` and found then used ``` netstat -p | grep ":8080" ```

# 7. Encodeded File

Ran through the directory using ``` ls ```

Afer I was able to find the encoded_flag.txt file and ran ``` base64 -d ``` on the file and got the last flag



