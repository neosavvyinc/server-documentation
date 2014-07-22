### Ghost Server

 This is where our blog lives
 
### Ghost Installation

 I followed the instructions here to make sure we always have our servers 
 restarting on reboot: http://0v.org/installing-ghost-on-ubuntu-nginx-and-mysql/

 Each of our user's has a blog installed in `/opt/adam`, `/opt/trevor`, `/opt/chris` and so on.
 
 The `config.js` has key parameters for setting the external URL that would be used for links
 within the app. Also the port is important so we can host multiple instances on this machine.
     
    ```
    adam   -> Port 2000
    trevor -> Port 2001
    chris  -> Port 2002
    pablo  -> Port 2003
    sushi  -> Port 2004
    ```
     
 If a new user is added then all we have to do is copy the `/opt/ghost` directory and change 
 the config.js file along with the start.sh script. Adding the entry to crontab will ensure
 that their blog starts when the server reboots.
 
 Additionally adding a stanza to the proxy as per these instructions [here](../vm0/PROXY.md)