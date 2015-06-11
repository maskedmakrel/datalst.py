# datalst.py
#I cobbled together a crude script to convert Papagayo .dat files for use in Synfig as lst files.  
#It is a patchwork of slightly modified suggestions that seems to work in Python3.  
#I move all my .dat files to a target directory with the script and run it.  
#Changes are permanent.

import os
import sys
import fileinput
import glob
for line in fileinput.input(glob.glob('*.dat'), inplace=True):
	sys.stdout.write(line.replace('MohoSwitch1', 'MohoSwitch1' '\n' 'FPS 24' '\n' 'png'))
for filename in os.listdir(os.path.dirname(os.path.abspath(__file__))):
  base_file, ext = os.path.splitext(filename)
  if ext == ".dat":
    os.rename(filename, base_file + ".lst")
    
