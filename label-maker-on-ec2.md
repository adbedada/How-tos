>Setup Python 3.6 environment on EC2 

Update the System

	sudo apt-get update
	sudo apt-get  -y upgrade

Install Python 3.6 

	sudo add-apt-repository
	ppa:deadsnakes/ppa
	sudo apt-get update
	sudo apt-get install python3.6

Installing pip 
	
	sudo apt-get install python3.6-pip


Add essential tools for programming environment

	sudo apt-get install build-essential libssl-dev libffi-dev python3.6-dev libcurl4-gnutls-dev  libgnutls-dev

Install Tippecanoe 
	
	git clone git@github.com:mapbox/tippecanoe.git
	cd tippecanoe
	make -j
	make install

Install label-maker
	
	pip install label-maker

> Working with Label Maker

create config.json file
	
	nano config.json

save the following configuration 

		{
	  "country": "vietnam",
	  "bounding_box": [105.42,20.75,106.41,21.53],
	  "zoom": 17,
	  "classes": [
	    { "name": "Buildings", "filter": ["has", "building"] }
	  ],
	  "imagery": "http://a.tiles.mapbox.com/v4/mapbox.satellite/{z}/{x}/{y}.jpg?access_token=pk.eyJ1IjoiZGVzdGFuZW9uMSIsImE$
	  "background_ratio": 1,
	  "ml_type": "classification"
	}

Download tiles

	label-maker download --dest dataset --config config.json
	
Download labels

	label-maker labels --dest dataset --config config.json

Download Images

	label-maker images --dest dataset --config config.json

Compile data-set
	
	label-maker package --dest dataset --config config.json
	
		


>Troubleshooting tips

	//grant user root access
		sudo su
		
	//use python3.6& pip3.6 with pip
		alias python=python3.6
		alias pip=pip3.6
	
	//Install pycurl independently	
		pip install pycurl=7.43.0.1
	





