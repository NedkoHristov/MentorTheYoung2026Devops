# DAY 7

This day is about services. More specifically about Apache, and today's task is to install and run an apache web server. \
One thing about such web servers(nginx, tomcat etc.) is that they get installed in an enabled and started state - https://imgur.com/a/06b1QPI \
Then let's check what the config file looks like, as we know by know they are within the /etc dir. 
It is pretty straightforward from there, you go on from the naming(apache2)->....conf, in some cases there are the .d directories containing additonal configs which are linked to the main one. This can be enabled/observed within the main config. Useful to not overload the main config file. https://imgur.com/a/R31CktB \
A look into the setup and the webpage, with the requests we made - https://imgur.com/a/Ng2JiTQ 

# DAY 8

This day is all about text processing, probably the most important thing to be confident in (I'm so so :D) \
We begin by using the "cat" command to review the access.log from earlier, we then kind of evolve from there.\
For today I will use this file and auth.log (in /var/log) with "cat, grep, tail, awk, sed" and will expirement different ideas.\
(skipping the pager examples as they are straightforward, manual text reviewing inside) - 
https://imgur.com/a/DBJzo8L , the topic is major and I am constantly working on improving my skill here. 

# DAY 9 

This day is about networking, more specifically firewalls and securing the enviroment. Since I am not under any attack vectors (localhost exposure) I will disable the http server we can showcase the principle. - https://imgur.com/a/nn7zm25