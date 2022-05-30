DISCLAIMER
================

The whole content of this repository were not made by me, the owner. I simply copied other people's codes into this repository and test if they would work properly. In other words, I am testing them. These people are the true creator's of the codes:

  * phyunsj, https://github.com/phyunsj

  * Sevenmojoe, https://github.com/Sevenmojoe
  
Both of them can be found in github. I took the internet simulator codes from phyunsj, and the Node-RED deployment codes from joeartsea. Here is their repository link respectively:

  * IoT Simulator, https://github.com/phyunsj/iot-device-simulator-1-mqtt

  * Deploy Node-RED to Heroku, https://github.com/Sevenmojoe/nodered-heroku

I can not be more thankful to them for their aid in my journey through my DAA class, even though they do not and perhaps will never know me.

### In case I haven't made this clear, I DO NOT own nor create the codes which are located in this repository.

================

# nodered-heroku
A wrapper for deploying [Node-RED](http://nodered.org) into the [Heroku](https://www.heroku.com).
* DEMO: Flow Editor - [https://nodered-heroku.herokuapp.com/editor](https://nodered-heroku.herokuapp.com/editor)
* DEMO: Dashboard UI - [https://nodered-heroku.herokuapp.com](https://nodered-heroku.herokuapp.com)


## Warning: Heroku doesn't automatically save flows, credentials and installed nodes
```
[TL,DR] Use the SAVE Inject node in the first flow (see step 5).
```
To overcome this, after having deployed the new flows, export All flows as *flows.json* file, and push it to the GitHub repo linked to Heroku. Do the same with *flows_cred.json* and *package.json* for credentials and nodes installed in Palette. Detail on step 5.

## 1. Deploying Node-RED to Heroku 
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy?template=https://github.com/hybuild-project/nodered-heroku)

## 2. Set up GitHub repo and Heroku app
* Fork this GitHub repo.
* Set GitHub as deploy source on Heroku setting. 
* Enable Automatic Deployment, so that every time any file is pushed to GitHub repo, Heroku will rebuild Node-RED with updated files.

## 3. Password protect the flow editor
Set username and password for Node-RED Flow Editor:
* **NODE_RED_USERNAME** - the username to secure the Flow Editor with
* **NODE_RED_PASSWORD** - the password to secure the Flow Editor with

## 4. Access Node-Red on Cloud
* Flow Editor - [nodered-on-cloud.herokuapp.com/editor](https://nodered-on-cloud.herokuapp.com/editor)
* Dashboard UI - [nodered-on-cloud.herokuapp.com/ui](https://nodered-on-cloud.herokuapp.com/ui)
* Home page - [nodered-on-cloud.herokuapp.com](https://nodered-on-cloud.herokuapp.com)

## 5. Export all flows, credentials and installed nodes
### Manual mode (original)
* In Editor, to export *flows.json*, click hamburger icon `☰` (top right), click Export, choose tab "All flows", then Download.
* To export all the other files, browse the <i>/app</i> folder, e.g., with this [flow](https://flows.nodered.org/flow/44bc7ad491aacb4253dd8a5f757b5407) or the [modified version](utils/file-explorer-flow.json), and download all files.
* Push *flows.json*, *flows_cred.json*, *package.json* to GitHub, so that Node-RED is rebuilt with the latest files at Heroku restart.
### Alternative mode (recommended)
* Use the `SAVE` Inject node in the [first flow](utils/save-all-changes-flow.json) to directly push all files to GitHub.

![SAVE](public/images/save-button.png)

## Some included nodes
* Dashboard UI - node-red-dashboard
* MQTT - node-red-contrib-aedes
* Blynk Cloud - node-red-contrib-blynk-ws
* Email - node-red-node-email
* Telegram - node-red-contrib-telegrambot-home
* InfluxDB, MongoDB, Modbus, OPC UA, Netatmo, PostgresSQL, Wordmap, etc. 
