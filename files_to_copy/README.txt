This directory should have two files:  00.timeout and 10.timeout 
and a third file that has the same name as one of these two but with no "." in the name.
 
Any file with a "." in its name, including this README.txt, has no effect on your sudo profile. 

The file without the "." in its name will change the timeout for your sudo command. 

Make sure you are in the  /etc/sudoers.d directory. 

To set the timeout to 10 minutes:
- Run: `sudo cp 10.timeout 10timeout`
- Run: `rm 00timeout`

To set the timeout to 0 minutes:
- Run `sudo cp 00.timeout 00timeout`
- Run `rm 10timeout` 

If both  00timeout and 10timeout are present in /etc/sudoers.d, the one that comes last in an alphanumeric 
sort will override any previous setting and will set the timeout. If there is no file that sets the timeout 
in this directory, the default, 5 minutes, will apply.
