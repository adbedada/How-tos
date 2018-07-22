	/home/adbe/.conda/envs/CondaEnvP3.6:
	source activate CondaEnvP3.6

ssh nodeXXX
Load Anaconda to current directory
	
	module load anaconda

Create personal conda environment
	
	conda create -n myCondaEnvP3.6 python=3.6 anaconda

Connect to an idle node
	
	salloc -p xyz -t 3:00:00

Activate personal environment
	
	module load anaconda	
	source activate myCondaEnvP3.6

Install Keras if its not already installed
		
	pip install keras --user

test
	
	python
	import tensorflow as tf


