# BRIDGE System Administration



## To add a new user:

see notes on out old wiki:
http://paleo-wikis.ggy.bris.ac.uk/wiki/bridge/SystemAdmin/New-users

`sudo -i`  
Your password

`ssh-agent $SHELL ; ssh-add ; [root password]`

`cd ~swsvsalde/sbin/`  
`./add_bridge_user.sh -u [UoB username - top priority] -d [for debug - doesn't do anything] -n [surname etc. - uses ldap] -e "2017-12-01" [expiry date] [-g miocene,lentil] [-s ksh] [-q is for quiet]`

Then type number.  
Default is for one year.  
Standard bash is in /etc/skel

## To modify a user:

### Expiration date:
`sudo -i`  
`chage -l [USER]` : check for expiration date  
`usermod -e YYYY-MM-DD [USER]` 

### Disk space:
To change array quota:  
`xfs_quota -x -c 'report -h' /export/silurian/array-01`  
`xfs_quota -x -c "limit bhard=50000g ggdjl" /export/silurian/array-01`  
`xfs_quota -x -c "limit bsoft=49000g ggdjl" /export/silurian/array-01`

To change home quota:  
`edquota -u ggdjl`

Open a new or existing file with:  
`vim filename`  
Type i to switch into insert mode so that you can start editing the file.  Enter or modify the text with your file.  Once you're done, press the escape key Esc to get out of insert mode and back to command mode. Type `:wq` to save and exit your file.  To exit Vi/Vim, type `:q` and hit Enter.





