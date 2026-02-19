====================

ScoreTrace 1.2.0

====================

**NOTICE: Some antivirus tools or browsers may flag ScoreTrace.exe as suspicious due to its self-contained packaging. We assure you this is a clean build compiled from self written code with no malicious intent. If blocked, you may need to unblock or whitelist the file manually. In the future we will apply for certification or develop an official installer to avoid false warnings.**


📊 What is ScoreTrace?

ScoreTrace has been completely reworked into a lightweight, multi-platform application that can parse data from a Daktronics AllSport 5000. Previous versions, while they worked well, required a direct link to the AllSport. With the redesign, ScoreTrace can now be deployed on a Raspberry Pi and accessed remotely via the local network as all output data from ScoreTrace is hosted in a json formatted WebAPI rather than an actual json file. We hope the time that has been spent on rebuilding this program pays off for those that use it.

--------------------------

🛠 **Changlog for version 1.2.0**

- added baseball/softball support. There are many data points that can be pulled from the AllSport 5000 for baseball and softball. The biggest limiting factor here will be how many of the features the scoreboard operator uses as I'm sure most keep very basic stats. Data points include but are not limited to: inning, balls, strikes, outs, total score, individual inning score (box score), errors, hits, etc. More data points may be added in the future but only upon request.
- made some fairly significant improvements to the code the reduced the overall complexity of the programming. This will make implementing new features much easier in the future.
- added a 'Copy URL' button that allows user to quickly copy and paste into their streaming software. Simply click the button and paste into the File/URL option of vMix or other scorebug software. If running the local exe on a remote laptop, you will still need to know the IP address of the laptop and enter the URL manually.
- added an alternating possession indicator for basketball. This shows as either a blank value or ">". Easiest setup for this point is to use a script to detect if its off (blank) or on (">") and allow the script to change the scorebug appearance.


**Known Issues**
- there is a potential issue with the football data point tied to 'Ball On' as it currently gives the same output as the 'To Go' data point. I am currently trying to find the source of this error but am unsure if it is an AllSport issue or ScoreTrace issue. Ideally this data point gives a bit more information that can be parsed in a way that the code can tell if its first and goal or simply first and 10.

--------------------------

🧠 Credits 

Created by AJ Fairchild on behalf of Tinora Rams Live and is being developed for community use.

--------------------------

📬 Feedback & Support

While testing ScoreTrace, feel free to leave feedback on our Discord

--------------------------

📊 Disclaimer

ScoreTrace is third‑party software and is not affiliated with, endorsed by, or supported by Daktronics or any scoreboard manufacturer. Use of this software is at your own risk. The developers of ScoreTrace assume no responsibility for hardware malfunctions, data errors, system crashes, or any damage resulting from the use of this application. Connecting ScoreTrace to a scoreboard or control system may affect manufacturer warranties; users are solely responsible for ensuring compliance with all warranty terms and equipment guidelines.
