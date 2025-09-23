====================

ScoreTrace v0.1.0

====================

What is ScoreTrace?

ScoreTrace is a lightweight Windows application that connects to scoreboard controllers and generates real-time XML data for broadcast overlays, dashboards, and live sports analytics. Designed for simplicity and reliability, ScoreTrace helps communities integrate live score data into their productions with zero technical overhead.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Getting Started

1. Double-click `ScoreTrace.exe` to launch the app.
2. Select your controller type from the dropdown.
3. Choose the correct COM port for your scoreboard (see "Selecting COM Port" for help on this).
4. Click **Run Script** to begin data transmission.
5. Click **Stop Script** to terminate the tracer.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Selecting COM Port

If more than one COM Port is available, you may disconnect the scoreboard controller and restart ScoreTrace. This will remove one from the list. Reconnect the scoreboard to your computer and restart ScoreTrace again. Now select the COM Port that has reappeared. This can also be done easily from the Device Manager as it can detect an changes in the COM ports available in real time while ScoreTrace needs to be restarted. (Hot-plugging or auto detecting COM port changes is a planned change for the near future)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Folder Structure - ScoreTrace can be stored in any folder, on your PC or on an external storage such as a USB, ready for plug and play
- `ScoreTrace.exe` — the main launcher
- `Output/` — XML file is written here as `ScoreTrace Output.xml` and will be created adjacent to the .exe file

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Troubleshooting
- If no COM ports appear, try reconnecting your scoreboard or restarting the app.
- If the XML file isn’t updating, check that the tracer script is running and your controller is transmitting data.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Credits 

Created by AJ Fairchild

On behalf of Tinora Rams Live and is being developed for community use.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Feedback & Support

While testing ScoreTrace, feel free to leave feedback on our Discord
