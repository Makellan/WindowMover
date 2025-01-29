# WindowMover
AppleScript to move windows for designated apps to the designated monitor

Do you move your laptop back and forth to frequent locations like work, home, a friend's house, a significant other's house, your couch...?
Do you think that certain apps belong on certain monitors and wish that they'd just go back there?

ME TOO!

Here's a really basic script (no laughing!) for selecting which apps move to which monitors. I'm sure that there's probably a cleaner or cooler way to do this but here's one that works pretty reliably. 

Code Structure:
There's a set of paired lists of applications and monitors. You'll have to look at your Window menu to see what the system has named them. Each set is followed by a call to move the designated applications to the designated window. It's at the top for easy editing.
Code to bring this script back to the front after moving windows around. See Tips for why.
Function to move windows
  Nested loops to select the only window of every single-window app and use the Window menu item to move it.
  Nested loops to loop through every visibile window of every multi-window app and use the Window menu item to move it.


Configure:
For each monitor and set of apps, you'll need to edit two or three lines of the script:
set First_Application_List to {"Google Chrome", "Safari", "Notes", "Preview"}
1. Name the list whatever makes sense to you
2. Add the names of whatever apps you want on that monitor

set Home_Left_Monitor to "Move to HP LA2405x" *
1. Name the monitor whatever makes sense to you. See Tips.
2. Add the exact menu item name from the Window menu for the selection that will move a window to the correct monitor

Move_Windows(First_Application_List, Home_Left_Monitor)
1. If you've renamed the list or monitor, change the function call to use your new names


Limitations:
Not all apps support being moved by using the menu bar. For example, Discord only recently supported this feature.

Tips: 
1. Create as many copies of this as you have frequent locations. I have three of these for commonly visited locations.
2. The script comes back to the front after moving all the windows. This is because it seems to sometimes skip a window and I'll have to run it twice. That's pretty rare but it's not impossible. Adding delays would probably get rid of it but that would slow the whole thing down more than I like.
