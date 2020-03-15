Welcome to Local Work Tracker! 

Use lwt.py to track project work sessions, and goals.py to track project goals. This document explains how, but it assumes the audience has at least my level of skill in Python (intermediate based on about two years practice). 

Other Resources:

You can read an article with detailed directions for using the scripts, meant for people who have no knowledge of such things, and it includes intros to programming concepts and helpful links along the way: (coming by March 15th 2020)

You can also read an article about the tracking method, how I came to use it and the concepts I'm testing out with this production: (coming by March 15th 2020)

How to set it up:

To run these scripts you'll need Python3 and the python module openpyxl. If you're using a mac, you'll need to install mpg123.

The scripts are meant to be run from a Python shell in Windows Command or Mac Terminal. They save data to spreadsheets that are saved in sub-directories of the folder the scripts are saved in. Similarly, the work-timer and break-timer alarms are chosen from .mp3 files available in sub-directories of the folder the scripts are saved in. Download or Clone the scripts to a folder that is in a higher-level directory than any of your project folders (where you'll keep their respective tracking spreadsheets), but not higher than you need because the lwt.py script searchers all sub-folders for .mp3 and .xlsx files, which could take a while depending on how many files it has to search through. 

In a folder that contains some big-part of your work, like a job for a client, or an area of your life (e.g. chores), or anything that can be divided into one or more projects, create a folder called "tracking". In the folder create a spreadsheet called goals.xlsx, and a .xlsx file for each project (called anything but goals). The tracking files will have additional categories of work-types for each project; I typically have writing, reading, brainstorming, admin (e.g. emails), and sometimes more specific stuff like doing-the-final-edit or checking-all-the-links.

starting lwt.py and goals.py:

1) start the python shell (if in Windows, from command line type: title tracker)
2) type: from lwt import LWT
3) type: a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT() 
4) start another python shell (if in Windows, from command line type: title goals)
5) type: from goals import Goals
6) type: a_variable_name_for_your_project_probably_best_to_keep_it_short = LWT() 

running lwt.py methods():

I run the class methods individually from this point. They each do some particular task, except for start(): it runs the next three listed methods because I almost always use them first in sequence.

method 1: start() #runs the next three methods in sequence
method 2: select() #lists all xlsx 


It's an open project:

If you'd like to help make it better, or if you have made your own better version, I would like to hear from you.
