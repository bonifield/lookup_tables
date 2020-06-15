# splunk-lookup-tables

### A collection of various useful lookup tables for Splunk, or any other program that reads the CSV format (any spreadsheet program or basic text editor). Lookups provide an easy way to enrich your data by using a separate file to add context to your logs.

### Here is a [official Splunk documentaion](https://docs.splunk.com/Documentation/Splunk/7.3.1/Knowledge/DefineanautomaticlookupinSplunkWeb), this one from [Hurricane Labs](https://www.hurricanelabs.com/blog/splunk-enterprise-security-automatic-identity-lookup-tables-using-active-directory-ldap), or follow the steps below:
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
- list of things to do

### Lookup Tables
- network_http_status.csv
	- for HTTP codes, from [Splunk documentation](https://wiki.splunk.com/Http_status.csv)
	- useful for Zeek or any other log type where HTTP status codes are found
- sysmon_EventCode_table.csv
	- for [Sysmon event codes](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)
- windows_Impersonation_Level_table.csv
	- for COM impersonation levels, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/com/impersonation-levels) documentation
- windows_Logon_Type_table.csv
	- collection of Windows logon types, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc787567(v=ws.10)) documentation
- windows_system_error_codes_table.csv
	- collection of Windows error codes, from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/debug/system-error-codes) documentation
- zeek_conn_state_table.csv
	- a for Zeek's [conn_state](https://docs.zeek.org/en/current/scripts/base/protocols/conn/main.zeek.html) field
