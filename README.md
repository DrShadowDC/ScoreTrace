====================

ScoreTrace v0.4.0

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

- fixed an issue where if the app was opened without any COM ports being detected, it would fail to open. It will now give a warning stating no COM ports are available and give a "DEBUG" option in the drop down menu.
- added advanced Distance logic to determine if it is "& Goal". This exposes an additional output variable `FormattedDistance` that can be used instead of the standard `Distance`. This builds the Down and Distance (i.e. "1st & Goal" or "2nd & 9") together into a single value, only requiring one textbox in your streaming software.
- Scaling of the UI was fixed. Some computers squeeze the UI objects together, overlapping them, or enlarged them to where the UI was too big for the screen. This should be improved but may need more testing on more devices.
- Default tracer has been changed back to Debug as it allows for easier testing
- code optimizations 

--------------------------

🚀 Upcoming changes

- Adding support for Hot-Plugging so that if you connect a scoreboard device after opening ScoreTrace, it will refresh the list live without needing to be restarted
- Play clock feature (started implementing this but it was showing incorrect data occasionally, more testing is needed)
