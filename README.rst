pyEfis
==================
This is an experimental system, and is not suited for primary or backup flight or engine instrumentation. Use at your own risk. 

Getting Started
---------------

For more detailed documentation see: https://github.com/makerplane/Documentation

1. `sudo apt install python3-pyqt5`
2. Install this package dependencies: `sudo python3 -m pip install -r requirements.txt`
3. Install `FIX-Gateway <https://github.com/makerplane/FIX-Gateway>`_  and run.

Controls
--------

This is an Electronic Flight Information System written in Python.

It was created for use in the MakerPlane Open Source Aircraft Project.

It does not have any method of reading flight information directly from the
hardware but instead uses FIX Gateway as it's source of information.  FIX
Gateway is a plugin based program that allows different types of flight
information systems to communicate to one another.  pyEfis contains a client
to FIX Gateway and so has access to all the flight data that FIX Gateway
is configured for.

Controls

'[' and ']' Keys changes the Altimeter Setting

'm' Changes Airspeed mode from IAS , TAS, and GS

'a' and 's' select the different screens.

Virtual VFR
-----------------------------

In order to take advantage of virtual
VFR chart object rendering, download the latest FAA CIFP file from here:
https://www.faa.gov/air_traffic/flight_info/aeronav/digital_products/cifp/download/

Extract the FAACIFP18 file into the pyEfis/CIFP directory. Make note of the FAA
disclaimers also in the zip file.

Create an index file:
'''
./MakeCIFPIndex.py CIFP/FAACIFP18
'''

This creates an index.bin file in CIFP directory

Update the config file [Screen.PFD] section dbpath and indexpath
with the path names of the FAACIFP18 and index.bin files respectively.
