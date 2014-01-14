---
layout: post
title: "Installing Mongodb in Windows 8"
date: 2013-12-30 13:29:18 +0530
comments: false
published: false
categories: MongoDB
keywords: 
description: 
---

There are two ways to install Mongodb in windows.

*	Installing with Chocolatey package manager
*	Manual Installation


####Installing with chocolatey package manager
This is the easiest way to install Mongodb. First you need to install Chocolatey package manager. Chocolatey is a quick Linux style package manager for windows. Installing Chocolatey is very easy. Just copy paste below line to your command line and run it as Administrator
```
@powershell -NoProfile -ExecutionPolicy unrestricted -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%systemdrive%\chocolatey\bin
```
Now you are ready to go, To install MongoDB, run the following command from the command line or from PowerShell:
```
 cinst mongodb
```
Chocolatey will download and install the latest version of Mongodb in your system. Also it will add Mongdb as a windows service.   

####Manual Installation
The MongoDB does not have an installer. For Windows platform, MongoDB distributes a zip archive. Download the latest production relese from the following page: http://www.mongodb.org/downloads. There are 32-bit and 64-bit versions, download the correct version as per your system architecture. If you dont know your system architecture run the following command from your command line: 
```
wmic os get osarchitecture
```
After download extract the zip archive to your C:\ drive rename the folder from

