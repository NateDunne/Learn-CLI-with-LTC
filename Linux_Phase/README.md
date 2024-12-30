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

Here I used the command ``` ls -a ``` to show all the files **Including hidden**. Once we see the hidden files run the ``` cat ``` command with the following file path and grab the FLAG!

# 2. Secret File

Here I used the previous command ``` ls -a ``` and saw the **very_secret_file.txt** and ran ``` cat very_secret_file.txt ``` and got the flag for this one

# 3. Large file

Here I switched directories and started with using ``` ls ``` to find the large file txt file. After I used the ``` more ``` command to grab the flag

# 4. Specific UID

First found the UID by ``` cat /etc/passwd ``` 

Then used ``` grep ":<UID>:" /etc/passwd ```  flag acquired 

# 5. Special permissions 

First use the ``` ls -l ``` command and with that you are able to see there is a file with chmod This is our file 

# 6. Hidden Service

Using ``` netstat ``` and found then used ``` netstat -p | grep ":8080" ```

# 7. Encodeded File

Ran through the directory using ``` ls ```

Afer I was able to find the encoded_flag.txt file and ran ``` base64 -d ``` on the file and got the last flag



