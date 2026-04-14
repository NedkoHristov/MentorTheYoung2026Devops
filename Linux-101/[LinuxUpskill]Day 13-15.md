# DAY 13

This day is about users and groups. We create a user and a group, then add the user to an existing group as well. There are two common ways to create users. One is with adduser. This is the easier, more user-friendly method. It automatically creates a home directory, sets up a group with the same name as the user, and prompts you to set a password and some optional info. \
The other way is with useradd. This is a lower-level command and does not do much by default. You usually have to specify things like the home directory, shell, and password yourself. It gives you more control, but requires more manual setup. \
Here is a showcase for today's task - https://imgur.com/a/zrEaq6h

# DAY 14

this day is about file permissions and ownership, basically controlling who can read write or execute files, and how ownership ties into users and groups. we use chmod, chown and chgrp to manage that. I understand the principle, every file has an owner and a group, and permissions are split into user group and others, so access is always checked against those. instead of just thinking “can i open this file”, it’s more like “who am i and what rights do i have on it”.

Here is a quick demo - https://imgur.com/a/oI69ynl 

# DAY 15

This day is about repositories and how software installation actually works under the hood with apt instead of blindly using apt install, we now look at sources, versions and how to extend or modify them.\
The system pulls packages from defined repositories listed under /etc/apt, mainly in sources.list. Each repo is tied to your system version, which is why you don’t always get the newest software but a stable one. if you want more or newer packages, you can enable extra repos or add external ones, but that comes with some risk depending on the source. Demo for today - https://imgur.com/a/Rwpa5z4