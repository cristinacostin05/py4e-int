..  Copyright (C)  Mark Guzdial, Barbara Ericson, Briana Morrison
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3 or
    any later version published by the Free Software Foundation; with
    Invariant Sections being Forward, Prefaces, and Contributor List,
    no Front-Cover Texts, and no Back-Cover Texts.  A copy of the license
    is included in the section entitled "GNU Free Documentation License".

.. |audiobutton| image:: Figures/start-audio-tour.png
    :height: 20px
    :align: top
    :alt: audio tour button

.. 	qnum::
	:start: 1
	:prefix: csp-11-1-

Using Repetition with Images
============================================

*Learning Objectives:*

- Use ``for`` loops to repeat actions on all pixels in a picture.
- Understand the pattern (the steps) used in modifying all the pixels in a picture.

..	index::
	single: images
	pair: statements; for

.. index::
   single: pixel
	 single: picture
	 single: color

Pictures on a computer are broken up into little bits called **pixels**, for *picture* (pix) *elements* (els).  These are laid out on a grid, from left to right (horizontal or **x** dimension) and top to bottom (vertical or **y** dimension).

.. figure:: Figures/grid.png
    :align: center
    :alt: A grid with horizontal (x) and vertical (y) dimensions
    :figclass: align-center

    Figure: A grid with horizontal (x) and vertical (y) dimensions

Pixels are quite small.  Even the small picture below has 180 columns and 240 rows of pixels.  Each pixel has a color associated with it: An amount of redness, an amount of greenness, and an amount of blueness.
Let's remove the red from this picture.  Now, there are lot of lines in the program below, but fortunately, you can ignore most of them. The Audio Tour explains the important lines.  Press |audiobutton| to hear the audio tour explanation.  When you run this program it may take several minutes to show the changed picture.

.. datafile:: arch.jpg
   :image:
   :fromfile: Figures/arch.jpg
   :hide:

.. activecode:: Image_Remove_Red
    :tour_1: "Important Lines Tour"; 1: timg3-line1; 4: timg3-line4; 7-8: timg3-line7-8; 11: timg3-line11; 14: timg3-line14; 17-18: timg3-line17-18;
    :nocodelens:
    :datafile: arch.jpg

    from image import *

    # CREATE AN IMAGE FROM A FILE
    img = Image("arch.jpg")

    # LOOP THROUGH THE PIXELS
    pixelList = img.getPixels()
    for p in pixelList:

    	# SET THE RED TO 0
        p.setRed(0)

        # UPDATE THE IMAGE
        img.updatePixel(p)

    # SHOW THE RESULT
    win = ImageWin(img.getWidth(),img.getHeight())
    img.draw(win)

The program above can take several minutes to execute on the ``arch.jpg`` picture.  But we're not stuck using just the arch image.  You can
change the file name in the program above to the URL for any small photo that is on the internet.

.. note::

    Discuss topics in this section with classmates.

      .. disqus::
          :shortname: cslearn4u
          :identifier: studentcsp_11_1
