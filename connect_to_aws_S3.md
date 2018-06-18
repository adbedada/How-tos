## Connect to AWS - S3 

**Install AWSCLI**
AWSCLI is Amazon's the command line interface. Open command prompt and type in: 

	pip install awscli

**Check if its correctly installed**

	aws --version

you should see:
> aws-cli/1.15.32 Python/3.6.2 Windows/10 botocore/1.10.32
			
**Configure Account**

First, Get your personal credential by following the path below*  
>xyz.pem
 
 Then, on command line type: 
		
		aws configure

Provide your information for each parameter. 
		
>  AWS Access Key ID [None]: **your Access ID** 
	AWS Secret Access Key [None]: **your secret access key**
	region name [None]: us-east-1  *(Identifies our location: N.Virginia)*
	Default output format [None]: json


## Navigate on S3

List all buckets
			
		aws s3 ls

List all files inside a bucket

		aws s3 ls bucket-name 
Create new bucket 
	
		aws s3 mb s3://bucket-name
 
Delete bucket

		aws s3 rb s3://bucket-name

Delete all files in a bucket
	
		aws s3 rb s3://bucket-name --force


Copy file from PC to a bucket

		 aws s3 cp input_name.tif s3://bucket-name

Move file from PC to a bucket
	
		aws s3 mv input_name.tif s3://bucket-name

 Copy/Sync folder from PC to a bucket
	
		aws s3 sync ./folder-name s3://bucket-name


