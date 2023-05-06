# process-background
So i am doing a task right now, making Cent-OS bootable pendrive.

the command that is running right now:
```bash
sudo dd if=/home/aditya/Documents/CentOS-7-x86_64-DVD-1908.iso of=/dev/sdb
```
* Open a new terminal window or tab.
* Find the process ID of the dd command by running:
```bash
pgrep -l '^dd$'
```
* This will show the process ID and the command name (dd). For example:
```bash
26132 dd
```
* Send the USR1 signal to the dd process, which will make it output the current progress. Replace process_id with the actual process ID obtained in the previous step:
```bash
sudo kill -USR1 26132
```
* Switch back to the original terminal where you ran the dd command. You should now see an output similar to the following, indicating the current progress:
![image](https://user-images.githubusercontent.com/95766110/236603226-473cb92e-f0de-4952-8f54-4778ebf933f9.png)

> repeat the step again and again if you want see the progess
Alternatively, you can use the status=progress option when running the dd command to see the progress directly in the command output:
```bash
sudo dd if=/home/aditya/Documents/CentOS-7-x86_64-DVD-1908.iso of=/dev/sdb status=progress
```


