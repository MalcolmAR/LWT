<h1>Welcome to Local Work Tracker!</h1> 

Use lwt.py to track project work sessions, and goals.py to track project goals. This document explains how, but it assumes the audience has at least my level of skill in Python (intermediate based on about two years practice). 

<h2>Other Resources:</h2>

You can read an article with detailed directions for using the scripts, meant for people who have no knowledge of such things, and it includes intros to programming concepts and helpful links along the way: (coming by March 20th 2020)

You can also read an article about the tracking method, how I came to use it and the concepts I'm testing out with this production: (coming by March 20th 2020)

How to set it up:

To run these scripts you'll need Python3 and the python module openpyxl. If you're using a mac, you'll need to install mpg123.

The scripts are meant to be run from a Python shell in Windows Command or Mac Terminal. They save data to spreadsheets that are saved in sub-directories of the folder the scripts are saved in. Similarly, the work-timer and break-timer alarms are chosen from .mp3 files available in sub-directories of the folder the scripts are saved in. Download or Clone the scripts to a folder that is in a higher-level directory than any of your project folders (where you'll keep their respective tracking spreadsheets), but not higher than you need because the lwt.py script searches all sub-folders for .mp3 and .xlsx files, which could take a while depending on how many files it has to search through. 

In a folder that contains some big-part of your work, like a job for a client, or an area of your life (e.g. chores), or anything that can be divided into one or more projects, create a folder called "tracking". In the folder create a spreadsheet called goals.xlsx, and a .xlsx file for each project (called anything but goals). The tracking files will have additional categories of work-types for each project; I typically have writing, reading, brainstorming, admin (e.g. emails), and sometimes more specific stuff like doing-the-final-edit or checking-all-the-links.

starting lwt.py and goals.py:

<ul>
  <li>Step 1) start the python shell (if in Windows, from command line type: title tracker)</li>
  <li>Step 2) >>> from lwt import LWT</li>
  <li>Step 3) >>> a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT()</li>
  <li>Step 4) start another python shell (if in Windows, from command line type: title goals)</li>
  <li>Step 5) >>> from goals import Goals</li>
  <li>Step 6) >>> a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT()</li>
</ul>

running lwt.py methods():

I run the class methods individually from this point. The following methods represent some particular task, except for start(): it runs the three methods I almost always use first in a sequence.

method 1) start() #runs the next three methods in a sequence
method 2) select() #lists all the directory and sub-directories' .xlsx file paths with "tracking" in the path and asks you to select one (i.e. the project you're working on)
method 3) alarm() #lists all the directory and sub-directories' .mp3 files and asks you to choose one for the break timer and one for the work timer
method 4) work() asks for the number of work minutes, then break minutes, then displays a countdown timer for each beginning with the work timer. When the work-timer expires, it asks you to select or write the work-type, it displays notes and asks you to add any, and it displays stats for the session and continues on to the break timer. It will repeat this session until you ctrl-c to break from the script.
method 5) timer(integer_for_number_of_minutes) this method simply runs the countdown timer for the given number of minutes. I often use this to run a break when I exited the work() cycle after the work segment for whatever reason, because starting the cycle always goes to work first.
method 6) 



It's an open project:

If you'd like to help make it better, or if you have made your own better version, I would like to hear from you.
