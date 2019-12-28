# awscli-guide

## Table of Content
* Overview
* Prerequisites
* Usage

## Overview
This guide explains the steps to upload/download files to/from AWS S3 Buckets using AWS Command Line Interface (CLI).

## Prerequisites
1. Obtain your own AWS credentials from an administrator. AWS credentials consist of a **key** and a **secret access**.
2. Download and install AWS CLI
3. Configure AWS CLI using AWS credentials


### Step 1 - Obtain AWS credentials
You can get your own AWS credentials from an administrator. It should look something like this:

aws_access_key_id=AKIAIOSFODNN7EXAMPLE
aws_secret_access_key=wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY

### Step 2 - Download and install AWS CLI
Please refer to the official guide if needed. We will be using AWS CLI version 1.
https://docs.aws.amazon.com/cli/latest/userguide/install-cliv1.html

**For Windows**
1. Download the MSI Instaler. Choose *Download the AWS CLI setup file*
2. Run the downloaded MSI installer or the setup file.
3. Follow the onscreen instructions.
4. Verify the sucess of installation. To confirm the installation, type the ```aws --version``` command in the command prompt (open the Start menu and search for cmd to start a command prompt).

**For Mac or Linux**
Please refer to the official guide.

### Step 3 - Configure AWS CLI
Type the ```aws configure``` command in the command prompt. The AWS CLI prompts you for four pieces of information (access key, secret access key, AWS Region, and output format). Please enter your access key and secret access key. Leave the default region and output format as None by pressing Enter.
```
AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE (use your own access key here)
AWS Secret Access Key [None]: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY (use your own secret key here)
Default region name [None]: leave as default by just pressing enter
Default output format [None]: leave as default by just pressing enter
````

## Usage
AWS CLI supports many commands to interface with all parts of AWS. We will go through one specific part of AWS called **S3**. The official documentation can be found here: https://docs.aws.amazon.com/cli/latest/reference/s3/index.html

### S3
Taken from the official AWS website, Amazon Simple Storage Service (Amazon S3) is an object storage service that offers industry-leading scalability, data availability, security, and performance.

As a object storage service, S3 can store files like images, videos, textfiles and etc. One way to use S3 is through the AWS CLI. The AWS CLI provides various simple operations:

* cp - copy file(s)
* rm - remove file(s)
* mv - move file(s)
* sync - sync file(s)
* ls - list file(s)
* mb - make bucket
* db - delete bucket

#### Examples
Let's go through some common examples:

**Download files**

Command: 
```aws s3 sync <S3Uri> <LocalPath>```

S3Uri is the location of the bucket.

LocalPath is the location of the folder on your local computer.

Examples: 

```aws s3 sync s3://graduation_photo.jpg ./``` This will download photo the graduation_photo.jpg to the current working directory of your local computer

```aws s3 sync s3://cat_videos ./Images``` This will download the folder cat_videos to the Images folder in your current working directory of your local computer

```aws s3 sync s3://ctangiogram ./``` This will download the folder ctangiogram to the current working directory of your local computer

**Upload files**

Command: 
```aws s3 sync <LocalPath> <S3Uri>```

Examples: 
```aws s3 sync ./ s3://ctangiogram```


