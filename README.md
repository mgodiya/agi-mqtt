agi-mqtt
========

Asterisk to MQTT Bridge

Installation
============

Clone repository somewhere convenient, possibly /etc/asterisk/agi.

Install python AGI (pip install pyst2)

Copy mqtt.cfg.sample to mqtt.cfg and edit the values. username/password are optional.


Integration
===========

Asterisk
--------

extensions.conf snippet:

```
exten => 43123456789,1,AGI(/etc/asterisk/agi/mqtt,/etc/asterisk/agi/mqtt.cfg,calls/${ARG1})
```


mqttwarn
--------

(See https://github.com/jpmens/mqttwarn for info about mqttwarn.)

Example config snippet:
```
[calls/missed]
targets = log:info, xmpp:ch
format = From {callerid} ({calleridname}) at {_dthhmm} for {extension}
title = Missed call
```
