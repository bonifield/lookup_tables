# splunk-lookup-tables
### various lookup tables for Splunk, or any other program that reads the CSV format (any spreadsheet program or basic text editor)

- conn_state_table.csv
	- a [lookup table](https://docs.splunk.com/Documentation/Splunk/7.3.1/Knowledge/DefineanautomaticlookupinSplunkWeb) for Zeek's conn_state field
- EventCode_table.csv
	- a lookup table for Sysmon event codes
- http_status.csv
	- lookup for HTTP codes
	- from [Splunk documentation](https://wiki.splunk.com/Http_status.csv)
- Impersonation_Level_table.csv
	- for COM impersonation levels, seen in Windows Security logs
- Logon_Type_table.csv
	- collection of Windows logon types, seen in Windows Security logs, [Microsoft](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc787567(v=ws.10)) documentation
- windows_system_error_codes_table.csv
	- collection of Windows error codes from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/debug/system-error-codes) documentation
