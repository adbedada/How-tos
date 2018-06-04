
	#!/bin/bash
	
	#generate output and error reports
	#SBATCH -o test_image.out
	#SBATCH -e test_image.err
	
	#pass parameters
	#SBATCH -p defq 
	#SBATCH -N 1 
	#SBATCH -n 16 
	#SBATCH -J spfeas 
	#SBATCH -t 3-00:00:00 
	
	# Setup Conda environment
	export PATH="/groups/engstromgrp/anaconda3/bin:$PATH"
	source activate Ryan_CondaEnvP2.7
	
	# run spfeas
	spfeas -i input.tif -o output_folder --vis-order rgb --block 1 --scales 3 5 7 -tr ndvi

