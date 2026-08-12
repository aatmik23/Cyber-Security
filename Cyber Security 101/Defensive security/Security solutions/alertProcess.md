
## Use-Case 1:

Adversaries tend to remove the logs during the post-exploitation phase to remove their tracks. A unique Event ID **104** is logged every time a user tries to remove or clear event logs. To create a rule based on this activity, we can set the condition as follows:

**Rule:** If the Log source is WinEventLog **AND** EventID is **104** - Trigger an alert `Event Log Cleared`

## Use-Case 2:

attacker un whoami 

**Rule:** If Log Source is WinEventLog **AND** EventCode is **4688,** and NewProcessName 
contains **whoami,** then Trigger an ALERT `WHOAMI command Execution DETECTED`

