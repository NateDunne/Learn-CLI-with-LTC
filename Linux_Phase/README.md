# Learn-CLI-with-LTC

I am trying to pick up the skills I need to pursue a career in cloud computing. To do this, I will need to understand linux as it is widely used on cloud servers.
I will need to set up the learning environment which was followed here https://github.com/learntocloud/ltc-linux-challenge/tree/main/aws

# Note
In the initial set-up for AWS CLI I ran into an issue where I was unable to ssh into the remote server because I didn't have the proper keys

To get around this I did the following:

1.) Went to the Amazon Web Services console

2.) Clicked your account name in the top right corner

3.) Select Security Credentials from the drop-down list

4.) Clicked Continue to Security Credentials

5.) Expand Access Keys

6.) Clicked Create New Access Key

7.) Clicked Show Access Key

8.) Ran the following command ``` aws configure ``` and input my keys

Hooray! We are in!

![image](https://static1.srcdn.com/wordpress/wp-content/uploads/2023/11/ryan-gosling-as-colt-giving-the-thumbs-up-in-an-army-uniform-in-the-fall-guy.jpg)

# Challenge!

- Find a hidden file

- Locate a file with "secret" in its name

- Find the largest file in a specific directory

- Identify a user with a specific UID

- Locate a file with specific permissions

# 1. Hidden File

Here use the command ``` ls -a ``` to show all the files **Including hidden**. Once we see the hidden files run the ``` cat ``` command with the following file path and grab the FLAG!

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



