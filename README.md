# splunk-lookup-tables
### various lookup tables for Splunk, or any other program that reads the CSV format (any spreadsheet program or basic text editor)

### here is a [link to making automatic lookups in Splunk](https://docs.splunk.com/Documentation/Splunk/7.3.1/Knowledge/DefineanautomaticlookupinSplunkWeb)

### the general naming convention, with few exceptions, is *field-name-as-seen-in-Splunk*_table.csv

- conn_state_table.csv
	- a for Zeek's [conn_state](https://docs.zeek.org/en/current/scripts/base/protocols/conn/main.zeek.html) field
- EventCode_table.csv
	- for [Sysmon event codes](https://docs.microsoft.com/en-us/sysinternals/downloads/sysmon)
- http_status.csv
	- for HTTP codes, from [Splunk documentation](https://wiki.splunk.com/Http_status.csv)
- Impersonation_Level_table.csv
	- for COM impersonation levels, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/com/impersonation-levels) documentation
- Logon_Type_table.csv
	- collection of Windows logon types, seen in Windows Security logs, from [Microsoft](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc787567(v=ws.10)) documentation
- windows_system_error_codes_table.csv
	- collection of Windows error codes from [Microsoft](https://docs.microsoft.com/en-us/windows/win32/debug/system-error-codes) documentation
