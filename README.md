====================

ScoreTrace v0.2.0

====================

**NOTICE: Some antivirus tools or browsers may flag ScoreTrace.exe as suspicious due to its self-contained packaging. We assure you this is a clean build compiled from self written code with no malicious intent. If blocked, you may need to unblock or whitelist the file manually. In the future we will apply for certification or develop an official installer to avoid false warnings.**


📊 What is ScoreTrace?

ScoreTrace is a lightweight Windows application that connects to scoreboard controllers and generates real-time XML data for broadcast overlays, dashboards, and live sports analytics. Designed for simplicity and reliability, ScoreTrace helps communities integrate live score data into their productions with zero technical overhead.

--------------------------

🚀 Getting Started

1. Double-click `ScoreTrace.exe` to launch the app.
2. Select your controller type from the dropdown.
3. Choose the correct COM port for your scoreboard (see "Selecting COM Port" for help on this).
4. Click **Run Script** to begin data transmission.
5. Click **Stop Script** to terminate the tracer.

When using the Daktronics tracer, many fields may start blank. This is due to the way the AllSport sends its data and is unavoidable. Fortunately as soon as the game clock is started/stopped, it will send a complete packet and ScoreTrace will then use it to synchronize all available fields.

--------------------------

🛠 Selecting COM Port

If more than one COM Port is available, you may disconnect the scoreboard controller and restart ScoreTrace. This will remove one from the list. Reconnect the scoreboard to your computer and restart ScoreTrace again. Now select the COM Port that has reappeared. This can also be done easily from the Device Manager as it can detect an changes in the COM ports available in real time while ScoreTrace needs to be restarted. (Hot-plugging or auto detecting COM port changes is a planned change for the near future)

--------------------------

📁 Folder Structure

ScoreTrace can be stored in any folder, on your PC or on an external storage such as a USB, ready for plug and play
- `ScoreTrace.exe` — the main launcher
- `Output/` — XML file is written here as `ScoreTrace Output.xml` and will be created adjacent to the .exe file

--------------------------

🛠 Troubleshooting
- If no COM ports appear, try reconnecting your scoreboard or restarting the app.
- If the XML file isn’t updating, check that the tracer script is running and your controller is transmitting data.

--------------------------

🧠 Credits 

Created by AJ Fairchild on behalf of Tinora Rams Live and is being developed for community use.

--------------------------

📬 Feedback & Support

While testing ScoreTrace, feel free to leave feedback on our Discord

--------------------------

🛠 Change Log

- Fixed an issue where starting and stopping the game clock would interrupt the data feed, causing a timeout exception
- Fixed a problem in which the data was not parsing fully when the Daktronics AllSport sent a full packet. The full "synchronizing" packet gets sent any time the game clock is stopped. This means that many fields may be blank until the first time the clock is stopped. This is not an issue with ScoreTrace, it is how the AllSport sends its information.
- Fixed "Ball On" variable had the incorrect index location and was returning a blank value.
- Changed: "Daktronics AllSport" is now the default tracer when opening ScoreTrace 

--------------------------

🚀 Upcoming changes

- Update will be coming in which the "Ball On" value gets a bit smarter. It currently only gives a yard line that is ambiguous to which side of the field its on. Daktronics outputs a 'full' variable in its packet that specifies which team has the ball, which direction they are going, and which side of the field they are on. For example, HRR35 indicated H=Home, R=Going right, R=on right side of the field, 35=current yard line. This will allow for more advanced parsing. The hope is to use these values to determine 1st/2nd and GOAL type situations automatically.

- Adding support for Hot-Plugging so that if you connect a scoreboard device after opening ScoreTrace, it will refresh the list live without needing to be restarted
