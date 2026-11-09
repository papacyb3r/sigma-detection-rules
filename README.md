# Sigma Detection Rules

A small starter set of vendor-neutral [Sigma](https://github.com/SigmaHQ/sigma) detection rules, each mapped to a MITRE ATT&CK technique. Sigma rules can be converted to the query language of your SIEM (Splunk, Elastic, Microsoft Sentinel and others).

## Rules

| Rule | Technique | Level |
|---|---|---|
| [powershell_encoded_command.yml](powershell_encoded_command.yml) | T1059.001 PowerShell | medium |
| [security_log_cleared.yml](security_log_cleared.yml) | T1070.001 Clear Windows Event Logs | high |
| [shadow_copy_deletion.yml](shadow_copy_deletion.yml) | T1490 Inhibit System Recovery | high |
| [new_local_user_created.yml](new_local_user_created.yml) | T1136.001 Create Account: Local Account | low |

## Using the rules

Convert with [sigma-cli](https://github.com/SigmaHQ/sigma-cli) (pySigma):

~~~bash
sigma convert -t <backend> -p <pipeline> powershell_encoded_command.yml
~~~

Choose the backend and processing pipeline that match your SIEM and log source.

## Important

- These are starting points. Test every rule against your own log data and tune it to cut false positives before enabling alerts.
- Field names depend on your log source and pipeline, so check them against your environment.
- Status is *experimental* until validated in production.

## Ideas to extend

Linux authentication and sudo abuse, cloud audit log rules, and web server attack patterns.

## Author

Papa, GRC, Risk & Cybersecurity Compliance Leader. [LinkedIn](https://www.linkedin.com/in/owoahene)
