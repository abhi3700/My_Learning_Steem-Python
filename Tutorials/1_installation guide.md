## URL - http://steem.readthedocs.io/en/latest/index.html
2 Methods to install - 

Method 1: 
1. Install using pip - 
	$ pip install steem

for upgrade using pip -
	$ pip install -U steem

NOTE: In windows, this is giving error of 'Microsoft Visual C++ 2015' file error "unistd.h" file.

*******************************************************************************************************************

Method 2:
1. Install 'Git' and get access from cmd.
2. Go to the required directory in cmd and download the folder using 'git' command.
	$ git clone https://github.com/steemit/steem-python
3. Now, a folder named "steem-python" is created. So, go to the folder using
	$ cd steem-python
4. Now, inside this folder, we can access the 'setup.py' file. So, install here using 
	$ python setup.py install

The software is installed successfully!!...

Check the installation from any directory in the computer by running some examples like

Run using python command in cmd or use different editor for writing codes and run in cmd using python
```
from steem import Steem
s = Steem()
s.get_account('ned')['sbd_balance']
```

*******************************************************************************************************************

### Resources - 
* https://utopian.io/utopian-io/@jefpatat/how-to-get-steem-python-working-on-windows
