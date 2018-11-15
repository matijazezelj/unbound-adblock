# unbound-adblock

this is setup to wrk with opnsense unbound DNS server

To make it work clone this repo somewhere on your router.

run update-hosts.sh

when script is done go to router webui -> services -> unbound DNS -> general -> advanced and under Custom options add:

include:/var/unbound/ad-blacklist.conf

After that you can restart/reload unbound and it will block ads.

Atm following lists are used:

http://winhelp2002.mvps.org/hosts.txt
http://pgl.yoyo.org/as/serverlist.php?hostformat=hosts&showintro=0&mimetype=plaintext
https://adaway.org/hosts.txt
https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts
https://mirror1.malwaredomains.com/files/justdomains
http://sysctl.org/cameleon/hosts
https://zeustracker.abuse.ch/blocklist.php?download=domainblocklist
https://s3.amazonaws.com/lists.disconnect.me/simple_tracking.txt
https://s3.amazonaws.com/lists.disconnect.me/simple_ad.txt
https://hosts-file.net/ad_servers.txt

This script WAS NOT originally written by me!

I found it on https://devinstechblog.com/block-ads-with-dns-in-opnsense/ and modified it a bit

Lists used here are all default pihole lists which are proven good and valid and some additional found online

Please add more lists if you want. awk line will change any line taht has  something like

0.0.0.0 foo.bar

or

127.0.0.1 foo.bar

to unbound format.
