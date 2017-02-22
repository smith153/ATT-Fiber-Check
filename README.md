# ATT-Fiber-Check
program to check where Fiber is available

Credit to MTdoyle for the original Century Link  speed checker
https://github.com/mtdoyle/cl_speedcheck

Requires Python 3.6  (3.5 WILL WORK)  
requires splinter package (pip install splinter or pip3 install splinter)  
requires pygeocoder package (pip install splinter or pip3 install splinter)  
Requires Phantomjs Web driver [Original Makers](http://phantomjs.org/)  
  
This script has been modified to handle LARGE swaths of land.  It has been coded to work in a defined API Limit and to stop on the hit.  Google has a limit of 2,500 hits per IP.  The script (address.py) **HITS TWICE FOR EACH SUCCESSFUL MATCH**  First to get a general address, then to get the "accurate" address.  When the API is hit, OR the API Limit you specify is hit it will write the changes and addresses to workdone (the Geocords) and addresses (the file that speedcheck uses).




Ubuntu 16.04 Install Process
(tested on FRESH install of ubuntu 16.04 Installed PYTHON3.5, Pip3 and below)

  
  ```bash
  git clone the repository and cd into it  
  
  sudo apt install python3.5  
  
  Sudo apt install python3-pip  
  
  pip3 install splinter  
  
  pip3 install pygeocoder  #(MAY NEED to use sudo -H pip3 install pygeocoder)  
  
  chmod +x installphantomjs.sh  
  
  sudo ./installphantomjs.sh
  ```
ON UBUNTU 16.04 A Script was Found [here](https://gist.github.com/julionc/7476620) This script was made by [gautiermichelin](https://gist.github.com/gautiermichelin) props to him 

Running the Program

In the directory this was cloned to.

screen python3.5 address.py (recommended to use screen based off the NEW functionality)

**IF CONTINUING WORK hit y or YES**  *Will be explained later*

Starting Address in Quotes "1600 Pennsylvania Ave NW, Washington, DC 20006"

It will ask a range, Valid answers are 100-*(I do not know have tested 3200+) (Meters: 1600 Meters is 1 Mile **A Duh Moment but This is why you use screen for LARGE areas)

It then calculates the Coords based off the "math" **TM**

It then asks whats the API Limit (I recommend 1000)

It then runs.  When it completes it creates the workdone and address files.

**CONTINUING WORK**

Run screen python3.5 address.py

type Y or Yes

It again asks for API Limit.  For a new day, new 1000.

The rest follows the normal path

python3.5 speedcheck.py

It will ask for the state.  Type in the 2 Letter State



use http://www.easymapmaker.com to create the map from the results file

The code probably needs lots of clean up. I have never programmed in Python until yesterday so forgive me for inaccuracies.
I am just glad I was able to port this over from the Century Link folks on dslr.

Anyone is welcome to modify and improve the code.


**FAQ**  
by ze Budman  
1. Why no Proxy or socks I see it in Previous commits.
  + I looked into it, It appears difficult to get a routine list, and I felt that it was bad form to skirt the limits by google.  I like to call this working within the restraints.
2. Why?
  + I wanted to learn python I enjoyed learning it, either going to work with another user on the Java phantom js or fix up the speedtest.py next. 

