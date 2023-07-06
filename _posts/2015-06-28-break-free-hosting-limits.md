---
title: "Break free hosting limits"
date: 2015-06-28T13:10:30+05:30
categories:
  - blog
tags:
  - server
  - tech
---

Internet is full of free-hosting sites giving enough disk space and bandwidth to run a basic website for personal or even small scale business. Sites like 000webhost.com and 5GBfree.com are quite popular and give tough competition to their paid counterparts providing upto 99.9% uptime.

However, apart from the limited disk usage and bandwidth the most ubiquitous restriction to free-hosting are the restrictions to provide uniform distribution of resources for all users. Errors like these are known to webmasters -

```
Fatal error: Maximum execution time of 10 seconds exceeded
Fatal error: Allowed memory size of 67108864 bytes exhausted
```

These limitation on php configuration causes failure of execution of scripts. Popular examples are the failure of script execution in WordPress and Joomla. Recently while using a backup plugin, I faced the time limit exceeded error. The script needed more time for execution than that was defined as a max limit by the server/host.

There is a rather simple solution to this problem .

- Create a blank file named .htaccess
- Paste these values

```
php_value post_max_size 20M
php_value upload_max_filesize 20M
php_value memory_limit 512M
php_value max_execution_time 24
```

- Change the values as per requirement .

- Save the file in your public_html directory

What we just did ?

.htaccess is a configuration file for use on web servers running Apache and provides a way to make configuration changes on a per-directory basis. Hence we kinda override the global configuration set by host and modified the settings for our site.

Tested on WordPress 3.x on 000webhost.com