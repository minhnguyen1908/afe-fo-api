# LOGIN_REQUEST

After user/client logon success, user/client will receive following different response:

|Response after logon|User Mode|Client Mode|
|----|----|----|
|Login Response|YES|YES|
|Holding Response (Streaming)|Empty Response|YES|
|Order Response (Streaming)|YES|YES|
|Trade Response (Streaming)|YES|YES|

Holding, Order and Trade Response can refer to [7 STREAMING RESPONSE.]()

## Command: LOGIN_REQUEST

```json title="Request message."
{
    "Command": "LOGIN_REQUEST",
    "LOGIN_ID": "ws001",
    "PASSWORD": "1234",
    "CHANNEL": "WU",
    "LANG": "EN",
    "OTP_CODE": "",
    "FSEC": "ODU3N2QzZDgtNzQzNS00Mzc5",
    "MACHINE_MAC_ADDRESS": "02-00-4C-4F-24-50",
    "CLIENT_IP": "192.168.240.3",
}
```
### Field(s) explanation:

|Field|Type|Format in DB|Req.|Description
|----|----|----|----|----|
|Command|String||Yes|"LOGIN_REQUEST"|
|LOGIN_ID|String|VARCHAR2(16 BYTE)|Yes|For User Mode: User Login ID<br>For Client Mode: Client Login ID|
|PASSWORD|String|VARCHAR2(32 BYTE)|Yes|Password of Login|
|CHANNEL|String|VARCHAR2(4 BYTE)|Yes|For User Mode: 'WU'<br>For Client Mode: 'WS'|
|LANG|String|VARCHAR2(2 BYTE)|Yes|'EN' - English<br>'VN' - Vietnamese|
|OTP_CODE|String|VARCHAR2(32 BYTE)|No|One Time Password Code|
|MACHINE_MAC_ADDRESS|String|VARCHAR2(20 BYTE)|No|MAC address<br>exp: 02-00-4C-4F-4A-50|
|CLIENT_IP|String|VARCHAR2(20 BYTE)|No|Remote IP adressof Login<br>xxx.xxx.xxx.xxx.|

## Login success:

```json title="Login success response."
{
    "LOGIN_ID": "60020056",
    "CLIENT_ID": "60020056",
    "CHANNEL": "WS",
    "SESSION_KEY": "NjNjMzc3OWEtZTBmMi00ZmE5",
    "STATUS": "OK",
    "RESULT": {
        "LAST_LOGIN_DATETIME": "2024-04-16 15:08:44",
        "PASSWORD_EXPIRY_DATE": "",
        "PASSWORD_CHANGE_DATETIME": "2024-04-16 15:05:18",
        "LAST_LOGIN_FAIL_DATETIME": "2024-04-16 15:04:09",
        "LOGIN_STATUS": "KO",
        "INFO_PACKAGE_ID": "",
        "FSEC": "NjNjMzc3OWEtZTBmMi00ZmE5",
        "DEFAULT_ORDER_TYPE": "04",
        "REQUIRE_VNIDR_CONSENT_FLG": "",
        "FORCE_CHG_PWD": "F",
        "SITE_ID": "141",
        "INFOBASE_PACKAGE_ID": "",
        "INFOBASE_PARAM": "",
        "SITE_NAME": "G2testing",
        "LOGIN_RECORD": {
            "LAST_LOGIN_FAIL_DATETIME": "2024-04-16 15:04:09",
            "LAST_LOGIN_FAIL_CHANNEL": "WS",
            "LAST_LOGIN_DATETIME": "2024-04-16 15:08:44",
            "LAST_LOGIN_CHANNEL": "WS",
            "LOGIN_STATUS": "KO"
        }
    },
    "Msg_ID": "LOGIN_RESPONSE"
}
```

## Login failer (wrong password):

```json
{
    "STATUS": "FAIL",
    "ERROR_MESSAGE": "Wrong password",
    "ERROR_CODE": "SEW002",
    "RESULT": {},
    "Msg_ID": "ERROR"
}
```