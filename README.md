<h1>Using Linux commands to manage file permissions</h1>


<h2>Description</h2>
The research team at an organization needs to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks:
<br />


<h2>Check file and directory details</h2>
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Screenshot 2023-08-20 6 05 56 PM](https://github.com/mmedinabet/mmedinabet/assets/142737434/3d7cc316-b4ee-4293-831c-f7211b253572)


The screenshot's initial line exhibits the command I inputted, while subsequent lines showcase the output line. The provided code enumerates all items within the projects directory. I employed the ls command with the -la parameter to present an elaborate inventory of file contents, encompassing concealed files. The output of my command reveals the presence of a directory named "drafts," an obscured file titled ".project_x.txt," and an additional five project files. The sequence of ten characters in the opening column signifies the permissions designated to each file or directory.

<h2> Explain the Permissions String</h2>
Breaking down the 10-character string allows for the identification of authorized users and their specific access privileges. The characters and their corresponding meanings are as follows:

- <b>1st character: This character represents the file type and is either a d (for directory) or a hyphen (-) for a regular file.</b>

- <b>2nd-4th characters: These characters signify the user's read (r), write (w), and execute (x) permissions. The presence of a hyphen (-) indicates the absence of that particular permission for the user.</b>

- <b>5th-7th characters: These characters denote the group's read (r), write (w), and execute (x) permissions. A hyphen (-) signifies the lack of that specific permission within the group.</b>

- <b>8th-10th characters: These characters indicate other users' read (r), write (w), and execute (x) permissions. In this context, "other" refers to all users except the owner and the group. The presence of a hyphen (-) signifies the exclusion of that permission for other users.</b>

<h2>Change file permissions</h2>
The organization concluded that other users should not possess write access to any of their files. To adhere to this requirement, I consulted the file permissions that I had previously retrieved. After assessing the situation, I recognized that it was necessary to revoke write access for other users on the "project_k.txt" file.

![Screenshot 2023-08-20 6 29 39 PM](https://github.com/mmedinabet/Using-Linux-commands-to-manage-file-permissions/assets/142737434/7777479c-43bf-483f-9c23-7e6c9e43034c)


The initial two lines in the screenshot showcase the commands I inputted, while the subsequent lines exhibit the output of the second command. The chmod command is responsible for modifying permissions on files and directories. The first parameter defines the permissions to be altered, and the second parameter designates the file or directory. In this instance, I eliminated write permissions for "other" on the "project_k.txt" file. Following this adjustment, I employed "ls -la" to assess the modifications I implemented.

<h2> Change file permissions on a hidden file </h2>
The organization's research team has recently stored away the file project_x.txt. Their intention is to restrict write access to this project, while maintaining read access for both the user and the group.

Below is an example of the Linux commands I employed to modify the permissions:

![Screenshot 2023-08-20 6 32 02 PM](https://github.com/mmedinabet/Using-Linux-commands-to-manage-file-permissions/assets/142737434/534344cd-d862-4c8e-8fc3-4e87cbe2d6f6)

The initial two lines in the screenshot exhibit the commands I inputted, while the subsequent lines exhibit the output stemming from the second command. I am aware that the file .project_x.txt is concealed, as it initiates with a period (.). In this illustration, I eliminated the user and group's ability to write by utilizing u-w. Subsequently, I revoked the group's write permission using g-w and appended read permission using g+r.

<h2>Change directory permissions</h2>
In the organization, exclusive access to the drafts directory and its contents is reserved solely for the user named researcher2. This implies that no individual apart from researcher2 should possess execution privileges.

The subsequent code illustrates the manner in which I employed Linux commands to alter the permissions:

![Screenshot 2023-08-20 6 34 31 PM](https://github.com/mmedinabet/Using-Linux-commands-to-manage-file-permissions/assets/142737434/f2845195-a069-4541-9d5b-1d22de0f9e3d)


The initial two lines within the screenshot exhibit the commands I inputted, while the subsequent lines present the output stemming from the second command. I had previously identified that the group possessed execute permissions, prompting me to utilize the chmod command to revoke them. Since the researcher2 user was already endowed with execute permissions, no further action was necessary in that regard.

<h2> Summary</h2> 
I changed numerous permissions to align with the authorization level sought by the organization for files and directories within the projects directory. This process began with using "ls -la" to inspect the directory's permissions, which then guided my subsequent actions. I subsequently employed the chmod command on multiple occasions to modify permissions for both files and directories.

</p>



 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
