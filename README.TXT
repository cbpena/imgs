--------------------------------------------------------------
IMGS (v0.12.0)
Image Stitching Tool
--------------------------------------------------------------

A tool for stitching multiple images into one larger image. Currently only
supports BITMAP images.

This is free software.  You may use, modify, and / or redistribute any part
of this software in any fashion.

--------------------------------------------------------------
Command line
--------------------------------------------------------------

Usage:

		imgs infile outfile [-options]

Options:
		
		-?				show help
		-f <value>		set empty space fill value
		-w				warn if images overlap
		-b				draw a border around each individual image
		-c <rgb>		change border color (default is 0x00FF0000 [RED])
		-i				label each image with its index
		-l				label each image with its file title

--------------------------------------------------------------
Script
--------------------------------------------------------------

The 'infile' argument is a script file describing how the images should be
positioned and clipped. Each line is a seperate image. Blank and lines beginning
in '#' are ignored. Negative values are valid for the destination coordinates.

Format:

	<filename> <src-x> <src-y> <src-w> <src-h> <dest-x> <dest-y>

Example:

#	This is a comment and is ignored
image00.bmp		0 0  512  512       0     0
image01.bmp		0 0 1536  256     512     0
image02.bmp		0 0  768  256   -1024     0


A 512 x 512 pixel rectangle from "image00.bmp" is copied starting at position
0,0 to the output at 0,0

A 1536 x 256 pixel rectangle from "image01.bmp" is copied starting at position
0,0 to the output at 512,0

A 768 x 256 pixel rectangle from "image02.bmp" is copied starting at position
0,0 to the output at -1024,0

--------------------------------------------------------------
<EOF>