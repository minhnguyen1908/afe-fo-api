# LOGOUT_REQUEST

## Command: LOGOUT_REQUEST

```json title="Request message."
{
    "COMMAND": "LOGOUT",
    "LOGIN_ID": "{{login_id}}",
    "CHANNEL": "{{channel}}",
    "LANG": "{{lang}}",
    "SESSION_KEY": "{{skey}}",
}
```

|Field|Type|Format in DB|Req.|Description
|----|----|----|----|----|
|Command|String||Yes|"LOGOUT_REQUEST"|
|LOGIN_ID|String|VARCHAR2(16 BYTE)|Yes|For User Mode: User Login ID<br>For Client Mode: Client Login ID|
|CHANNEL|String|VARCHAR2(4 BYTE)|Yes|For User Mode: 'WU'<br>For Client Mode: 'WS'|
|LANG|String|VARCHAR2(2 BYTE)|Yes|'EN' - English<br>'VN' - Vietnamese|
|SESSION_KEY|String|VARCHAR2(32 BYTE)|Yes|Session key|

## Response:

### Logout success:

```json title="Response body:"
{
    "LOGIN_ID": "ws001",
    "CLIENT_ID": "",
    "CHANNEL": "WU",
    "SESSION_KEY": "",
    "STATUS": "OK",
    "Msg_ID": "LOGOUT_RESPONSE"
}
```