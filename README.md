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

8.) Ran the following command ''' aws configure ''' and input my keys

Hooray! We are in!
