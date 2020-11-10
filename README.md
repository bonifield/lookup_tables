# Lookup Tables

### A collection of various useful lookup tables for Splunk, or any other program that can parse CSVs (Python, Excel, etc). Lookups provide an easy way to enrich your data by using a separate file to add context to your logs.

### Regarding Splunk lookups, here is [official Splunk lookup documentation](https://docs.splunk.com/Documentation/Splunk/7.3.1/Knowledge/DefineanautomaticlookupinSplunkWeb), this one from [Hurricane Labs](https://www.hurricanelabs.com/blog/splunk-enterprise-security-automatic-identity-lookup-tables-using-active-directory-ldap), or follow the steps below:
- Settings --> Lookups
	- Lookup table files --> Add new
		- upload the table, provide the name of the file as it will appear in Splunk (just use the same name AND INCLUDE THE EXTENSION)
	- Lookup definitions --> Add new
		- select the app (likely Search), set the name (same as the CSV name, MINUS the extension, or with _definition suffix), File-based, select the lookup added in the previous step
		- Advanced options --> un-check "Case sensitive match"
	- Automatic lookups --> Add new
		- set the name, select the lookup definition (again, based on the file uploaded), set the sourcetype to be affected
		- input field: left is the name inside the CSV/definition, right is field name CURRENTLY in the Splunk database. This is how the CSV joins/aligns itself to Splunk data.
		- output field: left is the name inside the CSV/definition, right is field name as it WILL appear in Splunk query results

### The general naming convention, with few exceptions, is *type*_*field-name-as-seen-in-Splunk*_table.csv

### TO DO:
- Get all of the lists!

### Lookup Tables
- mitre_attack_v7_table.csv
	- [MITRE ATT&CK framework](https://attack.mitre.org/) v7, including sub-techniques
	- updated 2020-07-29
- network_http_status.csv
	- for HTTP codes, from [Splunk documentation](https://wiki.splunk.com/Http_status.csv)
	- useful for Zeek or any other log type where HTTP status codes are found
- sysmon_EventCode_table.csv
	- for [Sysmon event codes](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)
- windows_EventCode_table.csv
	- Windows 7/Vista/8/10, Windows Server 2008/2012R2/2016/2019
	- sources: [Ultimate Windows Security](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/), [Andrea Fortuna](https://www.andreafortuna.org/2019/06/12/windows-security-event-logs-my-own-cheatsheet/)
- windows_EventCode_table_old-XP-2000-2003.csv
	- Windows 2000/XP and Windows Server 2003
	- sources: [Ultimate Windows Security](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/), [Andrea Fortuna](https://www.andreafortuna.org/2019/06/12/windows-security-event-logs-my-own-cheatsheet/)
- windows_Impersonation_Level_table.csv
	- for COM impersonation levels, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/com/impersonation-levels) documentation
- windows_Logon_Type_table.csv
	- collection of Windows logon types, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc787567(v=ws.10)) documentation
- windows_system_error_codes_table.csv
	- collection of Windows error codes, from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/debug/system-error-codes) documentation
- wlan_frame_types.csv
	- types (management, control, data, extension) and subtypes (probe request, response, etc)
	- source: [Wikipedia](https://en.wikipedia.org/wiki/802.11_Frame_Types)
	- note: if using Python and Scapy, use zfill if desired: ```type = str(bin(pkt.type)[2:].zfill(2))``` ```subType = str(bin(pkt.subtype)[2:].zfill(4))```
- wlan_frame_types.dictionary
	- a Python dictionary version of [wlan_frame_types.csv](https://github.com/bonifield/lookup_tables/blob/master/wlan_frame_types.csv)
- zeek_conn_state_table.csv
	- a for Zeek's [conn_state](https://docs.zeek.org/en/current/scripts/base/protocols/conn/main.zeek.html) field
	- optionally use ```typeName = types[type]["description"]``` ```subTypeName = types[type]["subtype"][subType]["description"]```
