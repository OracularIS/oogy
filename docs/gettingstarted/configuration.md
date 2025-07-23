# OOGY Configurations Files

The below section will explain you how to configure OOGY.

The following two files are in Program Data as shown below.
1. **config.yaml**
2. **application.properties**
 


<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/01-Config-Files.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>

## 1. Config.Yaml File

Configure Moca environments with the following key value parameters.

- ID: Unique name of the server

- WH: Warehouse ID 

- Service URL: Moca Server URL

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/02-Yaml-Config-File.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>

## 2.  Application.Property File

- Edit the application.properties file and set the server. Port variable. This is the SSL PORT.

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/03-App-Config-Yaml.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>

- Copy Moca file to the installed location. This file is required for OOGy to connect with the Moca instances.

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/04-Moca-Core.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
     </div>

## Services

Below section will explain you how to start and stop services. 

### Run Service Manually ## 

Open the location where OOGY is installed and double click on startup.bat to start OOGY

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/05-Start-Up-bat.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>
    <br>
    
This will initiate the services manually.

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/Manual-Start.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>
    <br>

### Start and Stop Service

User can start and stop OOGY service from the Windows Services as shown in the following image: Right click on the service name and there it can be stopped if in running state OR can be started if it is stopped.

<div style="text-align: left;">
     <img src="../assets/oogyconfiguration/start-stop.png"
       alt="java 1"
       style="height: 200px; margin: auto; display: block; cursor: zoom-in;
              border: 2px solid #000000; border-radius: 4px;"
       onclick="this.style.height='400px'; this.style.cursor='zoom-out';"
       ondblclick="this.style.height='200px'; this.style.cursor='zoom-in';">
    </div>
    

---
<br>