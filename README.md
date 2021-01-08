1. [ What is this project for. ](#Whatisthisprojectfor)
2. [ Prerequisite. ](#Prerequisite)
3. [ How to get prepared. ](#Howtogetprepared)
4. [ How to execute. ](#Howtoexecute)
5. [ Next release. ](#Nextrelease)

<a name="Whatisthisprojectfor"></a>
## 1. Sandbox environment automation using Terraform
This is a simple ansible role to perform the below tasks 
* This role will create buckets in aws S3. This has capability to create multiple bucket at a single shot using an input variable file with the list of buckets named
* This role will help us to list out the details of AWS S3 buckets as follows
  * Number of files in individual buckets in AWS S3
![bucket_details_files](https://user-images.githubusercontent.com/20129204/104019990-7efe8400-51e2-11eb-9914-65a39bc6b5ee.JPG)
  * Bucket creation data along with time
![bucket_details_1](https://user-images.githubusercontent.com/20129204/104020003-82920b00-51e2-11eb-8d25-67a2b97c5821.JPG)
  * Size of the S3 Buckets
![bucket_details_files_sizes](https://user-images.githubusercontent.com/20129204/104019999-8160de00-51e2-11eb-9910-cfb5de9a165f.JPG)
  * Last modifed files in list
![bucket_details_files_latest](https://user-images.githubusercontent.com/20129204/104019997-80c84780-51e2-11eb-9d6b-47da40f3da74.JPG)
<a name="Prerequisite"></a>
## 2. Prerequisite
This is developed over ansible which is a very light weight tool for configuration management. It need some of basic pre-requisite
* **Python 3+** : As this is pre-requisite for ansible for execution
  * How to get this: We can use apt installer for installing python - **apt install python3.6**, once installed please verify with command- python3 --version
* **Boto3 libraries** : Boto3 library is used for interating with AWS services using api calls. 
  * How to get this: have to follow below steps for right installation,
    * apt install python3-pip , Used to install pip (package installer for python) 
    * pip3 install boto3, boto package for aws cli execution
    * pip3 install awsebcli --upgrade, to upgrade awsebcli packages
    * eb --version, to check whether package is installed
    * pip install --upgrade awscli, upgrade awscli package
* **Ansible Installer**: Ansible package is essential for executing this project
  * How to get this: We can install ansible by using simple command - **apt install ansible**

<a name="Howtogetprepared"></a>
## 3. How to get prepared
Once the pre-requisite are done, we are ready to get started with the execution. A very minimul changes are needed,
* Firstly, please clone the this project to any of your location directory on linux machine(Can be Ubuntu)
* Once cloned, we need to update credentials.properties file for authenticating to AWS. This need 3 parameters to be updated,
  * AWS_ACCESS_KEY_ID
  * AWS_SECRET_ACCESS_KEY
  * AWS_DEFAULT_REGION
  You can update this using the this aws [help](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/getting-your-credentials.html) 
* Once updated, you can go ahead with the execution

<a name="Howtoexecute"></a>
## 4. How to execute
Execution of this project is designed in very simple way. We have 2 ways for execution,
* Create bucket in S3
  * ansible-playbook test.yml -e "create_bucket=true"  - This command will execute the create bucket logic for creating buckets in S3
![create_bucket_out](https://user-images.githubusercontent.com/20129204/104020001-81f97480-51e2-11eb-93b4-9924c3eecbef.JPG)
* Get the details of buckets in S3
  * ansible-playbook test.yml -e "bucket_details=true" - This command fetched all details mentioned in [section-1](#Whatisthisprojectfor)
  
<a name="Nextrelease"></a>
## 5. Next release
This is an initial kick start for AWS S3 utilities using ansible. Will be updating more in the next releases,
* Cleaning filtering of output for bucket size, number of files etc.,
* Create bucket and fetch details of bucket in a single playbook.
* custom modules for aws s3 utilities using python will be added as support

## Happy for Support ## 
Feel free to fork the code and modify it.
