# Image Cropper and Cleaner

This Python script takes a large image file, crops it into 512x512 images, and then deletes the images that have a large amount of specified color space in a row. The cropped images are saved in a new folder. The idea is to remove images that have large blocks of color. When creating a style LORA, these can cause issues if you have black space or white space in your image scans.

## Usage

The script can be run from the command line with the following arguments:

- `large_img_path`: The path to the large image file. Example: "/home/user/Pictures/image.png"
- `new_folder`: The new folder to save the cropped images. Example: "/home/user/Pictures/CroppedImages"
- `--color`: The colors to check for in hexadecimal or RGB format. Default is black (#000000). Example: "#FFFFFF" "#FF0000" or "255,255,255" "255,0,0"
- `--color_threshold`: The color threshold. If a pixel's color is above this threshold, it is considered as a color pixel. Default is 70. Example: 80
- `--color_percentage`: The percentage of color pixels in a row for an image to be considered having too much of that color. Default is 10. Example: 20
- `--color_specs`: The color specifications in the format "color,threshold,percentage". Example: "#FFFFFF,80,20" "#FF0000,70,10"

## Example

Here is an example of how to run the script:

````bash
python change_image512.py /home/user/Pictures/large_image.png /home/user/Pictures/CroppedImages --color "#FFFFFF" "#FF0000" --color_threshold 80 --color_percentage 20 --color_specs "#FFFFFF,80,20" "#FF0000,70,10"```

This will take the image at /home/user/Pictures/large_image.png, crop it into 512x512 images, save the cropped images in /home/user/Pictures/CroppedImages, and delete any images that have more than 20% of their pixels above a color threshold of 80 for the colors white and red.



Basic Command
The basic command to run this script with default parameters would be:
python change_image512.py <large_img_path> <new_folder>

Replace <large_img_path> with the path to the large image file you want to process, and <new_folder> with the path to the folder where you want to save the cropped images.

For example:
python change_image512.py /home/user/Pictures/image.png /home/user/Pictures/CroppedImages
This will run the script with the default parameters, which are:

Color to check for: Black (#000000)
Color threshold: 70
Color percentage: 10
Color specifications: None (will use default values of black and white with thresholds and percentages of 70,10 and 80,20 respectively)
````
