====================

# ScoreTrace

====================

**NOTICE: Some antivirus tools or browsers may flag ScoreTrace.exe as suspicious due to its self-contained packaging. We assure you this is a clean build compiled from self written code with no malicious intent. If blocked, you may need to unblock or whitelist the file manually. In the future we will apply for certification or develop an official installer to avoid false warnings.**


📊 What is ScoreTrace?

ScoreTrace has been completely reworked into a lightweight, multi-platform application that can parse data from a Daktronics AllSport 5000. Previous versions, while they worked well, required a direct link to the AllSport. With the redesign, ScoreTrace can now be deployed on a Raspberry Pi and accessed remotely via the local network as all output data from ScoreTrace is hosted in a json formatted WebAPI rather than an actual json file. We hope the time that has been spent on rebuilding this program pays off for those that use it.

--------------------------

🚀 Getting Started

There are a few ways to use ScoreTrace.

Running it Local
It can be launched on a laptop with direct connection to the AllSport 5000.
1. Launch the ScoreTrace_Local.exe file
2. select the sport you want (currently only implemented Football and Basketball but will be adding more in the future)
3. select the COM port for the scoreboard (see "Selecting COM Port" below for help on this)
4. Click "Launch ScoreTrace". You may get a network access popup since it now hosts ScoreTrace via WebAPI. Simply allow this and you should see a notice in the window stating it has started.
5. Check the status of ScoreTrace by using http://localhost:5000 or add a path to the end of this link for more details (see paths below)

Running it Remotely
Please see the txt file called "Raspberry Pi Setup.txt" for steps on how to build your own raspberry pi device for ScoreTrace.
It can also be hosted on a Raspberry Pi devices such as a Raspberry Pi Zero for minimal footprint. Steps below assume you already have a Pi setup with ScoreTrace
1. plug the Pi in to the AllSport via a serial data cable and power it on
2. open ScoreTrace_RemotePi.exe on any windows laptop connected to the same network as the pi
3. using the IP address of the Pi and the password you set for it, select the sport you want and click "Launch ScoreTrace"
4. Check the status of ScoreTrace by typing http://0.0.0.0:5000 into your browser and replace the 0s with your Pi's IP address (see paths below for more detailed options)
5. It is very important that after conclusion of the event, you power down the Pi correctly before cutting power to it. This is all handled by the "Shutdown Pi" button on the Launcher. Failure to do so can lead to corruption of the Pi's SD card. If this happens, its not the end of the world. The SD card will simply need to be reflashed and ScoreTrace reinstalled.


Many of the fields may start blank. This is due to the way the AllSport sends its data and is unavoidable. Fortunately as soon as the game clock is started/stopped, it will send a complete packet and ScoreTrace will then use it to synchronize all available fields.

--------------------------

🚀 Setting up Scorebug software

Most testing has been done with vMix using titles designed in GT Title designer but has also worked with NewBlue. Simply add a JSON data source and use the IP address or localhost link as the URL with "/ScoreTrace" appended to the end. examples of this would look like "http://0.0.0.0:5000/ScoreTrace" or "http://localhost:5000/ScoreTrace". For decimal point accuracy, set the refresh rate on the data source to every 100ms instead of the default 1000ms. Once the data populates, assign each data point to the value it represents in your scorebug.

--------------------------

🛠 Selecting COM Port

On the Local exe version, you are asked which COM port to use, if you are unsure, you can unplug the AllSport and use the refresh ports button to see which number disappears. Reconnect the AllSport and the number port that reappears upon refresh, is the correct one.

the Remote version *should* always use the same COM port. If there is any issues with the incorrect port being used on the Pi, you will need to access the Pi and determine the correct port to use and change the code in the ScoreTrace.py file on the Pi as it is defaults to "/dev/ttyUSB0". This change is made on line 12 of the code.

--------------------------

🛠 Paths for ScoreTrace

These paths are added to the end of the IP address after the port number
- "/ScoreTrace" provides a snapshot of the output data from ScoreTrace in the json format
- "/Status" gives a bit more specific status details of how ScoreTrace's WebAPI is work

More paths may be added in the future for more functionality.

--------------------------

🛠 Troubleshooting

- If the data does not read properly, make sure you have a cord that is capable of passing serial data using an RS-232 serial cord with FTDI chipset. This is not a printer cable and example cord that has been tested can be found at https://www.amazon.com/dp/B08ZK78LHC?ref=ppx_yo2ov_dt_b_fed_asin_title&th=1. Using a cord that is a non-RS232 or non-FTDI cable may result in dropped packets, no data, or unstable COM ports.
- If ScoreTrace is confirmed working on one device but data is not being read on a remote device, ensure they are connected to the same network, this is especially important when using RemotePi.exe as it will tell you no Pi found if not on the same network.
- If the Daktronics Scoreboard is disrupted for any reason and the connection to ScoreTrace breaks (particularly using it remotely on a Raspberry Pi. A simple restart of the Pi can correct the issue. This has only happened once during testing and has not been replicated so troubleshooting is limited at this point, though it was able to be corrected within 60 seconds or so.

--------------------------

🧠 Credits 

Created by AJ Fairchild on behalf of Tinora Rams Live and is being developed for community use.

--------------------------

📬 Feedback & Support

While testing ScoreTrace, feel free to leave feedback on our Discord

--------------------------

📊 Disclaimer

ScoreTrace is third‑party software and is not affiliated with, endorsed by, or supported by Daktronics or any scoreboard manufacturer. Use of this software is at your own risk. The developers of ScoreTrace assume no responsibility for hardware malfunctions, data errors, system crashes, or any damage resulting from the use of this application. Connecting ScoreTrace to a scoreboard or control system may affect manufacturer warranties; users are solely responsible for ensuring compliance with all warranty terms and equipment guidelines.
