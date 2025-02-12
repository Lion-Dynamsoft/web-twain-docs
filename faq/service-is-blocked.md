---
layout: default-layout
noTitleIndex: true
needAutoGenerateSidebar: true
title:  The scanner's UI or the system's file dialog does not open when scanning
keywords: Dynamic Web TWAIN, Dynamsoft Service, scanner UI, file dialog
breadcrumbText:  The scanner's UI or the system's file dialog does not open when scanning
description:  The scanner's UI or the system's file dialog does not open when scanning
permalink: /faq/service-is-blocked.html
---

# Project Deployment and End-user Installation

## The scanner's UI or the system's file dialog does not open when scanning


### Symptom

Dynamsoft Service is installed successfully, but when attempting to scan or load files, the scanner's UI or the system's file dialog does not open. You may also see the error, "The pipe is being closed."

### Cause

This can be due to permissions, firewall, or other programs (e.g. anti-virus) blocking connections to the Dynamsoft Service.

To determine if Dynamsoft Service is blocked by another process, open Task Manager and go to the Details Tab.

Typically, before opening the scan page, you will see three Dynamsoft Service processes listed: two under SYSTEM and one under the user account.

![service blocked-1]({{site.assets}}imgs/service-blocked-1.png)

When you open the scan page, two new processes are created under the user account.

![service blocked-2]({{site.assets}}imgs/service-blocked-2.png)

If these two processes are not under the user account, we can confirm that Dynamsoft Service is being blocked by another process.

### Resolution

To determine which process is blocking Dynamsoft Service, please follow the steps below.

1. Collect <a href="{{site.faq}}general-troubleshooting-steps.html#how-to-enable-and-collect-verbose-log" target="_blank">verbose log</a>

2. Open the file wts.log and search for the string "GetConnectionProcessID" to locate the line:
*GetConnectionProcessID:: connection client 1960 process is xxxxx.*

[xxxxx] indicates the connection process id, which will identify a process in Task Manager. This process should should typically be a browser process.

![service blocked-3]({{site.assets}}imgs/service-blocked-3.png)

However, if the identified PID is not a browser process as expected, the PID will typically be the process which is blocking Dynamsoft Service.

If you need further assistance, please contact Dynamsoft Support.
