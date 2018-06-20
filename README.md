# fixpoint
The linux NetworkManager tries to optimise your connection by scanning and rescanning to find the access point with the strongest signal. In this aspect, it is a bit too zealous and causes alot of short disconnects due to constantly droping the connection in favor of connecting to the better accesspoint, even if it only one percent better.

The script can list the known networks, which should be configured before you use fixpoint.\
Then you can tell the NetworkManager, thorugh the fixpoint command, to lock to a particular access point.\
When you change your position you should drop the lock or simply refresh your lock when you sit at a new location. 

### using fixpoint
Call:\
&nbsp;&nbsp;./fixpoint command

Parameters:\
&nbsp;&nbsp;list&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;lists all known networks\
&nbsp;&nbsp;lock [NETWORK]&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;find the best accesspoint for the given networkfile and bind the network to it\
&nbsp;&nbsp;drop [NETWORK]&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;drop the fix on accesspoint to the given network\
&nbsp;&nbsp;refresh [NETWORK]&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;first drop the fix on an accesspoint of given\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;network then find the best accesspoint for the given network and last bind the network to it

&nbsp;&nbsp;\*note that if NETWORK is not given the actual connected network is choosen and also note if NETWORK has spaces in its\
&nbsp;&nbsp;&nbsp;name, put it between "" (double quoutes)

Examples:\
&nbsp;&nbsp;fixpoint refresh "wireless connection 1"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"wireless connection 1" gets locked to the best available accesspoint and\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;delivers a stable connection

### installation guide
I have not managed to write a install script but it is very uncomplicated.

1. open the Terminal
2. copy fixpoint in /bin/\
&nbsp;&nbsp;&nbsp;&nbsp;$ sudo cp fixpoint /bin/
3. copy fixpoint_auto in /etc/bash_completion.d/\
&nbsp;&nbsp;&nbsp;&nbsp;$ sudo cp fixpoint_auto /etc/bash_completion.d/
4. run fixpoint_auto once ... from now it will start on boot\
&nbsp;&nbsp;&nbsp;&nbsp;$ . /etc/bash_completion.d/fixpoint_auto

And you're done.
