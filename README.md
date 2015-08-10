#Magnet Message

August 10, 2015

This repo contains a manifest file that can be used by the "repo" script to retrieve the various components of Magnet Message.

To use:

1.  Install Repo:
    ```
    $ mkdir ~/bin
    $ PATH=~/bin:$PATH
    $ curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
    $ chmod a+x ~/bin/repo
    ```
2. Create a directory for your source:
    ```
    $ mkdir ~/Projects/message
    $ cd ~/Projects/message
    ```
3. Initialize the repo:
    ```
    $ repo init -u git@github.com:magnetsystems/message-repo
    ```
4. Download the source:
    ```
    $ repo sync
    ```
 
For installation or troubleshooting information, refer to ‘troubleshooting’ in this distribution or Magnet Message Developer Guide located on the web at https://www.magnet.com/developer/magnet-message/

---

##What is Magnet Message?
  Magnet Message is full-featured, open source mobile messaging software that allows developers to easily add messaging functionality to their mobile applications. Magnet Message is delivered as a ready-to-run server and native mobile SDKs  for iOS and Android. Magnet Message is deployable in the cloud or on-premise and easily integrates with any app, existing system, or environment. For ease of administration, Magnet Message uses a web interface for configuration and management of the messaging server and reporting of in-app message and push notification delivery status.

  Highlights:
  
  - Push and In-App Messaging: Support for push notifications and two way, in-app messaging in your iOS or Android app via push notifications, in-app messages, or bi-directional chat. Rich client side SDKs and server side APIs let you target users, devices, topics, or tags. 
  - Rich Message Payloads: Send rich content, including documents, HTML, images, strings, JSON, and deep-links as the message payload.
  - Confirmed Delivery: Verify message receipts and open/read status to improve operations and compliance. 
  - Secure Messaging: Protect sensitive content by securing client-server connections (via TLS) and controlling the messaging infrastructure.
  - Open Source: Freedom to use, customize, and integrate.

For more details on Magnet Message, please visit: https://www.magnet.com/developer/magnet-message/

![Alt text](https://www.magnet.com/wp-content/uploads/2015/04/mag_message_logo_1950x992-300x153.png "Magnet Message")

---

##Requirements
  Magnet Message server requires:
   - JDK v6 or higher
   - MySQL v5.6 or higher

  Magnet Message Mobile Client SDKs require:
   Android: Android Studio 1.1 or higher
   Xcode: 6.3 or higher

---

##Features
  - Push notifications via Google Cloud Messaging (GCM) and Apple Push Notification Service (APNS)
  - In-app messaging (server to mobile and mobile to server)
  - Mobile to mobile messaging
  - REST API to send messages to users, devices, topics and tags
  - Pub/sub support
  - Support for rich message payloads
  - Confirmed message delivery and open/read status
  - Geo tracking support for active sessions
  - Notification expiration
  - Android and iOS SDKs
  - Administration web UI

---

##Known Issues
 - If there are port conflicts, installation may be blocked. To fix, free up the ports or assign a new port number for Magnet Message. Refer to instructions in the ‘troubleshooting’ doc provided in the distribution for details. 
 - In some situations, re-installing Magnet Message on a system may fail if the processes on the previous installation were not stopped properly prior to deletion. To fix, STOP the Magnet Message server. Refer to instructions in the ‘troubleshooting’ doc provided in the distribution for details.
 - In some situations, install may fail if the database is not running. Verify that MySQL is installed and running before installing Magnet Message on the system.    
 - Magnet messaging server has a write buffer of 5 MB per connected client. If a mobile client is too slow to consume messages addressed to it, then the message buffers on the server side start filling up; after the client's message buffer exceeds 5 MB the server will deem the client session to be stalled and will disconnect the client. You can manage this mechanism for throttling messages using the following two properties:
    - disable.kill.stalled.sessions: If set to true, the server will not disconnect clients. 
    - session.stalled.cap: Use this to specify the message buffer threshold in bytes; if this is exceeded, the server disconnects the client. 
 - In some situations, ”Path too long" error is shown when extracting mmx-standalone-dist-win.zip on Windows environments. This occurs when server install runs into the 260 character path name limit affecting all Windows operating systems when extracting the mmx-standalone-dist-win.zip due to the nested dependency structure of node.js. To fix this issue, extract the zip file into directories with a shorter path. 

---

##Ports
  For a list of ports or to change the default ports refer to ‘troubleshooting’ in this distribution.

---

##View Magnet Message Web Interface
  Messaging: http://127.0.0.1:3000/ (3000 is the default port number)

  Administration: http://127.0.0.1:3000/admin (3000 is the default port number)

---

##How to start, stop, or restart Magnet Message

  IMPORTANT: You should always start and stop the server with the included batch script (mmx.bat).

  Start
  Use a Command Prompt and cd to "mmx-standalone-dist-win" in the directory that you have unzipped the zip file to.
  Execute ".\mmx.bat start".

  Stop
  Use a Command Prompt and cd to "mmx-standalone-dist-win" in the directory that you have unzipped the zip file to.
  Execute ".\mmx.bat stop".

  Restart
  Use a Command Prompt and cd to "mmx-standalone-dist-win" in the directory that you have unzipped the zip file to.
  Execute ".\mmx.bat restart".

---

##Uninstall Magnet Message
   1. Stop the server (for steps, see ‘troubleshooting’ doc).
   2. Delete the Magnet Message home: ~/mmx-standalone-dist-<version>
   3. Remove the MySQL database schema that you have created for Magnet Message.

---

##Documentation
  Detailed documentation can be found at: https://www.magnet.com/developer/magnet-message/

---

##Licensing
  Magnet Message source code is governed under Apache version 2.0 license and it uses third party Open Source components that are governed under their own license terms. Refer to the following documents for details:

 - Apache version 2.0 license: see http://www.apache.org/licenses/LICENSE-2.0 or LICENSE.txt in this distribution
 - 3rd Party Open Source licenses: see LICENSE-3RD-PARTY.txt in this distribution

  All files are included in the root folder of your mmx-standalone-dist directory (or mmx-standalone-dist-win directory for Windows installations). 

---

##Contact
   - If you want to be informed about new code releases, bug fixes, security fixes,
     general news and information about Magnet Message, or other products
     from Magnet Systems, please visit our Developer Community: https://www.magnet.com/developer/

   - If you need support please visit: https://www.magnet.com/developer/ and view the Help Center or Forum. 

   - If you wish to report an issue or bug, please contact us via the link below:
     https://www.magnet.com/contact-us/



  -------------------------------------------------------------------------------
  Copyright info:
  The contents of this document are subject to change without notice.
  Copyright © 2015 Magnet Systems, Inc.
  All Rights Reserved. MAGNET SYSTEMS, the MAGNET SYSTEMS Logo and all other Magnet Systems product names are trademarks of Magnet Systems, Inc. All other trademarks are the property of their respective owners.
