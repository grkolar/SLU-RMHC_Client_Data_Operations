# SLU-RMHC_Client_Data_Access
This a description of how to interact and retrieve your data with the SLU-RMHC.

- Table of Contents
  * [Using Billikenscope (OMERO)](#using-billikenscope--omero-)
  * [Using the RMHC FTPServer](#using-the-rmhc-ftpserver)
    + [Login Information](#login-information)
    + [Using Filezilla](#using-filezilla)
    + [Command Line Instructions](#command-line-instructions)
      - [Downloading your files (basic)](#downloading-your-files--basic-)
      - [Advanced Downloading](#advanced-downloading)
    + [Password Change](#password-change)

## Using Billikenscope (OMERO)

## Using the RMHC FTPServer
The sFTP site can be reached for registered users (using a an individually supplied username and password) via a FTP client such as Filezilla or the command line interface.  On a Mac or Linux system command line interface is via the terminal application and on Windows it can be sued via changes the the Powershell.  In all cases you must be either at SLU or logged in via GlobalProtect SLU VPN.

### Login Information
The sFTP IP address will be given to you along with your login information and the sFTP port is 22.  along with your username and password this should take you immediately to your user directory with your images.  

### Using Filezilla
Use the Login information above to plug into section just below the header on the Filezilla user interface.  Your directory should appear on the right hand panel and any download progress that you initiate should appear in the bottom box.

### Command Line Instructions
To Login

`sftp <username>@<IP address>`
  
Where `<username>` (including carrots) is replaced with the username and `<IP address>`  is the IP address given to you in an individual email.
You will then be prompted to enter your password in the blind.

#### Downloading your files (basic)
Once logged in you should be in your home directory with the command prompt.  To see the contents type

`ls -hl`

You will see a detailed list of the files.  You can then download your file using the command:

`get ./<filename> /path/to/local/directory`
  
Where you replace `<filename>` with the specific file you would like to download (you can use the tab key to expand unique names).  **The path to your local directory depends on your system.**

#### Advanced Downloading
We will attempt to organize your files in a directory for you.  Such directories (by user and date) will be appear as folders in the command line.  You will use the 

`cd <subdirectory_name>`

command to navigate to the directory and repeat the 

`ls -hl`

command.  Remember that all names with spaces must be enclosed in single or double quotes (we try not to have this situation).

If you wan to download the contents of a directory you can either use

`get ./* /<path to local directory>`

or for a file or use the -R flag (recursive) if providing the path to a directory.  Make sure you replace the text between the carrots with your local file path (without the carrots).

### Password Change
You should change your password from the default.  To do so you will need to open a SSH connection using the same information as above

`ssh <username>@<IP address>`
  
Enter you current password to get into the system then:
  
`passwd`
  
This will ask for your current password, a new password, and a confirmation.  We cannot look up your password but can reset it.
