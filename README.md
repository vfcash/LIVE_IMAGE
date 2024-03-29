The VFCASH network has been mostly unused for the majority of its life span. Unfortunately the server hosting the VFCASH services was compromised on two occasions that I am aware of in the last 6 months, for this reason I have decided to permanently terminate the only remaining VFCASH node.

The "blockchain" file is from the 12th of February 2023 at 19:52 hours with the last transaction being made on the 30th of November 2022. Some time between 19:52 hours on the 12th and 08:15 hours on the 13th (UTC) of February 2023 an attacker who either already had access to the server from a prior date or gained access between the specified hours performed a surgical take down of the VFCASH network by erasing all of the files from the server related to the VFCASH program and the two blockchain backups on removable, but at the time mounted drives - leaving only the www directory intact and other services the server had running.

I don't know how access was gained to the server and for this reason, it's become more hassle than it is worth to keep the node running.

This repository contains the blockchain file and the www directory for the now defunct [vfcash.uk](https://vfcash.uk) website.

The script I was using to populate the graphdata directory was:
```
vfc minted >> /var/www/html/graphdata/allminted_pm.txt
date +%s >> /var/www/html/graphdata/alldate_pm.txt
tail -360 /var/www/html/graphdata/allminted_pm.txt > /var/www/html/graphdata/minted_pm.txt
stat --printf="%s\n" /srv/.vfc/blocks.dat >> /var/www/html/graphdata/alltrans_pm.txt
tail -360 /var/www/html/graphdata/alltrans_pm.txt > /var/www/html/graphdata/trans_pm.txt
```
