Connecting to EC2 using Windows/Putty

> Open Puttygen > Click on Load > Browse to .pem key
	
	aws_personal.pem
> Save as Priate Key
	
	aws.personal.ppk

> Open Putty 
> Go to Connection > SSH > Auth > Browse

navigate to where .ppk file is stored 
	
	aws_personal.ppk

> Go To Session > Host Name or IP Address 
>  Type <<user-name and the current Public DNS (IPv4)>>
	
for ubuntu  linux system the user-name is 'ubuntu'
	 
	ubuntu@ec2-54-175-22-99.compute-1.amazonaws.com		

Putty > Open

Install Python 2.7

	sudo apt update
	sudo apt upgrade
	sudo apt install python2.7 python-pip

Install basic modules

	pip install numpy scipy tables statmodels Rtree sckit-learn scikit-image colorama PySAL PyYAML retrying xmltodict  BeautifylSoup4 psutil  deprecation joblib --user


 
Install GDAL
		
	sudo add-apt-repository ppa:ubuntugis/ppa
	sudo apt-get update
	sudo apt-get install gdal-bin
	sudo apt-get -y install python-gdal

Install Cython

	pip install Cython

Install OpenCV

	sudo apt-get install libopencv-dev python-opencv	


Install MpGlue

	git clone https://github.com/jgrss/mpglue.git
	cd mpglue
	python setup.py build
	python setup.py install --user

Install SpFeas

	git clone https://github.com/jgrss/spfeas.git
	cd spfeas
	python setup.py build 
	python setup.py install --user

Check
	
	spfeas -h
	spfeas -e
