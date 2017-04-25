# AYAB

All Yarns Are Beautiful

This is the GUI interface for AYAB.

## Installation

### Linux

#### Prerequisites

You need Python 2.7 and PyQt5 from your package manager's repository.
The other main dependencies can be found in requirements.txt

*For Debian/Ubuntu*

    sudo apt-get install python-pip python-qt5 python-dev python-virtualenv

*For openSUSE*

    sudo zypper install python-pip python-qt5 python-virtualenv

*All Distributions*
To be able to communicate with your Arduino, it might be necessary to add the rights for USB communication by adding your user to some groups.

    sudo usermod -a -G tty [userName]
    sudo usermod -a -G dialout [userName]
    
#### Release Version

This will install the latest release version from PyPi

    virtualenv --system-site-packages venv/
    source venv/bin/activate
    pip install ayab
    
Now, you can start the software with

    ayab

#### Running from Source & Development

To install the development version you can checkout the git repository

    git clone https://github.com/AllYarnsAreBeautiful/ayab-desktop

Create a virtual enviroment in the cloned repository
    
    cd ayab-desktop
    virtualenv --system-site-packages venv/
    source venv/bin/activate

Now start ayab with

    ayab_devel_launch.py

Note: If running ayab fails with "IOError: [Errno 13] Permission denied: '/usr/local/lib/python2.7/dist-packages/oauthlib-0.6.0-py2.7.egg/EGG-INFO/top_level.txt" or similar, try to change the permissions of the file using
    sudo chmod o+r /usr/local/lib/python2.7/dist-packages/oauthlib-0.6.0-py2.7.egg/EGG-INFO/top_level.txt

To be able to work on GUI elements and translation files, the Qt Dev tools are needed also:

    qttools5-dev-tools

### Windows

#### Release Version

The Windows version which is available at http://ayab-knitting.com has been packed with py2exe and should not require any additional dependencies. Just unzip the archive to C:\ayab-apparat and run

    ayab.exe

#### Running from source & Development (Tested on Win10)

You need Python Version 2.7.13 (Important: the 64 bit version!) and PyQt5 (we used 5.3.2).

Download and install Python 2.7.13 (64 bit) (pip is already contained in this installer) from
    https://www.python.org/downloads/windows/

and additionally run

    pip install virtualenv python-qt5
    
You can checkout the git repository with

    git clone https://github.com/AllYarnsAreBeautiful/ayab-desktop

Create a virtual enviroment in the cloned repository
    
    cd ayab-desktop
    virtualenv --system-site-packages venv/
    venv\Scripts\activate

Then install the remaining prerequisites with

    pip install -r requirements.txt

Now start ayab with

    ayab_devel_launch.py

### macOS

**TODO**

## Release Notes

### 0.80 (November 2015)

#### Firmware

* API v4
* Added Test Mode
* Added Auto-Init functionality
* Added FW Version Define
* Fixed reset of needles out of active needle area
* Added support for I2C port expander on shield v1.3TH (MCP23008)

#### GUI

* requires APIv4
* Basic visualisation of pattern position
* Mouse wheel zooming of pattern
* Visualisation of Test Mode data
* Auto-Init functionality (no need to click OK several times when starting to knit)
* Firmware database moved to external JSON file
* Fix pattern rotation direction
* Fix pattern inversion
* Fix growth of image when rotating
* Fix unlocking of knit controls after image manipulation

### 0.75 (February 2015)

#### Firmware

* Fixed Lace carriage support

### 0.7 (February 2015)

#### Firmware

* Lace carriage support

#### GUI

* Showing info about current line number
* Some layout fixes (disabling UI elements, ...)
* Starting to knit with the bottom of the image
* Fixed progressbar in 2 color doublebed mode
* Start and Stop needle selection like on the machine (orange/green)
* Infinite Repeat functionality
* Cancel button added