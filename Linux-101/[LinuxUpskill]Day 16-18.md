# DAY 16

This day is about archiving and compression, something you’ll use all the time for backups or moving data. Key point, they are not the same. Archiving just bundles files together, compression actually reduces size. Usually you do both together. Compression is straightforward with gzip. By default it replaces the file, so if you want to keep the original you use -k. Decompression is just -d. Text compresses well, already compressed files don’t. \
Tar is for bundling files. You create a .tar from a directory, and the -f flag is important because whatever follows it is treated as the archive name. Combine archiving and compression with -z to create a .tar.gz in one step. \
Extraction is easy but checking first is probably even more important. Use -t to preview contents, otherwise you risk dumping files everywhere (tarbomb). Using -c to control where things get extracted.

Today's demo - https://imgur.com/a/SKM5yj1 

# DAY 17

This day is about stepping outside the comfort of package managers and actually building software from source, which is useful but also where things can get messy if you don’t know what you’re doing. \
From there we move into the standard build flow with ./configure, make, and make install, understanding while exploring what which step does. 
We also look at where binaries end up, how multiple versions can exist at the same time. \
Big takeaway is that this bypasses apt completely, so updates and dependencies are now your responsibility, which is fine for tools like nmap but risky for anything critical, definitely something to be aware of moving forward. \
Quick demo for today's eventful day - https://imgur.com/a/jrI68yK

# DAY 18

This day is about logs and not letting them quietly absorb your entire disk space and mess things up.
We go through /var/log and apache2 logs, checking how rotation already works and noticing the compressed older files. \
Then we tie it to cron, since logrotate runs automatically from /etc/cron.daily, so this whole thing is handled in the background. \
After that we look into the configs in /etc/logrotate.conf and /etc/logrotate.d/apache2 to understand how rotation, compression and retention are defined.
In the end we tweak apache2 to rotate logs daily instead of weekly, just adjusting defaults to something more practical. \
The task was a bit different on my side - https://imgur.com/a/mG2BO3Y