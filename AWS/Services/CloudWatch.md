## Amazon Connect
```
fields @timestamp, @message
| sort @timestamp desc
| limit 25
| filter ContactFlowModuleType = 'Transfer'
| filter Results = 'false'
| display Results, ContactId, @timestamp
```
```
fields @timestamp, @message
| sort @timestamp desc
| limit 25
| filter ContactId = '44a26767-698f-464c-a063-886766dcf438'
| display Results, ContactId, @timestamp, ContactFlowModuleType
```
```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
| filter @message like /ERROR/
| stats count(*) by bin(15m)
```