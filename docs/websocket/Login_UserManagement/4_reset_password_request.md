# RESET_PASSWORD_REQUEST

```json title="Request message"
{
  "Command": "RESET_PASSWORD_REQUEST",
  "LOGIN_ID": "henrywB10",
  "CLIENT_ID": "henrywB10",
  "REQ_ID": "AT001",
  "Channel": "WS",
  "Lang": "en",
  "EMAIL": "henry.wong@afe-solutions.com",
  "HKID": "G987978(0)"
}
```

| Field     | Type   | Format in DB       | Req. | Description                                         |
| :-------- | :----- | :----------------- | :--- | :-------------------------------------------------- |
| Command   | String |                    | Yes  | "RESET_PASSWORD_REQUEST"                            |
| LOGIN_ID  | String | VARCHAR2(16 BYTE)  | Yes  | For User Mode: Use User Login ID<br>For Client Mode: Use Client Login ID |
| CLIENT_ID | String | VARCHAR2(16 BYTE)  | Yes  |                                                     |
| REQ_ID    | String |                    | No   | To indicate each Request and Response               |
| Channel   | String | VARCHAR2(4 BYTE)   | Yes  | "WS" - WebSocket H5<br>"WA" - WebSocket API<br>"WU" - WebSocket User Mode |
| Lang      | String | VARCHAR2(2BYTE)    | Yes  | "EN" - English<br>"CN" - Simplified Chinese<br>"TW" - Traditional Chinese |
| Email     | String | VARCHAR2(60 BYTE)  | Yes  |                                                     |
| HKID      | String | VARCHAR2(20 BYTE)  | Yes  |                                                     |


| Field | Type | Format in DB | Description |
|---|---|---|---|
| LOGIN_UID | String | VARCHAR2(16 BYTE) | Login ID for the login session |
| CHANNEL | String | VARCHAR2(4 BYTE) | "WS" - WebSocket |
| SESSION_KEY | String | VARCHAR2(32 BYTE) | Session Key |
| OLD_PASSWORD | String | VARCHAR2(4 BYTE) | |
| NEW_PASSWORD | String | | |
| RECONFIRM_PASSWORD | String | | |
| REQ_ID | String | | To indicate each Request and Response |


ÒWSÓ - WebSocket H5
