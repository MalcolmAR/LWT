<h1>Welcome to the project page for Local Work Tracker!</h1> 

Use lwt.py to track project work sessions, and goals.py to track project goals. This document explains how, but it assumes the audience has at least my level of skill with Python and Windows Command or Mac Terminal (intermediate, based on about two years of steady practice). 

<h3>Other Resources:</h3>

You can read an article with detailed directions for using the scripts, meant for people who have no knowledge of such things, and it includes intros to programming concepts and helpful links along the way: (coming by March 20th 2020)

You can also read an article about the tracking method, how I came to use it and the concepts I'm testing out with this production: (coming by March 20th 2020)

<h2>How to set it up:</h2>

To run these scripts you'll need Python3 and the python module openpyxl. If you're using a mac, you'll need to install mpg123.

The scripts are meant to be run from a Python shell in Windows Command or Mac Terminal. They save data to spreadsheets that are saved in sub-directories of the folder the scripts are saved in. Similarly, the work-timer and break-timer alarms are chosen from .mp3 files available in sub-directories of the folder the scripts are saved in. Download or Clone the scripts to a folder that is in a higher-level directory than any of your project folders (where you'll keep their respective tracking spreadsheets), but not higher than you need because the lwt.py script searches all sub-folders for .mp3 and .xlsx files, which could take a while depending on how many files it has to search through. 

In a folder that contains some big-part of your work, like a job for a client, or an area of your life (e.g. chores), or anything that can be divided into one or more projects, create a folder called "tracking". In the folder create a spreadsheet called goals.xlsx, and a .xlsx file for each project (called anything but goals). The tracking files will have additional categories of work-types for each project; I typically have writing, reading, brainstorming, admin (e.g. emails), and sometimes more specific stuff like doing-the-final-edit or checking-all-the-links.

<h2>Using Work Tracker</h2>

<h3>starting lwt.py and goals.py:</h3>

<ul>
  <li>Step 1) start the python shell (if in Windows, from command line type: title tracker)</li>
  <li>Step 2) >>> from lwt import LWT</li>
  <li>Step 3) >>> a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT()</li>
  <li>Step 4) start another python shell (if in Windows, from command line type: title goals)</li>
  <li>Step 5) >>> from goals import Goals</li>
  <li>Step 6) >>> a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT()</li>
</ul>

<h3>running lwt.py methods():</h3>

I run the class methods individually from this point. The following methods represent some particular task, except for start(): it runs the three methods I almost always use first in a sequence.
<ul>
  <li>start() runs the next three methods in a sequence</li>
<li>select() lists all the directory and sub-directories' .xlsx file paths with "tracking" in the path and asks you to select one (i.e. the project you're working on)</li>
<li>alarm() lists all the directory and sub-directories' .mp3 files and asks you to choose one for the break timer and one for the work timer</li>
<li>work() asks for the number of work minutes, then break minutes, then displays a countdown timer for each beginning with the work timer. You can also enter run instead of an integer for minutes, which instead of running a timer will simply ask you to hit enter when the work or break session is over. When the work-timer expires, it asks you to select or write the work-type, then it displays notes previously written in this session and lets you write a new note, and finally it displays stats for the session and continues on to the break timer. It will repeat this cycle until you ctrl-c to break from the script.</li>
<li>timer(integer_for_number_of_minutes) this method simply runs the countdown timer for the given number of minutes. I often use this to run a break when I exited the work() cycle after the work segment for whatever reason, because starting the cycle always goes to work first.</li>
  <li>info_set() let's you set the number of work minutes and break minutes without running work(), in other words without actually using the timer. I always use this before using the next method, entry().</li>
  <li>entry() use this to make a work session entry without actually running the timers. The number of minutes it enters will be whatever was set last with work(), or with info_set().
  <li>stats() this will show you the amount of time you've spent on each work-type by day, then as a total, and then it shows the total time spent on the project.</li> 
</ul>

<h3>runnin goals.py methods():</h3>

Just like with lwt.py, I use these scripts by running class methods. An entry into the Goals.xlsx file includes a field for all projects associated with the goal. When you check how long you've been working on a goal, what you'll see is a sum of minutes you've spent working on all projects associated with the goal since the goal's start date. 

<h4>establishing and accomplishing goals</h4>

<ul>
  <li>gselect() lists all .xlsx file-paths with goals in the file-path and asks you to select one. Remember that one goals.xlsx file is created for a collection of projects in one folder (which should represent some larger category of work that can be subdivided into a number of projects). This is important because for each new goal, goals.py will ask you to associate it with one or more projects from the same folder with the goals.py file. This lets you set project-specific goals or goals for the larger category of work that span multiple projects</li>
  <li>add() lets you add a new goal and select which projects the goal is affiliated with.</li>
  <li>edit() lets you edit the goal (i.e. the way it's written)</li>
  <li>accomplished() set's the goal as accomplished and time-stamps the end time (the time it took to complete the goal will be the sum of minutes spent on all affiliated projects between the start and end times).
  <li>stop() when the stop field has a value it decalres the goal null, which means it will no longer show up in stats. This can be used when you no longer want to work on a goal, or when a goal has been accomplished but you no longer want it showing up in the stats. To delete a goal, edit the spread sheet, but make sure to delete the whole spread sheet row or else LWT will keep reading and reproducing the empty values in the row.</li>  
</ul>

<h4>Goal stats and other tools</h4>

<ul>
  <li>stats(*args) this will give a list of all goals with the total time spent on each goal, and a breakdown of time spent on each work-type for each project. The argument 'running' will return a list of goals excluding those that are accomplished. The argument 'lite' will return just the total time spent on the goal, none of the other stats.<li>
  <li>pselect(*args) this will ask you to select a project, then will list the goals and stats affiliated with that project. The 'lite' and 'running' arguments mentioned in stats(*args) will work here too.</li>
  <li>notes(*args) this allows you to add a note to the goal. The note will have a date-stamp added (a date-string in the note-string, not a datetime object), and previous notes will be displayed for the selected goal. The argument 'list' can be used to simply display the notes, not add one.</li>
</ul>


