# Calabrio_Automator
Context.

We FINALLY been able to create an automation bot that will bulk update Calabrio schedules.

Objective.

To have an automation to auto update, remove, replace, add shifts in Calabrio, without human interaction.

How it works?

Automator will open into a GUI screen where you can specify the required changes:

Team name:

Here you need to write team names, it can be an individual team, or multiple teams, separated by commas. e.g. “CS APAC ASIA 1,CS APAC ASIA 2” 

 N.B. don’t leave any spaces after the comma between team names. 

We selected CS APAC ASIA 1,2 teams here for testing

Old activity:

That’s the name of the activity to be replaced. 

Despite that each team may have different names for live channels activities, Automator can smartly recognize and consolidate live channel activities into either Phones, Chats, or Emails. .  

Example: you don’t have to select “E Email How It Works” or “Voice - English - Europe”, just select “Emails” or “Phones” and it will do that rest for you.   

New Activity:

That’s the name of the activity to be added instead. 

In this step you have to be specific on what should be the new activity, so, If it’s “E Email How it Works”, then you should select that, and not “Emails” only. 

It will still work if you selected Emails only, but for later reporting purposes, we’d be better off unifying those activities per team.  

Date Range:

That’s simply the date range we’d like to modify. 

Dates are inclusive, so selecting 1-Oct to 10-Oct, means both 1st and 10th of Oct are included.

If the range is only 1 day, FROM and TO fields can be the date. 

Hours difference from UTC:

Write here the difference between your OWN time zone vs UTC time in hours.

Example1: Running the script from Tallinn, the number will be 3

Example2: Running from TPA, the number will be -4  



All parameters are set and ready now!! In this case, we’re replacing all Admin hours with Phones for CS APAC ASIA 1,2 teams from 1st-9th Sep. 

Now hit RUN and let the magic begin!   



Now Microsoft Edge browser window will open, login using your normal Calabrio credentials. 

Then make sure to select the required business unit, e.g. CS, KYC, PayOPS..etc. 

Login using your Calabrio credentials normally



Select required business unit from the list



 Admin activity at 5:30 was replaced with Phones



We can see first admin activity at 5:30AM was replaced by Phones.

Now you can click anywhere on the screen to hide Microsoft Edge and continue what you were doing,
don’t worry, Automator will continue doing the work in the background. 


N.B. It’s recommended to click anywhere around Edge window to hide it, and NOT to use “_” minimize icon, as this will slow down the automation, because Edge throttles PC memory flow to any minimized windows.

Even if you forgot and clicked minimize, no worries, it will still work, but a bit slower. 

Actions Log:



Automator will log every action taken on schedules into the following path

 C:\Calabrio\Your_Windows_Username_Date_Time.txt

All logs are tagged by username, time, agent name, activity and new activity name. 



Sample Video:





Where to download?



Automator will log every action taken on schedules into the following path

 C:\Calabrio\Your_Windows_Username_Date_Time.txt

All logs are tagged by username, time, agent name, activity and new activity name. 



Technical Stuff - For geeks:



The script was built in Python, using pyodbc library to connect to Calabrio CRA tables. 

selenium.webdriver library was used to automate browser actions. 

Finally, to create the GUI, PySimpleGUI was used.
