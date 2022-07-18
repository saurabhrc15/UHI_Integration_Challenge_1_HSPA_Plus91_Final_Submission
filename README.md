# Physical Consultation Booking Document

# Plus91 HSPA App Microservice [Folder - medixcel-uhi]

Objective of this microservice is to handle the requests coming from gateway & EUAs & forwarding it to
the correct hospital which is using plus91 EMR software.

Workflow:

1: The microservice manages list of all the hospitals which used plus91 EMR software
2: For search request
	Microservice sends the search request to all registered hospitals with plus91 & sends search response back to the EUAs

3: The booking workflow requests:
	Microservice forwards the the requests to the correct hospital & sends the response back to the requesting EUA.

# Plus91 HSPA App Side Code [Folder - Medixcel-HSPA]

Objective of this repository is to process all the requests coming from above microservice & forward the response 
back to microservice. Then the microservice returns the response to the corresponsing EUA.

# Our HSPA Credentials
```json
{
	"provider_id" : "plus91-HSPA",
	"provider_url" : "https://plus91hq.ddns.net/medixcel_uhi"
}
```

# Search Request
```json
{
    "message": {
        "intent": {
            "fulfillment": {
                "agent": {
                    "name": "vijay"
                }
            }
        },
        "order": null,
        "catalog": null,
        "order_id": null
    },
    "context": {
        "domain": "Health",
        "country": "IND",
        "city": "Pune",
        "action": "search",
        "timestamp": "2022-07-18T05:26:16.689Z",
        "core_version": "0.7.1",
        "consumer_id": "plus91-EUA",
        "consumer_uri": "https://c32f-2409-4042-4b00-ade3-b757-3bf1-ff61-d120.in.ngrok.io/api/v1",
        "transaction_id": "b2e9f303-cb4a-47de-8a8f-5ff9fb86f591",
        "message_id": "4fb2cefe-2d24-4b00-aa1c-f35b0760a7a5"
    }
}
```

# On Search Request
```json
{
    "context": {
        "domain": "Health",
        "country": "IND",
        "city": "PUNE",
        "action": "on_search",
        "core_version": "NA",
        "message_id": "1e619ca2-ab1b-4385-8d31-beac0b3ffd45",
        "transaction_id": "74ac1268-ca9c-457e-8b4d-b147b6a229f0",
        "timestamp": "2022-07-17T07:44:36.000000"
    },
    "message": {
        "catalog": {
            "descriptor": {
                "name": "Lohegaon - Clinic"
            },
            "items": [
                {
                    "id": "1",
                    "descriptor": {
                        "name": "Cardiology"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "12"
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "2",
                    "descriptor": {
                        "name": "Cardiology Follow Up"
                    },
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "3",
                    "descriptor": {
                        "name": "Chest Physician"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "150"
                    },
                    "fulfillment_id": "6"
                }
            ],
            "fulfillments": [
                {
                    "id": "6",
                    "type": "Teleconsultation",
                    "agent": {
                        "id": "6",
                        "name": "Vijay Dandekar",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": "12",
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:50+00:00"
                        }
                    }
                },
                {
                    "id": "6",
                    "type": "Teleconsultation",
                    "agent": {
                        "id": "6",
                        "name": "Vijay Dandekar",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": null,
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:50+00:00"
                        }
                    }
                },
                {
                    "id": "6",
                    "type": "Teleconsultation",
                    "agent": {
                        "id": "6",
                        "name": "Vijay Dandekar",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": "150",
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:50+00:00"
                        }
                    }
                }
            ]
        }
    }
}
```

# Init Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "PUNE",
        "action": "init",
        "timestamp": "2022-07-17T07:44:48.678Z",
        "core_version": "0.7.1",
        "consumer_id": "plus91-EUA",
        "consumer_uri": "https://7aa3-112-133-244-202.in.ngrok.io/api/v1",
        "transaction_id": "74ac1268-ca9c-457e-8b4d-b147b6a229f0",
        "message_id": "c50f4511-ef2f-4f75-8b49-720878e883ee"
    },
    "message": {
        "order": {
            "id": "5f32c7c8-1465-43b8-a3ec-e0cf3c6bba90",
            "item": {
                "id": "3",
                "descriptor": {
                    "name": "Chest Physician"
                },
                "price": {
                    "currency": "INR",
                    "value": "150"
                },
                "fulfillment_id": "6"
            },
            "billing": {
                "name": "Shubham Bhadale",
                "address": {
                    "door": "406",
                    "name": "Plus91 Techbologies Pvt Ltd",
                    "locality": "Vimannagar",
                    "city": "Pune",
                    "state": "Maharashtra",
                    "country": "India",
                    "area_code": "411013"
                },
                "email": "shubham.bhadale@plus91.in",
                "phone": "11111111111"
            },
            "fulfillment": {
                "id": "6",
                "type": "Teleconsultation",
                "agent": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": "M",
                    "tags": {
                        "@abdm/gov/in/first_consultation": "12",
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "Consultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-07-17T04:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-07-17T04:15"
                    }
                }
            },
            "customer": {
                "id": "61-7719-8914-2522",
                "cred": "shubham.bhadale@abdm"
            }
        }
    }
}
```

# On Init Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "PUNE",
        "action": "on_init",
        "timestamp": "2022-07-17T07:44:48.678Z",
        "core_version": "0.7.1",
        "consumer_id": "plus91-EUA",
        "consumer_uri": "https://7aa3-112-133-244-202.in.ngrok.io/api/v1",
        "transaction_id": "74ac1268-ca9c-457e-8b4d-b147b6a229f0",
        "message_id": "c50f4511-ef2f-4f75-8b49-720878e883ee",
        "provider_id": "plus91-HSPA",
        "provider_uri": "https://plus91hq.ddns.net/medixcel_uhi"
    },
    "message": {
        "order": {
            "id": "2228f3c6-5ea2-4c9a-a05c-629ec30d3e9d",
            "state": "PROVISIONALLY_BOOKED",
            "provider": {
                "id": 1,
                "descriptor": {
                    "name": "Lohegaon - Clinic"
                }
            },
            "item": {
                "id": "3",
                "descriptor": {
                    "name": "Chest Physician"
                },
                "price": {
                    "currency": "INR",
                    "value": "150"
                },
                "fulfillment_id": "6"
            },
            "billing": {
                "name": "Shubham Bhadale",
                "address": {
                    "door": "406",
                    "name": "Plus91 Techbologies Pvt Ltd",
                    "locality": "Vimannagar",
                    "city": "Pune",
                    "state": "Maharashtra",
                    "country": "India",
                    "area_code": "411013"
                },
                "email": "shubham.bhadale@plus91.in",
                "phone": "11111111111"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": "Male",
                    "tags": {
                        "@abdm/gov/in/first_consultation": "150",
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "PhysicalConsultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-07-17T04:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-07-17T04:15"
                    }
                }
            },
            "quote": {
                "quote": {
                    "price": {
                        "currency": "INR",
                        "value": "150"
                    },
                    "breakup": [
                        {
                            "title": "Consultation",
                            "price": {
                                "currency": "INR",
                                "value": "150"
                            }
                        }
                    ]
                }
            },
            "payment": {
                "uri": "payto://ban/98273982749428?amount=INR:110&ifsc=SBIN0000575&message=hello",
                "type": "ON-ORDER",
                "status": "PENDING",
                "tl_method": null,
                "params": null
            }
        }
    }
}
```

# Confirm Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "PUNE",
        "action": "confirm",
        "timestamp": "2022-07-17T07:45:16.339Z",
        "core_version": "0.7.1",
        "consumer_id": "plus91-EUA",
        "consumer_uri": "https://7aa3-112-133-244-202.in.ngrok.io/api/v1",
        "transaction_id": "74ac1268-ca9c-457e-8b4d-b147b6a229f0",
        "message_id": "e1d22217-0878-4fbc-ac6b-e171a9042747"
    },
    "message": {
        "order": {
            "id": "2228f3c6-5ea2-4c9a-a05c-629ec30d3e9d",
            "item": {
                "id": "3",
                "descriptor": {
                    "name": "Chest Physician"
                },
                "price": {
                    "currency": "INR",
                    "value": "150"
                },
                "fulfillment_id": "6"
            },
            "billing": {
                "name": "Shubham Bhadale",
                "address": {
                    "door": "406",
                    "name": "Plus91 Techbologies Pvt Ltd",
                    "locality": "Vimannagar",
                    "city": "Pune",
                    "state": "Maharashtra",
                    "country": "India",
                    "area_code": "411013"
                },
                "email": "shubham.bhadale@plus91.in",
                "phone": "11111111111"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": "Male",
                    "tags": {
                        "@abdm/gov/in/first_consultation": "150",
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "PhysicalConsultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-07-17T04:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-07-17T04:15"
                    }
                }
            },
            "quote": {
                "quote": {
                    "price": {
                        "currency": "INR",
                        "value": "150"
                    },
                    "breakup": [
                        {
                            "title": "Consultation",
                            "price": {
                                "currency": "INR",
                                "value": "150"
                            }
                        }
                    ]
                }
            },
            "payment": {
                "uri": "payto://ban/98273982749428?amount=INR:110&ifsc=SBIN0000575&message=hello",
                "params": null,
                "type": "ON-ORDER",
                "status": "PAID",
                "tl_method": null
            }
        }
    }
}
```

# On Confirm Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "PUNE",
        "action": "confirm",
        "timestamp": "2022-07-17T07:45:16.339Z",
        "core_version": "0.7.1",
        "consumer_id": "plus91-EUA",
        "consumer_uri": "https://7aa3-112-133-244-202.in.ngrok.io/api/v1",
        "transaction_id": "74ac1268-ca9c-457e-8b4d-b147b6a229f0",
        "message_id": "e1d22217-0878-4fbc-ac6b-e171a9042747"
    },
    "message": {
        "order": {
            "id": "2228f3c6-5ea2-4c9a-a05c-629ec30d3e9d",
            "item": {
                "id": "3",
                "descriptor": {
                    "name": "Chest Physician"
                },
                "price": {
                    "currency": "INR",
                    "value": "150"
                },
                "fulfillment_id": "6"
            },
            "billing": {
                "name": "Shubham Bhadale",
                "address": {
                    "door": "406",
                    "name": "Plus91 Techbologies Pvt Ltd",
                    "locality": "Vimannagar",
                    "city": "Pune",
                    "state": "Maharashtra",
                    "country": "India",
                    "area_code": "411013"
                },
                "email": "shubham.bhadale@plus91.in",
                "phone": "11111111111"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": "Male",
                    "tags": {
                        "@abdm/gov/in/first_consultation": "150",
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "PhysicalConsultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-07-17T04:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-07-17T04:15"
                    }
                }
            },
            "quote": {
                "quote": {
                    "price": {
                        "currency": "INR",
                        "value": "150"
                    },
                    "breakup": [
                        {
                            "title": "Consultation",
                            "price": {
                                "currency": "INR",
                                "value": "150"
                            }
                        }
                    ]
                }
            },
            "payment": {
                "uri": "payto://ban/98273982749428?amount=INR:110&ifsc=SBIN0000575&message=hello",
                "params": null,
                "type": "ON-ORDER",
                "status": "PAID",
                "tl_method": null
            }
        }
    }
}
```

### API Logs for testing with EUA Postman Collection

# Search Request
```json
{
    "context": {
        "domain": "Health",
        "country": "IND",
        "city": "Pune",
        "action": "search",
        "timestamp": "2022-07-18T10:43:48.705082Z",
        "core_version": "0.7.1",
        "consumer_id": "eua-nha",
        "consumer_uri": "http://100.96.9.173:8080/api/v1/euaService",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2"
    },
    "message": {
        "intent": {
            "fulfillment": {
                "agent": {
                    "name": "vijay"
                },
                "type": "PhysicalConsultation"
            }
        }
    }
}
```

# On Search Request
```json
{
    "context": {
        "domain": "Health",
        "country": "IND",
        "city": "PUNE",
        "action": "on_search",
        "core_version": "NA",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "timestamp": "2022-07-18T08:00:19.000000",
        "provider_id": "plus91-HSPA",
        "provider_uri": "https://plus91hq.ddns.net/medixcel_uhi"
    },
    "message": {
        "catalog": {
            "descriptor": {
                "name": "Lohegaon - Clinic"
            },
            "items": [
                {
                    "id": "1",
                    "descriptor": {
                        "name": "Cardiology"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "12"
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "2",
                    "descriptor": {
                        "name": "Cardiology Follow Up"
                    },
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "3",
                    "descriptor": {
                        "name": "Chest Physician"
                    },
                    "price": {
                        "currency": "INR",
                        "value": "150"
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "4",
                    "descriptor": {
                        "name": "Chest Physician Follow Up"
                    },
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "6",
                    "descriptor": {
                        "name": "Diet Follow Up"
                    },
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "fulfillment_id": "6"
                },
                {
                    "id": "16",
                    "descriptor": {
                        "name": "Family Physician"
                    },
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "fulfillment_id": "6"
                }
            ],
            "fulfillments": [
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": "12",
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                },
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": null,
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                },
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": "150",
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                },
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": null,
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                },
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": null,
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                },
                {
                    "id": "6",
                    "type": "Consultation",
                    "agent": {
                        "id": "SNO-6",
                        "name": "Vijay Dandekar",
                        "cred": "SNO-6",
                        "gender": "M",
                        "tags": {
                            "@abdm/gov/in/first_consultation": null,
                            "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                            "@abdm/gov/in/follow_up": null,
                            "@abdm/gov/in/experience": null,
                            "@abdm/gov/in/languages": "Eng, Hin",
                            "@abdm/gov/in/speciality": "Consultation",
                            "@abdm/gov/in/lab_report_consultation": null,
                            "@abdm/gov/in/education": null,
                            "@abdm/gov/in/hpr_id": null,
                            "@abdm/gov/in/signature": null
                        }
                    },
                    "start": {
                        "time": {
                            "timestamp": "T18:30+00:00"
                        }
                    },
                    "end": {
                        "time": {
                            "timestamp": "T17:30+00:00"
                        }
                    },
                    "tags": {
                        "@abdm/gov.in/slot_id": "6"
                    }
                }
            ]
        }
    }
}
```

# Init Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "std:080",
        "action": "init",
        "timestamp": "2022-07-18T08:05:55.252760Z",
        "core_version": "0.7.1",
        "consumer_id": "eua-nha",
        "consumer_uri": "http://100.96.9.173:8080/api/v1/euaService",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2"
    },
    "message": {
        "order": {
            "id": "d49a3f60-e630-11ec-b41c-99795ccbf2d5",
            "item": {
                "id": "2",
                "descriptor": {
                    "name": "Cardiology Follow Up"
                },
                "fulfillment_id": "6",
                "price": {
                    "currency": "INR",
                    "value": "1000"
                }
            },
            "billing": {
                "name": "Ganesh Borse",
                "address": {
                    "door": "21A",
                    "name": "ABC Apartments",
                    "locality": "Dwarka",
                    "city": "New Delhi",
                    "state": "New Delhi",
                    "country": "India",
                    "area_code": "110011"
                },
                "email": "",
                "phone": "9595163508"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "SNO-6",
                    "name": "Vijay Dandekar",
                    "gender": "F",
                    "tags": {
                        "@abdm/gov/in/education": "MD Medicine",
                        "@abdm/gov/in/experience": "15.0",
                        "@abdm/gov/in/follow_up": "300.0",
                        "@abdm/gov/in/first_consultation": "500.0",
                        "@abdm/gov/in/speciality": "Neurologist",
                        "@abdm/gov/in/languages": "English, Hindi",
                        "@abdm/gov/in/upi_id": "sana.bhatt@okaxis",
                        "@abdm/gov/in/hpr_id": "12345678"
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-06-18T13:00:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-06-18T13:15:00"
                    }
                },
                "tags": {
                    "@abdm/gov.in/slot_id": "6"
                }
            },
            "customer": {
                "id": "61-8787-9274-4422",
                "cred": "ganeshborse@sbxabdm"
            }
        }
    }
}
```

# On Init Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "std:080",
        "action": "on_init",
        "timestamp": "2022-07-18T08:05:55.252760Z",
        "core_version": "0.7.1",
        "consumer_id": "eua-nha",
        "consumer_uri": "http://100.96.9.173:8080/api/v1/euaService",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2",
        "provider_id": "plus91-HSPA",
        "provider_uri": "https://plus91hq.ddns.net/medixcel_uhi"
    },
    "message": {
        "order": {
            "id": "9e0af9b8-1bab-4090-9dbc-7da1815f0f87",
            "state": "PROVISIONALLY_BOOKED",
            "provider": {
                "id": 1,
                "descriptor": {
                    "name": "Lohegaon - Clinic"
                }
            },
            "item": {
                "id": "2",
                "descriptor": {
                    "name": "Cardiology Follow Up"
                },
                "price": {
                    "currency": "INR",
                    "value": null
                },
                "fulfillment_id": "6"
            },
            "billing": {
                "name": "Ganesh Borse",
                "address": {
                    "door": "21A",
                    "name": "ABC Apartments",
                    "locality": "Dwarka",
                    "city": "New Delhi",
                    "state": "New Delhi",
                    "country": "India",
                    "area_code": "110011"
                },
                "email": "",
                "phone": "9595163508"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "SNO-6",
                    "name": "Vijay Dandekar",
                    "gender": "Male",
                    "cred": "SNO-6",
                    "tags": {
                        "@abdm/gov/in/first_consultation": null,
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "PhysicalConsultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-06-18T13:00:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-06-18T13:15:00"
                    }
                },
                "tags": {
                    "@abdm/gov.in/slot_id": "6"
                }
            },
            "quote": {
                "quote": {
                    "price": {
                        "currency": "INR",
                        "value": null
                    },
                    "breakup": [
                        {
                            "title": "Consultation",
                            "price": {
                                "currency": "INR",
                                "value": null
                            }
                        }
                    ]
                }
            },
            "payment": {
                "uri": "payto://ban/98273982749428?amount=INR:110&ifsc=SBIN0000575&message=hello",
                "type": "ON-ORDER",
                "status": "PENDING",
                "tl_method": null,
                "params": null
            }
        }
    },
    "status_code": 200
}
```

# Confirm Request
```json
{
     "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "std:080",
        "action": "confirm",
        "timestamp": "2022-07-18T08:05:55.252760Z",
        "core_version": "0.7.1",
        "consumer_id": "eua-nha",
        "consumer_uri": "http://100.96.9.173:8080/api/v1/euaService",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2"
    },
    "message": {
        "order": {
            "id": "9e0af9b8-1bab-4090-9dbc-7da1815f0f87",
            "item": {
                "id": "2",
                "descriptor": {
                    "name": "Cardiology Follow Up"
                },
                "fulfillment_id": "6",
                "price": {
                    "currency": "INR",
                    "value": "1000"
                }
            },
            "billing": {
                "name": "Amod Suresh Joshi",
                "address": {
                    "door": "21A",
                    "name": "ABC Apartments",
                    "locality": "Dwarka",
                    "city": "New Delhi",
                    "state": "New Delhi",
                    "country": "India",
                    "area_code": "110011"
                },
                "email": "joshiamod@gmail.com",
                "phone": "9970983214"
            },
            "fulfillment": {
                "id": "6",
                "type": "PhysicalConsultation",
                "agent": {
                    "id": "SNO-6",
                    "name": "ganeshborse@hpr.ndhm - Ganesh Vikram Borse",
                    "gender": "M",
                    "tags": {
                        "@abdm/gov/in/education": "MBBS",
                        "@abdm/gov/in/experience": "5.0",
                        "@abdm/gov/in/follow_up": "200.0",
                        "@abdm/gov/in/first_consultation": "300.0",
                        "@abdm/gov/in/speciality": "Cardiology",
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/upi_id": "ganeshborse@icici",
                        "@abdm/gov/in/hpr_id": "73-5232-1888-8686"
                    }
                },
                "start": {
                    "time": {
                        "timestamp": "2022-07-18T13:00:00"
                    }
                },
                "end": {
                    "time": {
                        "timestamp": "2022-07-18T13:15:00"
                    }
                },
                "tags": {
                    "@abdm/gov.in/slot_id": "6"
                }
            },
            "quote": {
                "price": {
                    "currency": "INR",
                    "value": "1000"
                },
                "breakup": [
                    {
                        "title": "Consultation",
                        "price": {
                            "currency": "INR",
                            "value": "1000"
                        }
                    },
                    {
                        "title": "CGST @ 5%",
                        "price": {
                            "currency": "INR",
                            "value": "50"
                        }
                    },
                    {
                        "title": "SGST @ 5%",
                        "price": {
                            "currency": "INR",
                            "value": "50"
                        }
                    },
                    {
                        "title": "Registration",
                        "price": {
                            "currency": "INR",
                            "value": "400"
                        }
                    }
                ]
            },
            "payment": {
                "uri": "https://api.bpp.com/pay?amt=1500&txn_id=ksh87yriuro34iyr3p4&mode=upi&vpa=sana.bhatt@upi",
                "params": {
                    "amount": "1500",
                    "mode": "UPI",
                    "vpa": "sana.bhatt@upi",
                    "transaction_id": "abc128-riocn83920"
                },
                "type": "ON-ORDER",
                "status": "PAID",
                "tl_method": "http/get"
            },
            "customer": {
                "id": "",
                "cred": "amodjoshi@sbx"
            }
        }
    }
}
```

# On Confirm Request
```json
{
    "context": {
        "domain": "nic2004:85111",
        "country": "IND",
        "city": "std:080",
        "action": "on_confirm",
        "core_version": "0.7.1",
        "transaction_id": "b49e6d90-fde1-11ec-b66a-f551703a8c52",
        "message_id": "uh9e6d90-fde1-11ec-b66a-f551703a8da2",
        "timestamp": "2022-07-18T08:10:20.000000",
        "provider_id": "plus91-HSPA",
        "provider_uri": "https://plus91hq.ddns.net/medixcel_uhi"
    },
    "message": {
        "order": {
            "id": "9e0af9b8-1bab-4090-9dbc-7da1815f0f87",
            "state": "CONFIRMED",
            "provider": {
                "id": 1,
                "descriptor": {
                    "name": "Lohegaon - Clinic"
                }
            },
            "item": {
                "id": 2,
                "descriptor": {
                    "name": "Cardiology Follow Up"
                },
                "fulfillment_id": "6",
                "provider_id": 1
            },
            "billing": {
                "name": "Amod Suresh Joshi",
                "address": {
                    "door": "21A",
                    "name": "ABC Apartments",
                    "locality": "Dwarka",
                    "city": "New Delhi",
                    "state": "New Delhi",
                    "country": "India",
                    "area_code": "110011"
                },
                "email": "joshiamod@gmail.com",
                "phone": "9970983214"
            },
            "fulfillment": {
                "id": "6",
                "type": "NA",
                "person": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": null,
                    "image": "",
                    "cred": "SNO-6"
                },
                "agent": {
                    "id": "6",
                    "name": "Vijay Dandekar",
                    "gender": null,
                    "image": "",
                    "cred": "SNO-6",
                    "tags": {
                        "@abdm/gov/in/first_consultation": 0,
                        "@abdm/gov/in/upi_id": "9999999999@okhdfc",
                        "@abdm/gov/in/follow_up": null,
                        "@abdm/gov/in/experience": null,
                        "@abdm/gov/in/languages": "Eng, Hin",
                        "@abdm/gov/in/speciality": "PhysicalConsultation",
                        "@abdm/gov/in/lab_report_consultation": null,
                        "@abdm/gov/in/education": null,
                        "@abdm/gov/in/hpr_id": null,
                        "@abdm/gov/in/signature": null
                    }
                },
                "state": {
                    "descriptor": {
                        "code": ""
                    }
                },
                "time": {
                    "range": {
                        "start": "2022-07-18 13:00:00",
                        "end": "2022-07-18 13:15:00"
                    }
                },
                "tags": null
            },
            "quote": {
                "price": {
                    "currency": "INR",
                    "value": 0,
                    "breakup": []
                }
            },
            "payment": {
                "uri": "",
                "type": "",
                "status": ""
            }
        }
    },
    "status_code": 200
}
```
