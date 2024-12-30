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

<img width="332" alt="image" src="https://github.com/user-attachments/assets/0f8e913a-244a-45e4-a723-83a4d76130be" />



# 2. Secret File
**Objective:** Locate a file with the word "secret" in its name anywhere in the /home/ctf_user directory.

Here I used the previous command ``` ls -la ``` and saw the **very_secret_file.txt** and ran ``` cat very_secret_file.txt ``` 

<img width="294" alt="image" src="https://github.com/user-attachments/assets/e6c6f340-d27e-4c57-a1fb-98e48d98b52e" />


# 3. Large file
**Objective:** Find the largest file in the /var/log directory and retrieve the flag from it.

I ran the command ``` du -hs /var/log* | sort -h ``` this helped tidy things up a bit so I could sort by the size of the file. After I saw the **large_log_file.log** and used ``` cat /var/log/large_log_file.log | more ``` to show a the contents in smaller secctions. 

<img width="379" alt="image" src="https://github.com/user-attachments/assets/208fcd92-c80d-4ac5-b65d-1059be794a92" />


# 4. Specific UID
**Objective:** Identify the user with UID 1001 and find the flag in their home directory.

Here I found the user ID 1001 by heading to the home directory and use ``` id ``` I tried to get into the **ctf_user** directory but was denied. I then used ``` sudo ``` to try and enter the directory but this didn't do anything. After I tried to list any files in the user directory with ``` sudo ls /home/ctf_user ``` I found the **flag.txt** I then used ``` sudo cat ``` to extract the contents.

<img width="355" alt="image" src="https://github.com/user-attachments/assets/e1e72e71-acfe-4bad-83e7-ba1f456d215a" />


# 5. Special permissions 
**Objective:** Locate the file owned by root with permissions 777 and read its contents.
I first needed to find theh permissions for files so I used ``` find / -type f -perm 777 ``` this slammed my console with a lot of files but I saw the /root directory and used ``` sudo ls /root ``` to get the **everyone_can_access_me** file and used ``` sudo cat /root/everyone_can_access_me ``` to get the flag.

<img width="403" alt="image" src="https://github.com/user-attachments/assets/909e7a63-21a7-43a5-9f38-d17598440800" />



# 6. Hidden Service
**Objective:** Find the process running on port 8080 and retrieve the flag from its command.

I remember seeing a **port_8080_service.sh** file listed in the ``` /ctf_challenges ``` directory earrlier. I ran ``` cat ``` and then found the flag within the content.

<img width="434" alt="image" src="https://github.com/user-attachments/assets/99f45c44-f036-4612-b64c-3b910eec35ee" />



# 7. Encodeded File
**Objective:** Decode the base64 encoded flag in the 'encoded_flag.txt' file.

While in the directory above I saw the encoded file and ran ``` base64 -d ``` on the file and got the last flag.

![image](https://github.com/user-attachments/assets/9a2bdcfc-abc6-4e3f-83fe-00887e716951)




