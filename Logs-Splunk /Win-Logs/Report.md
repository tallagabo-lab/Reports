# Analysing Windows Logs(Syslog,WinEventLogs)-with Splunk SIEM.

## Overview
This report presents an investigation and analysis on Windows logs, using Splunk queries ,after finding a suspicious network connection using port 5678 on the WIN-105 host.

----
## Findings
after using this querie:**index=task4 destinationport: 5678 host="WIN-105"
| table _time ComputerName Image SourceIp SourcePort DestinationIp DestinationPort Protocol**
we find that the destination ip :**10.10.114.80**
as also that from the image we can assume that SharePoint.exe was executed
-we see sheduld task **schtasks  /create /sc once /st 15:30 /tn "Office365 Install" /tr "C:\Windows\Temp\SharePoInt.exe"**
HASH:08/14/2025 11:10:22 AM
LogName=Microsoft-Windows-Sysmon/Operational
EventCode=7
EventType=4
ComputerName=WIN-105
User=NOT_TRANSLATED
Sid=S-1-5-18
SidType=0
SourceName=Microsoft-Windows-Sysmon
Type=Information
RecordNumber=7468
Keywords=None
TaskCategory=Image loaded (rule: ImageLoad)
OpCode=Info
Message=Image loaded:
RuleName: image_load
UtcTime: 2025-08-14 11:10:22.702
ProcessGuid: {c5d2b969-c41e-689d-dc02-000000002101}
ProcessId: 1460
Image: C:\Windows\Temp\SharePoInt.exe
ImageLoaded: C:\Windows\Temp\SharePoInt.exe
FileVersion: -
Description: -
Product: -
Company: -
OriginalFileName: -
Hashes: MD5=770D14FFA142F09730B415506249E7D1,SHA256=096A8CA80A730BD354334278700991EB762EBC8CB2E7D5CAED8702EC0EF2A912,IMPHASH=B4C6FFF030479AA3B12625BE67BF4914
Signed: false
Signature: -
SignatureStatus: Unavailable
User: WIN-105\Ben Foster	 	 	MD5=770D14FFA142F09730B415506249E7D1,SHA256=096A8CA80A730BD354334278700991EB762EBC8CB2E7D5CAED8702EC0EF2A912,IMPHASH=B4C6FFF030479AA3B12625BE67BF4914
08/14/2025 11:10:22 AM
LogName=Microsoft-Windows-Sysmon/Operational
EventCode=1
EventType=4
ComputerName=WIN-105
User=NOT_TRANSLATED
Sid=S-1-5-18
SidType=0
SourceName=Microsoft-Windows-Sysmon
Type=Information
RecordNumber=7467
Keywords=None
TaskCategory=Process Create (rule: ProcessCreate)
OpCode=Info
Message=Process Create:
RuleName: -
UtcTime: 2025-08-14 11:10:22.691
ProcessGuid: {c5d2b969-c41e-689d-dc02-000000002101}
ProcessId: 1460
Image: C:\Windows\Temp\SharePoInt.exe
FileVersion: -
Description: -
Product: -
Company: -
OriginalFileName: -
CommandLine: "C:\Windows\Temp\SharePoInt.exe" 
CurrentDirectory: C:\Windows\Temp\
User: WIN-105\Ben Foster
LogonGuid: {c5d2b969-c3df-689d-bef6-3e0000000000}
LogonId: 0x3EF6BE
TerminalSessionId: 5
IntegrityLevel: Medium
Hashes: MD5=770D14FFA142F09730B415506249E7D1,SHA256=096A8CA80A730BD354334278700991EB762EBC8CB2E7D5CAED8702EC0EF2A912,IMPHASH=B4C6FFF030479AA3B12625BE67BF4914
ParentProcessGuid: {c5d2b969-c3e1-689d-9302-000000002101}
ParentProcessId: 5240
ParentImage: C:\Windows\explorer.exe
ParentCommandLine: C:\Windows\Explorer.EXE
ParentUser: WIN-105\Ben Foster	"C:\Windows\Temp\SharePoInt.exe"	 	**MD5=770D14FFA142F09730B415506249E7D1**,SHA256=096A8CA80A730BD354334278700991EB762EBC8CB2E7D5CAED8702EC0EF2A912,IMPHASH=B4C6FFF030479AA3B12625BE67BF4914


