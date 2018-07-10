---
### Upload large number files to R-studio using Winscip 
---
##### 1) Add user authenticate rstudio as ubuntu user

On Windows: connect to the instance using putty

	putty>ubuntu@ec2_xx.xxx.xx.xxx.compute-1.amazonaws.com

Once connected, change security context using: 
	
	sudo su rstudio
Go to rstudio home directory and create .ssh folder. Change the file permission to 700 for rstudio/new user/to write and read keys

	cd ../rstudio
	mkdir .ssh
	chmod 700 .ssh
	
Create authorized keys, copy and paste the .pem private key. Use ssh-keygen -y or PuTTYgen to get private key
	
	touch .ssh/authorized_keys
	cd .ssh
	nano authorized_keys

exit and save the authorized_keys

##### 2) ssh using the private pem file as the new user

	ssh -i xoxo.pem rstudio@ec2_xx.xxx.xx.xxx.compute-1.amazonaws.com

##### 3) connect to the instance using winscip
	
	Host name:@ec2_xx.xxx.xx.xxx.compute-1.amazonaws.com
	Username: rstudio
	
Upload as many file as you want !

