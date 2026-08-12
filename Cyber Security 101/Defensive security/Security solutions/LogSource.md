

## Windows Machine

Windows records every event that can be viewed through the Event Viewer. It assigns a unique ID to each type of log activity, making it easy for the analyst to examine and keep track of. To view events in a Windows environment, type `Event Viewer` in the search bar.

## Linux Machine

Linux OS stores all the related logs, such as events, errors, warnings, etc. These are then ingested into SIEM for continuous monitoring. Some of the common locations where Linux stores logs are:

- /var/log/httpd: Contains HTTP Request  / Response and error logs.
- /var/log/cron: Events related to cron jobs are stored in this location.
- /var/log/auth.log and /var/log/secure: Stores authentication-related logs.
- /var/log/kern: This file stores kernel-related events.

## Web Server

It is important to monitor all requests/responses coming in and out of the web server for any potential web attack attempt. In , common locations to write all apache-related logs are /var/log/apache or /var/log/httpd.



![](../../assets/Pasted%20image%2020260810012349.png)


### Log Ingestion

**Log ingestion** means collecting logs and sending them to a centralized SIEM.

- **Agent/Forwarder:** Software installed on endpoints that sends logs to the SIEM.
    
- **Syslog:** Protocol used to send logs from servers, devices, etc. to a central system.
    
- **Manual Upload:** Offline log files are uploaded for analysis.
    
- **Port Forwarding:** Devices send logs to a specific listening port on the SIEM.