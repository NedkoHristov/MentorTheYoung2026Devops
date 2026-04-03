# DAY 1
For the day you had to connect to your server via SSH. If it is a machine I will use frequently I also initiate a copying of my ssh key at the same time. For this task I used the ssh-copy-id command. 
An example would be: 

ssh-copy-id -i /home/user/.ssh/id_ed25519.pub  labuser@mentee 

This way it also checks beforehand if you've already set them up or not. \
Upon successful login I like to add the host to the config file (within the machine used for sshing ~/.ssh/config). Then logging becomes a matter of a single hostname. After logging I always check how the system is doing(usually htop). Today we had to inspect the system. I used the time to run a few standard commands (df -h , uname -a mostly for the kernel info, ) also reviewed the current OS (cat /etc/\*release*). Since this VM is practically unused there is nothing else to really dig into.  
Confirmed my network interface looks as I wish. 
Since this VM is a part of a machine I use frequently I know all about it's hardware capabilites.

# DAY 2

This section is all about the navigation within the system. Here we blend the introduction of basic commands used to move/rename (mv) copy (cp) list files and dirs (ls), change working directory (cd) 

To use all of these I decided to create a new directory within my ~ dir. \
 First check always where we are(pwd) in this case I was already in the wanted home directory. I could safely create it like this: mkdir example \
 Then i created a new file: touch firstFile.txt , after creation I decided to check what are the contains of the folder. Ran a ll comand(aliased command of ls -la, alternatively could also run it natively) Like so - https://imgur.com/a/lZtqp0r

This is all standard within linux but this day teaches an important thing about command exploration. It introduces arguably the most useful commands - man, help, type and apropos. Using these full-stack gems you can pretty much gather everything you need. \
Man (short for manual) is a pager styled help centre. You can explore the official documention and expand or completely learn a new command. The drawback here is that there might be quite a few commands without a manual. Actually I could only think of cd and alias as examples, these commands use the builtin "help"  documentation. It is less detailed and also comes without a pager, although it is usually more straightforward if you're not doing deep analysis. \
There is also the "apropos", used for searching via keywords - helps you find the command you forgot (of over 1000 :D) \
Now "type" is exactly the command which helps you seperate the builtin from the external ones. Also the stored folder (usually within /usr/bin..  ) \
Also briefly exposed the pushd and popd, I've read that especially for scripts they are not as recommended. For example they are only native to Bash and the Zshell. The idea is that for example - "cd /var/log/nginx/" (you review the badconfighelp.log) you then "pushd /etc/nginx/" hope you can find and edit whatever mess you made. Then you popd and go back into the logs directory directly, you can also nest it. for example a second pushd after the config, if you want to go back to the logs you would do popd and then popd again. This way you exit to the /var/log/nginx and clear the stack. You use "dirs -v" to display the current stack in numbered orderd. I mostly've used it with just pushd. Make a few dirs and then jump with pushd +(specific number you want to go to). Or with a cool checkpoint, using "pushd ." somewhere you want to return to, then you can do as many pushd ... as you wish. Using just popd after without worrying as the end of the stack is the one you wanted to be in. I've used it for some time but definetly still get confused if I get a 10+ stack and forgot what I wanted to do next :D 

# DAY 3

This day also teaches important stuff. \
Will start a bit backwards with sudo, specifically the difference between "sudo -s" and "sudo -i" then will mostly show the work via screenshots from the completed tasks. \
sudo -s , it allows for the current user to enter his sudo shell. For example $PATH is still that of the user, also the bashrc config, if you had any aliases or anything that normally you benefit from. 
sudo -i, this logs you as the actual root, here the $HOME is just /root . Eternal hole :D

That being said I think it is recommended to use sudo -i if you must escalate the access further from the typical sudoer. Your enviroment is clean, no users connected with it. They are both as dangerous as it gets and should be avoided, but would prefer to at least know that I am in a real root. - https://imgur.com/a/8LZOjbB

For the tasks today: \
Timezone - https://imgur.com/a/N4Kl2wX (at least here forgetting sudo let's you slip :D) \
Hostname - time to give it a more.. unique name https://imgur.com/a/fnRBEO5 \
Securing current user -  https://imgur.com/a/7qJltQD \
New use, using adduser - https://imgur.com/a/cncfhrR
