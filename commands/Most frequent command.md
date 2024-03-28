* List of all files and directory in the current directory.
  * Ls
  * Ls -l // To view details/permission of directory and file Long format
  * Ls -a // To view hidden files
  
* File all related application
      * dpkg -L neo4j
* Change current shell
    * Csh // The shells are Tcsh, csh(c-shell), bash(Bourne-Again shell)
* Unzip tar
    * Tar -xvzf filename
        * tar xvjf file.tar.tbz 
        * dtrx file.tar.gz 
        * dtrx file.tar.bz2 
        * 7z x file.7z
    * Zip

* Zip Folder
  ```
  tar -zcvf log.tar.gz logs/
  zip -r folder.zip folder/
  ```
* Print current shell name
    * $shell
* Check RAM
    * free
* Change directory
    * Cd /tmp // Change to temp
    * Cd .. // Go to previous directory
* Print current working directory
    * pwd
* Change password
    * Passwd
    * Sudo su // for root
    * passwd
* Create new directory in the current directory
    * Mkdir newFolderName
* Remove directory.
    * Rmdir directoryName 
* Copy file from USB drive to harddisk
* fdisk -l - to check the drive names mount /dev/sdb1 /media cd media cp filename.ext /home/user
    * Increase the reading number of file: 
* ulimit -n 4096
* Make background process 
    * setsid skype
* Copy files from one system to another system 
    * scp orbeon-2016.1.201604200638-PE.zip enkindle@192.168.0.16:/home/enkindle
* Connect to remote system
    * ssh {userName}@{ipaddress}
* Create link 
        * sudo ln -s /usr/local/apache-maven-3.3.3/bin/mvn /usr/bin/mvn
* Change the permission of directory or file use chmod
        * chmod 777 <fileName or directoryName>
* Change directory and its sub folder use -R
        * chmod 777 -R <fileName or directoryName>
* 
    * Change to root directory
        * /
    * Grep
        * grep {search content} {file name}
        * grep 192.168.0.24 /config/ip.config
    * Directory Usage
        * du
    * File System usage
        * df
* Editor:VI:
    * Go to last page of file => Esc + G 
* VPN: 
    * To install open openConnect (Cisco AnyConnect mobile)
        * sudo apt-get install openconnect 
        * sudo openconnect 173.231. 120.210 // To connect
* 
    * Install OpenConnect gnome
        * sudo apt-get install network-manager-openconnect-gnome
* Virtual box:
    * CTRL + C ===> Switch from scale mode (To show the menu bar of virtual box)
* 
    * To increase/decrease virtual machine hard disk size
        * Open a terminal and navigate to the folder with the VirtualBox disk image, then use the following command: 
            * VBoxManage modifyhd YOUR_HARD_DISK.vdi --resize SIZE_IN_MB
* EG:
    * Thirumals-MacBook-Air:Windows 10 Thirumal $ VBoxManage modifyhd Windows\ 10.vdi --resize 35840
* 0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
* SSH:-
  * To remove host identification
    * ssh-keygen -R <host>
    * Eg: ssh-keygen -R 192.168.0.14
* 
•	Command	•	Function	•	remarks
•	echo $PATH	•	To know all environments variables	•
•	Which	•	To know where the command executable file is located.	•
•	Du	•	Display disk usage statistics To get current directory space
	•	du -sh ./*/
	•	du -cksh *
	•	du -h -d 1
	•	df -h --total
	•	df -a -h
	•	Du -h --max-depth=1 /opt/alfresco	•	du -k - Display sizes in Kilobytes.du -h - Display sizes in human readable format. For example, 1.2M, 3.7G, etc.
•	Cal	•	Calendar	•
•	.	•	This directory	•
•	..	•	Parent directory	•
•	/	•	Directory separator	•
•	Ls -lF	•	List file by type/ ==> directory@ ==> Link. The file that follows the -> symbol is the target of the link.	
•	chmod	•	Change permission	•	$ ls -l sales.data-rw-rw-r-- 1 bob users 10400 Sep 27 08:52 sales.data$ chmod g-w sales.data$ ls -l sales.data-rw-r--r-- 1 bob users 10400 Sep 27 08:52 sales.data$ ls -l sales.data-rw-r--r-- 1 bob users 10400 Sep 27 08:52 sales.data$ chmod g+wx sales.data$ ls -l sales.data-rw-rwxr-- 1 bob users 10400 Sep 27 08:52 sales.data$ ls -l sales.data-rw-r--r-- 1 bob users 10400 Sep 27 08:52 sales.data$ chmod ug+wx sales.data$ ls -l sales.data-rwxrwxr-- 1 bob users 10400 Sep 27 08:52 sales.data
•	Watch	•	To check memory usage	•	watch -n 5 free -m
•	Number of lines in the directory	•	find . -name '*.java' | xargs cat | wc -l	•	find . -name '*.java' | xargs cat | wc -l
•	Process elapsed time	•	ps -p <process_id> -o etime	•
•		
•	*	•	Executable program	•	
•	-a	•	All files, including hidden files
•	--color	•	List files with colorized output
•	-d	•	List directory names and not their contents
•	-l	•	Long format
•	-r	•	Reverse order
•	-R	•	List files recursively
•	-t	•	Sort by time, most recently modified first
•	
•	Symbolic	•	Octal	•	Use Case / Meaning
•	-rwx------	•	700	•	Ensures a file can only be read, edited, and executed by the owner. No others on the system have access.
•	-rwxr-xr-x	•	755	•	Allows everyone on the system to execute the file but only the owner can edit it.
•	-rw-rw-r--	•	664	•	Allows a group of people to modify the file and let others read it.
•	-rw-rw----	•	660	•	Allows a group of people to modify the file and not let others read it.
•	-rw-r--r--	•	644	•	Allows everyone on the system to read the file but only the owner can edit it.
•		
