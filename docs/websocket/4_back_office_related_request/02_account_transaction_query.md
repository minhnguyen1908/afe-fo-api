# ACCOUNT_TRANSACTION_QUERY

## REQUEST

=== "User mode"
    ```json hl_lines="5"
    {
        // Required.
        "COMMAND": "ACCOUNT_TRANSACTION_QUERY_REQUEST",
        "LOGIN_ID": "GARY1",
        "USER_ID": "GARY1",
        "ACCOUNT_ID": "011C000018",
        "SESSION_KEY": "rdc8T8lcbD1kBOhjZDT3se1f",
        "CHANNEL": "WU",
        "LANG": "EN",
        "START_DATE": "20240101",
        "END_DATE": "20250112",
        // Optional.
        "TYPE": "",
        "REQ_ID": "TEST001"
    }
    ```

=== "Client mode"
    ```json hl_lines="5" 
    {
        // Required.
        "COMMAND": "ACCOUNT_TRANSACTION_QUERY_REQUEST",
        "LOGIN_ID": "GARY1",
        "CLIENT_ID": "GARY1",
        "ACCOUNT_ID": "011C000018",
        "SESSION_KEY": "rdc8T8lcbD1kBOhjZDT3se1f",
        "CHANNEL": "WU",
        "LANG": "EN",
        "START_DATE": "20240101",
        "END_DATE": "20250112",
        // Optional.
        "TYPE": "",
        "REQ_ID": "TEST001"
    }
    ```

## RESPONSE

=== "Success"
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
                "QUERYACCOUNTTRANSACTION": {
                    "map": {
                        "RETURNCODE": {
                            "map": {
                                "SUCCESS": {
                                    "map": {
                                        "ARGUMENTS": "",
                                        "TIME": {
                                            "map": {
                                                "TYPE": "TIMESTAMP",
                                                "content": "2025-03-25 11:43:54.490"
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                },
                "ID": 0,
                "RESULT": {
                    "map": {
                        "RECORD": {
                            "myArrayList": [
                                {
                                    "map": {
                                        "INSTRUMENTID": "",
                                        "REMARKEXLANGUAGE": "EN",
                                        "SUBTYPEID": "",
                                        "UpdateSettledBalanceFlag": "Y",
                                        "QUANTITY": {
                                            "map": {
                                                "TYPE": "DECIMAL"
                                            }
                                        },
                                        "INPUTDATE": {
                                            "map": {
                                                "TYPE": "DATE",
                                                "content": "2024-05-21"
                                            }
                                        },
                                        "UpdateLedgerBalanceFlag": "Y",
                                        "CHECKEDON": {
                                            "map": {
                                                "TYPE": "TIMESTAMP",
                                                "content": "2024-05-21 16:43:21.007"
                                            }
                                        },
                                        "MARKETID": "",
                                        "STATE": "A",
                                        "INSTRUMENTSETTLEDATE": {
                                            "map": {
                                                "TYPE": "DATE"
                                            }
                                        },
                                        "TRADEDATE": {
                                            "map": {
                                                "TYPE": "DATE",
                                                "content": "2024-05-21"
                                            }
                                        },
                                        "TRANSACTIONCODE": "OCW",
                                        "REGIONID": "VN",
                                        "LINKUPID": 267479,
                                        "UPDATEDON": {
                                            "map": {
                                                "TYPE": "TIMESTAMP",
                                                "content": "2024-05-21 16:43:13.740"
                                            }
                                        },
                                        "AMOUNT": {
                                            "map": {
                                                "TYPE": "DECIMAL",
                                                "content": -500000
                                            }
                                        },
                                        "CURRENCYID": "VND",
                                        "SEQUENCE": {
                                            "map": {
                                                "TYPE": "INTEGER",
                                                "content": 0
                                            }
                                        },
                                        "SETTLECASHMETHOD": "A",
                                        "ACCOUNTID": "011C000018",
                                        "UPDATEDBY": "SUPPORT",
                                        "TYPE": "CPFCW",
                                        "REMARK": "~00430048005500591ec2004e0020004b0048004f1ea2004e0020005400521ef0004300200054005500591ebe004e0020005200410020004e0047004f00c00049",
                                        "SUBTYPE": "",
                                        "CASHSETTLEDATE": {
                                            "map": {
                                                "TYPE": "DATE",
                                                "content": "2024-05-21"
                                            }
                                        },
                                        "TRANSACTIONID": 8479958,
                                        "INTERFACETYPEID": "",
                                        "LINKUPTYPE": "CPC",
                                        "TYPEID": "",
                                        "PRINTDATE": {
                                            "map": {
                                                "TYPE": "DATE",
                                                "content": "2024-05-21"
                                            }
                                        },
                                        "SETTLEINSTRUMENTMETHOD": "",
                                        "QUANTITYDECIMALPLACES": {
                                            "map": {
                                                "TYPE": "INTEGER",
                                                "content": 0
                                            }
                                        },
                                        "REMARKLANGUAGE": "VN",
                                        "REMARKEX": "Online Transfer",
                                        "CHECKEDBY": "SUPPORT"
                                    }
                                }
                            ]
                        }
                    }
                }
            }
        },
        "Msg_ID": "ACCOUNT_TRANSACTION_QUERY_RESPONSE"
    }
    ```

=== "Failure" 
    ```json
    {
        "STATUS": "FAIL",
        "ERROR_MESSAGE": "Invalid parameters",
        "ERROR_CODE": "CMM500",
        "RESULT": {},
        "Msg_ID": "ACCOUNT_TRANSACTION_QUERY_RESPONSE"
    }
    ```
