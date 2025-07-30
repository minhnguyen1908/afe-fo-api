# STOCK_INFORMATION_REQUEST

## Request 

### Body

```json
{
    "Command": "STOCKINFO_QUERY_REQUEST",
    "LOGIN_ID": "{{login_id}}",
    "USER_ID": "{{login_id}}",
    "SESSION_KEY": "{{skey}}",
    "REQ_ID": "GMAN001",
    "Channel": "{{channel}}",
    "Lang": "EN",
    "ACCOUNT_ID": "011C000020",
    "INSTRUMENT_CODE": "HCM"
}
```

### Parameters

| Field | Type | Format in DB | Req. | Description |
|---|---|---|---|---|
| Command | String | | Yes | "STOCKINFO_QUERY_REQUEST" |
| LOGIN_ID | String | VARCHAR2(16 BYTE) | Yes | For User Mode: Use User Login ID<br>For Client Mode: Use Client Login ID |
| USER_ID | String | VARCHAR2(16 BYTE) | Yes | |
| SESSION_KEY | String | VARCHAR2(32 BYTE) | Yes | |
| REQ_ID | String | | No | To indicate each Request and Response |
| INSTRUMENT_CODE | String | VARCHAR2(20 BYTE) | Yes | |
| Channel | String | VARCHAR2(4 BYTE) | Yes | "WS" - WebSocket H5<br>"WA" - WebSocket API<br>"WU" - WebSocket User Mode |
| Lang | String | VARCHAR2(2BYTE) | Yes | EN - English (Default)<br>VN - Vietnamse |

## Response

### Success

#### Body

```json
{
    "LOGIN_ID": "GARY1",
    "CLIENT_ID": "011C000018",
    "CHANNEL": "WU",
    "SESSION_KEY": "aMNj1mmeoazk3stZFYQ!U3pI",
    "REQ_ID": "GMAN001",
    "INSTRUMENT_CODE": "HCM",
    "STATUS": "OK",
    "RESULT": {
        "STOCK_INFO": [
            {
                "STOCK_CODE": "HCM",
                "STOCK_NAME": "CTY CPCK TP HO CHI MINH",
                "LOCAL_NAME": "CTY CPCK TP HO CHI MINH",
                "TYPE": "EQ",
                "EXCHANGE": "HOSE",
                "LOT_SIZE": "100",
                "PREVIOUS_CLOSE": "40700.0",
                "FLOOR": "37100.0",
                "CEILING": "42600.0",
                "STATUS": "OK",
                "Msg_ID": "STOCK_INFO_RECORD"
            }
        ]
    },
    "Msg_ID": "STOCKINFO_QUERY_RESPONSE"
}
```

#### Parameters

| Field | Type | Format in DB | Description |
|---|---|---|---|
| LOGIN_ID | String | VARCHAR2(16 BYTE) | Login ID for the login session |
| CLIENT_ID | String | VARCHAR2(16 BYTE) | |
| CHANNEL | String | VARCHAR2(4 BYTE) | "WS" - WebSocket H5<br>"WA" - WebSocket API<br>"WU" - WebSocket User Mode |
| INSTRUMENT_CODE | String | VARCHAR2(20 BYTE) | |
| SESSION_KEY | String | VARCHAR2(32 BYTE) | |
| REQ_ID | String | | To indicate each Request and Response |
| STATUS | String | VARCHAR2(4 BYTE) | |
| RESULT | Object | | |
| STOCK_INFO | Object | | |
| STOCK_CODE | String | VARCHAR2(20 BYTE) | Stock Code |
| STOCK_NAME | String | VARCHAR2(250 BYTE) | Stock Name |
| STOCK_LOCAL_NAME | String | VARCHAR2(250 BYTE) | Stock Local Name |
| TYPE | String | VARCHAR2(4 BYTE) | Stock Type |
| EXCHANGE | String | VARCHAR2(8 BYTE) | Exchange Code |
| LOT_SIZE | Number | NUMBER | Stock Lot Size |
| PREVIOUS_CLOSE | Number | NUMBER | Previous Closing Price |
| FLOOR | Number | NUMBER | Stock Floor Price |
| CEILING | Number | NUMBER | Stock Ceiling Price |
| PT_FLOOR | Number | NUMBER | Put Through Floor |
| PT_CEILING | Number | NUMBER | Put Through Ceiling |
| PO_FLOOR | Number | NUMBER | Post Session Floor |
| PO_CEILING | Number | NUMBER | Post Session Ceiling |
| BI_FLOOR | Number | NUMBER | Buyin Floor |
| BI_CEILING | Number | NUMBER | Buyin Ceiling |

### Fail

#### Body

```json
{
    "STATUS": "FAIL",
    "ERROR_MESSAGE": "Invalid Security Code",
    "ERROR_CODE": "SH8496",
    "RESULT": {},
    "Msg_ID": "STOCKINFO_QUERY_RESPONSE"
}
```

#### Parameters

| Field | Type | Format in DB | Description |
|---|---|---|---|
| STATUS | String | | |
| ERROR_MESSAGE | String | VARCHAR2(120) | |
| ERROR_CODE | String | VARCHAR2(6) | |
| Msg_ID | String | | "ERROR" |
