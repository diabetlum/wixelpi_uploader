wixelpi_uploader
================

*** THIS IS AN EXPERIMENT!! DO NOT USE THIS CODE, OR RESULTING DATA, TO MAKE ANY MEDICAL DECISIONS! ***

Uploader scripts for Raspberry Pi (or other linux) to upload raw cgm records from wixel to mongo.
I've set this up using a raspberry pi (out of the box setup, no changes or mods. I may have had to install curl (can't recall)
This connects via a usb cable to a wixel (http://www.pololu.com/product/1336) running Adrien's code (search the cgminthecloud facebook group for a post linking to his code repository) that *does not* shut down the USB. This is important as the the readline code won't work otherwise.

Interesting aside: I used the wixel code that shuts down the usb port, and was able to read from that on my mac by polling the usb port. This did not work on raspberry pi. I assume the difference is that the mac does a better job of flushing the buffer once the wixel shuts down the port.

Load the files into a directory, and make the .sh files executable (chmod +x *.sh)

You can determine which USB port has the wixel by simply plugging and unplugging to see what appears and goes away. On my rpi it's /dev/ttyACM0

Load mongo credentials into mongo.cfg

Invoke the program as ./dexterity.sh XXXXX /dev/usbporthere
substituting your values.

I edited some of this code on the fly in order to pretty it up and remove account references. In doing so I may have introduced some errors...

--- Peter Miller
