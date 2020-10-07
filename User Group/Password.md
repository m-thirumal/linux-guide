#### Change Your User Password
    $passwd
    $Enter new UNIX password:
    $Retype new UNIX password:
    $passwd: password updated successfully
#### Change Another User’s Password
    $sudo passwd thirumal
    $Enter new UNIX password:
    $Retype new UNIX password:
    $passwd: password updated successfully
#### Force User to Change Password at Next Login 
By default, passwords are set to never expire. To force a user to change their password the next time they log in, use the passwd command with `--expire` option followed by the username of the user
   
    $sudo passwd --expire thirumal
    $ssh thirumal@192.168.0.1
    $WARNING: Your password has expired.
    $You must change your password now and login again!
    $Changing password for thirumal.
    $(current) UNIX password:
    $Enter new UNIX password:
    $Retype new UNIX password:
    $passwd: password updated successfully
    $Connection to 192.168.0.1 closed.