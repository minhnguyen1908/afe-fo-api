# CHANGE_USER_LOGIN_PASSWORD_REQUEST

```json title="Request body."
{
    "Command": "CHANGE_PASSWORD_REQUEST",
    "LOGIN_ID": "ws001",
    "SESSION_KEY": "aMNj1mmeoazk3stZFYQ!U3pI",
    "Channel": "WU",
    "OLD_PASSWORD": "1234",
    "NEW_PASSWORD": "Ab123457",
    "RECONFIRM_PASSWORD": "Ab123457",
    "Lang": "EN" ,
    "REQ_ID": "CHANGE_PWD",
}
```

| Field | Type | Format in DB | Description |
|---|---|---|---|
| LOGIN_UID | String | VARCHAR2(16 BYTE) | Login ID for the login session |
| CHANNEL | String | VARCHAR2(4 BYTE) | "WS" - WebSocket |
| SESSION_KEY | String | VARCHAR2(32 BYTE) | Session Key |
| OLD_PASSWORD | String | VARCHAR2(4 BYTE) | |
| NEW_PASSWORD | String | | |
| RECONFIRM_PASSWORD | String | | |
| REQ_ID | String | | To indicate each Request and Response |
