# CASH_MOVEMENT_QUERY

## REQUEST

### BODY

```json
{
    // Required
    "COMMAND": "CASH_MOVEMENT_QUERY_REQUEST",
    "LOGIN_ID": "GARY1",
    "USER_ID": "GARY1",
    //"CLIENT_ID": "GARY1",
    "ACCOUNT_ID": "011C000018",
    "SESSION_KEY": "rdc8T8lcbD1kBOhjZDT3se1f",
    "CHANNEL": "WU",
    "START_DATE": "20240101", //(1)!
    "END_DATE": "20250311",
    "RECORD_STATE": "PI,A,C",
    "LANG": "EN",
    // Optionale
    "REQ_ID": "TEST001"
}
```

1. Format: `YYYYMMDD`

## RESPONSE

### SUCCESS

#### BODY

```json
{
    "LOGIN_ID": "GARY1",
    "CLIENT_ID": "011C000018",
    "CHANNEL": "WU",
    "SESSION_KEY": "rdc8T8lcbD1kBOhjZDT3se1f",
    "REQ_ID": "TEST001",
    "STATUS": "OK",
    "RESULT": {
        "map": {
            "QUERY": {
                "map": {
                    "MOREFLAG": {
                        "map": {
                            "TYPE": "BOOLEAN",
                            "content": "N"
                        }
                    },
                    "RETURNCODE": {
                        "map": {
                            "SUCCESS": {
                                "map": {
                                    "ARGUMENTS": "",
                                    "TIME": {
                                        "map": {
                                            "TYPE": "TIMESTAMP",
                                            "content": "2025-03-25 11:25:10.466"
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            },
            "ID": 123,
            "RESULT": {
                "map": {
                    "TCAccountCashMovement": {
                        "map": {
                            "RECORD": {
                                "myArrayList": [
                                    {
                                        "map": {
                                            "TransactionReference": 642948558,
                                            "FeeType": "O",
                                            "CheckedBy": "",
                                            "NeedHoldFlag": "N",
                                            "BatchID": "",
                                            "SettleInterfaceID": {
                                                "map": {
                                                    "TYPE": "INTEGER",
                                                    "content": 0
                                                }
                                            },
                                            "ReleasedAmount": {
                                                "map": {
                                                    "TYPE": "DECIMAL"
                                                }
                                            },
                                            "ToBankAccountName": "CTY CO PHAN CHUNG KHOAN SSI CN HN",
                                            "TransferToInterfaceTypeID": "",
                                            "MovementID": 267495,
                                            "MovementType": "W",
                                            "Remark": "Client 0103686 registers to buy IPO of CW VNMCW",
                                            "UpdatedBy": "G3B",
                                            "ToBankAccountNumber": 22210003996789,
                                            "AutoReleaseDate": {
                                                "map": {
                                                    "TYPE": "DATE"
                                                }
                                            },
                                            "TransferToAccountID": "",
                                            "TransactionCode": "OCW",
                                            "ToBankBranch": "",
                                            "SettleCashMethod": "A",
                                            "ValueDate": {
                                                "map": {
                                                    "TYPE": "DATE",
                                                    "content": "2024-05-22"
                                                }
                                            },
                                            "UpdatedOn": {
                                                "map": {
                                                    "TYPE": "TIMESTAMP",
                                                    "content": "2024-05-23 09:13:36.687"
                                                }
                                            },
                                            "IsCashFlag": "N",
                                            "CreatedOn": {
                                                "map": {
                                                    "TYPE": "TIMESTAMP",
                                                    "content": "2024-05-23 09:13:36.687"
                                                }
                                            },
                                            "NotificationFlag": "Y",
                                            "SettleStatus": "U",
                                            "AutoReleaseAmount": {
                                                "map": {
                                                    "TYPE": "DECIMAL"
                                                }
                                            },
                                            "AccountID": "011C000018",
                                            "CreatedBy": "G3B",
                                            "HoldType": "",
                                            "Amount": {
                                                "map": {
                                                    "TYPE": "DECIMAL",
                                                    "content": 1234
                                                }
                                            },
                                            "DrawAllWithAccruedFeeFlag": "N",
                                            "CurrencyID": "VND",
                                            "ToBankName": "",
                                            "ProcessState": "I",
                                            "RemarkEx": "Client 0103686 registers to buy IPO of CW VNMCW",
                                            "TransferToInterfaceID": {
                                                "map": {
                                                    "TYPE": "INTEGER",
                                                    "content": 0
                                                }
                                            },
                                            "SettleInterfaceTypeID": "",
                                            "State": "PI",
                                            "ChequeNumber": "",
                                            "ReleasedDate": {
                                                "map": {
                                                    "TYPE": "DATE"
                                                }
                                            },
                                            "CheckedOn": {
                                                "map": {
                                                    "TYPE": "TIMESTAMP"
                                                }
                                            }
                                        }
                                    }
                                ]
                            }
                        }
                    }
                }
            }
        }
    },
    "Msg_ID": "CASH_MOVEMENT_QUERY_RESPONSE"
}
```

### FAILURE

#### BODY

```json
{
    "STATUS": "FAIL",
    "ERROR_MESSAGE": "Invalid parameters",
    "ERROR_CODE": "CMM500",
    "RESULT": {},
    "Msg_ID": "CASH_MOVEMENT_QUERY_RESPONSE"
}
```
