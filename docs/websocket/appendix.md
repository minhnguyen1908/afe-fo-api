# APPENDIX

| Field | Type | Format in DB | Description |
|---|---|---|---|
| Command | String | | "CASH_MOVEMENT_QUERY_REQUEST" |
| LOGIN_ID | String | VARCHAR2(16 BYTE) | For User Mode: Use User Login ID<br>For Client Mode: Use Client Login ID |
| USER_ID<br>*(CLIENT_ID)* | String | VARCHAR2(16 BYTE) | USER_ID: For user mode.<br>*(CLIENT_ID: For client mode.)* |
| ACCOUNT_ID | String | VARCHAR2(16 BYTE) | |
| SESSION_KEY | String | VARCHAR2(32 BYTE) | |
| REQ_ID | String | | To indicate each Request and Response |
| CHANNEL | String | VARCHAR2(4 BYTE) | "WS" - WebSocket H5<br>"WA" - WebSocket API<br>"WU" - WebSocket User Mode |
| LANG | String | VARCHAR2(2 BYTE) | "EN" - English<br>"VN" - Vietnamese |
| RECORD_STATE | String | | |
| STATUS | String | | "OK" |
| RESULT | Object | | Result from G3B (The result body is depends on G3B response so it may different from sample response body) |
| Msg_ID | String | | "CASH_MOVEMENT_QUERY_RESPONSE" |
| TYPE | String | | linkup type (optional, refer to REMARK for list of linkup type) |
| START_DATE | String | | Start date for transaction query<br>Format: **YYYYMMDD** |
| END_DATE | String | | End date for transaction query<br>Format: **YYYYMMDD** |
