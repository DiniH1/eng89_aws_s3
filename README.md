README.md

# Setting up an S3 Bucket
- Create an ec2 instance and ssh into it.
- Ensure python is version 3 and above in order to avoid errors 
```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
apt list | grep python3.9
sudo apt-get install python3.9
sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1
sudo update-alternatives --config python3
alias python=python3
sudo apt install python3.9-distutils
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.9 get-pip.py
```
## Installation of awscli
```
#check python3 is installed
python3 --version



#install awscli with python3
python3 -m pip install awscli



-- OR --



#create an alias for python3
alias python = python3



#install awscli with python3
python -m pip install awscli

```
- Configuring `aws configure`
- Then there will be prompts of entering Access ID, and Secret ID
- Followed by region. Which in our case is eu-west-1
- followed by preferred format `json`

## Creating an s3 bucket
- `aws s3 mb s3://engdini89` where mb stands for make bucket and proper naming conventions appky with the exception of no special characters allowed in the name
- Upload a file: `aws s3 cp test.txt s3://eng89dini`
- Deleting the file from our terminal using `rm -rf test.txt`
- This file can be restored from the s3 bucket using `sudo aws s3 cp s3://eng89dini/test.txt test.txt`
- This file can be removed from the s3 bucket using `aws s3 rm s3://eng89dini/test.txt`
- The s3 bucket can be deleted using ``aws s3 rb s3://eng89dini`
