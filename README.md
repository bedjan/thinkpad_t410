# thinkpad_t410

#### ThinkPad_T410

http://www.notebookreview.com/notebookreview/lenovo-thinkpad-t410-review/

#### Ovladače Win7 64 bit
https://yadi.sk/d/eNpemYGv3MLdDZ

#### Linux
[http://www.thinkwiki.org/wiki/Installing_Ubuntu_11.10_(Oineric_Ocelot)_on_a_ThinkPad_T410](Installing Ubuntu 11.10 Oineric Ocelot on a ThinkPad T410)

[Think wiky](http://www.thinkwiki.org/wiki/Category:T410|Category:T410)

[Gentoo_on_a_ThinkPad_T410](http://www.thinkwiki.org/wiki/Installing_Gentoo_on_a_ThinkPad_T410)

#### Linux sudo práva

sudo -s
visudo

UZIVATEL  ALL=(ALL) NOPASSWD: /usr/bin/lxtask

UZIVATEL  ALL=(ALL) NOPASSWD: /sbin/shutdown

UZIVATEL  ALL=(ALL) NOPASSWD: /usr/sbin/synaptic

UZIVATEL  ALL=(ALL) NOPASSWD: /usr/bin/leafpad

UZIVATEL  ALL=(ALL) NOPASSWD: /sbin/modprobe


#### HDAPS (Hard Drive Active Protection System)

You need the ThinkPad SMAPI and the hdaps-daemon, install them by following command:

<code>sudo apt-get install tp-smapi-dkms hdapsd</code>

Edit /etc/default/hdapsd with root privileges:

START=yes         # hdaps should be started automatically

DISK=sda          # normally sda should fit 

SENSITIVITY=15    # higher values mean lesser sensitivity 

FORCEENABLE="no"  # force hdaps, not needed

OPTIONS=""        # additional options, not needed

Restart the daemon:

<code>sudo /etc/init.d/hdapsd restart</code>

Testing (stop daemon and start in foreground):

<code>sudo /etc/init.d/hdapsd stop</code>

<code>sudo hdapsd -d sda -s 15</code>

If you shake your T410 gently the output should look like:

<code>sudo /etc/init.d/hdapsd start</code>

</code>sven@T410:~$ <code>sudo hdapsd -d sda -s 15</code>

Tue Nov 15 13:25:25 2011: Starting hdaps
Tue Nov 15 13:25:25 2011: Selected interface: HDAPS
Tue Nov 15 13:25:25 2011: Selected HDAPS input device: /dev/input/event9
Tue Nov 15 13:25:28 2011: parking
Tue Nov 15 13:25:29 2011: un-parking

If test was succesful start daemon again:

<code>sudo /etc/init.d/hdapsd start</code>
