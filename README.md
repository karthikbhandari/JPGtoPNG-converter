# JPGtoPNG-converter

import sys
import os
from PIL import Image

# grab first and second argument
image_folder = sys.argv[1]
outer_folder = sys.argv[2]
print(image_folder,outer_folder)

# check if new exists, if not create it.
if not os.path.exists(outer_folder):
	os.makedirs(outer_folder)

# loop through pokedex 
for filename in os.listdir(image_folder):
	img = Image.open(f'{image_folder}{filename}')
	clean_name = os.path.splitext(filename)[0]
	img.save(f'{outer_folder}{clean_name}.png','png')
	
	print('all done')
