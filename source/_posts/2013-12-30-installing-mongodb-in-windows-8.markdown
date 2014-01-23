---
layout: post
title: "Installing Mongodb in Windows"
date: 2014-01-07 13:29:18 +0530
comments: true
sharing: false
categories: MongoDB
keywords: Installing mongodb in windows, install mongodb chocolatey
description: Installing and configuring Mongodb in Windows
---

There are two ways to install [Mongodb](http://www.mongodb.org/) in windows.

*	Installing with Chocolatey package manager
*	Manual Installation


####Installing with chocolatey package manager
This is the easiest way to install Mongodb. First you need to install [Chocolatey](http://chocolatey.org/) package manager  . Chocolatey is a quick Linux style package manager for windows. Installing Chocolatey is very easy. Just copy paste below line to your command line and run it as Administrator
```
@powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%systemdrive%\chocolatey\bin
```
Now you are ready to go, To install MongoDB, run the following command from the command line or from PowerShell:
```
 cinst mongodb
```
Chocolatey will download and install the latest version of Mongodb in your system. Also it will add Mongdb as a windows service.   <!--more-->

####Manual Installation
The MongoDB does not have an installer. For Windows platform, MongoDB distributes a zip archive. Download the latest production relese from the following page: http://www.mongodb.org/downloads. There are 32-bit and 64-bit versions, download the correct version as per your system architecture. If you don't know your system architecture run the following command from your command line: 
```
wmic os get osarchitecture
```
After download extract the zip archive to your C:\ drive rename the folder and rename the folder to mongodb. MongoDB requires a data folder to store its files and a text file to log its output. Create two folders data and log inside the mongodb folder. For ease of installation crate a config file named mongo.config(just a text file) like below and and put it in the mongodb folder.

{% codeblock %}
##store data here
dbpath=C:\mongodb\data
 
##log file. Mongodb will create it automatically
logpath=C:\mongodb\log\mongo.log

#port
port = 27017

##log read and write operations
diaglog=3
{% endcodeblock %}

Now your mongodb folder will look like this
{% img https://lh5.googleusercontent.com/-HNWIrzMTRt8/UuE9AFPrFvI/AAAAAAAAAz8/TLzjmjPDCDQ/s618/Capture.PNG 150 250 'Mongodb folder' 'Mongodb folder_ajmalvh.com' %}

######Run Mongodb
For starting and stopping the mongodb server, we need only the mongod.exe inside the bin folder. To run mongod just run this command in the command line
```
C:\mongodb\bin\mongod.exe --config C:\mongodb\mongo.config
```
 Now you can use mongo.exe to connect to the started Mongodb server.

#### MongoDB as Windows Service
To install Mongodb as a service. Execute the following commands:
```
C:\mongodb\bin\mongod.exe --config C:\mongodb\mongo.config  --install
net start MongoDB
```
This will install mongodb as a windows service.
