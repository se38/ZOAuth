# ZOAuth
The ABAP OAuth Handler
 
Nugget: NUGG_TWIBAP.nugg
 
* NW 7.00: in addition to the OAuth nugged, please install also the Javascript Slinkees delivered with all ZOAuth releases (since 0.1.3) in the right order
* NW 7.01: no Javascript sources needed
 
If you have installed the whole Twibap packages (JSON, OAUTH, TWIBAP) and only want to use it for Twitter, you don't need to read the following notes, all the methods, except the setup tasks as mentioned in the Twibap wiki, are called within the Twibap API.
 
The following informations are only needed for standalone usage of the OAuth package!
 
## Required Packages
* JSON Document Class (see https://github.com/se38/zJSON )
 
## Installation
* Download Nugged (incl. required packages) and install via [SAPlink](http://www.saplink.org)
* Activate all inactive objects.
 
If your service provider needs SSL requests (https://), you have to activate the HTTPS port in your system. (For installation informations have a look at the SCN blogs for [Windows](http://scn.sap.com/community/netweaver-as/blog/2005/10/11/setup-https-ssl-for-the-sneak-preview-sap-netweaver-04-abap-edition-on-windows) and [Linux](http://scn.sap.com/community/netweaver-as/blog/2005/04/01/setup-https-for-the-sap-netweaver-testdrive-sr1-on-linux), thanks @wolf_gregor). Additionally you have to import the certificates of your service provider (the whole chain!) into your system, see OSS note 1094342 (thanks @rmtiwari) and Document "[Import StreamWork Certificate](http://wiki.scn.sap.com/wiki/display/SWAPI/Importing+StreamWork+SSL+certificate+into+ABAP+systems)" by Benjamin Merkle / project "Streamwork ABAP Client"
 
## Register Application
An application must be registered at your service provider. After your registration, you'll get the consumer key and consumer secret.
 
Start the report Z_OAUTH_SETUP_1_API_KEY and enter key and secret. The field "Consumer Name" can be left blank (only necessary, if you want to implement more than one client in your system).
 
## Register User
Each user must allow the application to handle actions in the name of the user. Start report Z_OAUTH_SETUP_2_REGISTER_USER, enter user and password on service provider page (if not already logged in) and press "Allow". You'll get a PIN or something similar which you enter on the SAP screen.
 
If you are the only user in your SAP system (e.g. on NSP), you can leave the field "password" blank, else you should also enter a password to protect your credentials.

## Usage
see wiki ( https://github.com/se38/ZOAuth/wiki )

## License
This software is published under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0.html)
