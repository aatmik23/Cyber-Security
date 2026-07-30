cron process to execute each line step-by-step. Crontabs require 6 specific values:
**Crontab** is one of the processes that is started during boot, which is responsible for facilitating and managing cron jobs.


|   |   |
|---|---|
|Value|Description|
|MIN|What minute to execute at|
|HOUR|What hour to execute at|
|DOM|What day of the month to execute at|
|MON|What month of the year to execute at|
|DOW|What day of the week to execute at|
|CMD|The actual command that will be executed.|
`0 */12 * * * cp -R /home/cmnatic/Documents /var/backups/`

# Understanding `*/12`

This means:

> **Every 12 units.**
> 

(`*`). we dont want to give anyvalue

https://crontab-generator.org/
	 
Crontabs can be edited by using `crontab -e`
`crontab -l`   to see corn job

daemon - program run in background to perffromm specific task