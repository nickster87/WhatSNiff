WhatSNiff
=========

A tiny PHP mitm proxy to retrieve your WhatsApp password during registration.

I've tested it only on Windows and Android, but it should work on other platforms as well.

REQUIRES ROOT ON ANDROID DEVICE (you'll be editing the hosts file)

Instructions:
Set up server:
  - Install WAMP server 2.2 32-bit http://www.wampserver.com/en/#download-wrapper
  - Copy the contents of apache/ to c:/wamp/bin/apache/apache/apache2.2.22/conf/
  - Enable these PHP extensions: curl and openssl
  - Copy the folder whatsapp/ to c:/wamp/www/
  - Restart Apache

Set up Android device:
  - Install the app Hosts Editor http://play.google.com/store/apps/details?id=com.treb.hosts
  - Add a new hosts entry:
      
    - IP:   your Windows machine running WAMP server and WhatSNiff
    - Host: v.whatsapp.net
  - Copy apache/server.crt to the root of your SD card
  - Go to Settings->Security->Install Certificates and install it.
  - BACK UP YOUR WHATSAPP CONVERSATIONS!
  - Clear WhatsApp application data
  
Using WhatSNiff:
  - Just make sure your phone is on the same subnet as your Windows machine.
  - Open WhatsApp on your phone, enter your number and finish the setup.
  - Your password will show up in c:/wamp/www/whatsapp/v2/exist.log
  
TODO:
  - Check compatibility with other platforms (e.g. OS X, Linux, iOS, Windows Phone 7.5)
  - Test the instructions above to see if I forgot anything, it's 03:30 AM ok..? :(
