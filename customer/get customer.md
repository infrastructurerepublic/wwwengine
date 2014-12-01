Description
=============

Definition
------------
Get Customer.

Usage
------------
Use this command to Get Customer.

Availability
-------------
The get command is available to every ISP.

Constraints
=============

Input Parameters
=================
| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
| @id | Required | customerID | 63 |
| @userID | Required | Acting User ID | |
| @publicApiKey | Required | Public API key for each ISP generated by WWWengine | 64 |
| @privateApiKey | Required | Private API key for each ISP generated by WWWengine | 64 |
| @queryString | Required | 'actingUserID=' . @userID . '&auth=' . @publicApiKey; | - |
| @hash | Required | Generated by algorithm hash('sha256()', @privateApiKey . @queryString); | - |

URL
===========
```html
https://api.wwwengine.net/customer/@id?@queryString&hash=@hash
```
Method
========
GET

Return Parameters
=================
All user info

Example
=========
````
@domainName: zenregistry.com
@userID: 1
@publicApiKey: 38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae
@privateApiKey: 1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
@queryString: 'actingUserID=' . @userID . '&auth=' . @publicApiKey;
@hash: it is generated by algorithm hash('sha256()', @privateApiKey . @queryString);
````
Method
----------

GET

URL
----------

````html
https://api.wwwengine.net/customer/145?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````
JSON Response
--------------------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": "145",
        "status": "active",
        "type": "customer",
        "parentID": "137",
        "email": "abc@abc.com",
        "password": "abc123",
        "buyingCurrency": "TRY",
        "totalReceipts": "65307.58000",
        "created": "2014-05-24T08:14:44.700",
        "updated": "2014-11-04T09:02:59.910",
        "creatorID": "137",
        "updaterID": "145",
        "contactInfo": {
            "countryID": "29",
            "voice": {
                "number": "+91.11441114",
                "ext": "635241",
                "countrycode": "29"
            },
            "fax": {
                "number": "+91.9821293862",
                "ext": "9821",
                "countrycode": "29"
            },
            "callInPin": "1985",
            "voicecode": "29",
            "cellcode": "33",
            "userlogo": "\/user-info\/userlogo\/92.png",
            "faxcode": "29",
            "postalInfo": {
                "title": "Mr.",
                "address": {
                    "street": [
                        "4, abc",
                        "",
                        ""
                    ],
                    "city": "mumbai",
                    "state": "Maharashtra",
                    "countryCode": "IN",
                    "postalCode": "400090"
                },
                "firstName": "Pravin",
                "lastName": "sin",
                "organization": "WWWEngine"
            },
            "cell": {
                "number": "+355.344233",
                "type": "android",
                "countrycode": "33"
            }
        },
        "userInfo": {
            "dateOfBirth": "1890-01-01"
        },
        "preferences": {
            "phoneNoType": "work",
            "billingInfo": {
                "funds_threshold_preferedcurrency": null,
                "funds_threshold_higheramount": null,
                "preferedcurrency": "disabled",
                "higheramount": null,
                "credditCardDetails": null,
                "preferedgateway": "3"
            }
        },
        "socialInfo": {
            "facebookpage": "http:\/\/www.facebook.com\/test",
            "googleplus": "http:\/\/plus.google.com\/"
        },
        "debitaccountbalance": {
            "creditBalance": "10050727.35000"
        },
        "parentContactDetails": {
            "sales": {
                "id": "77",
                "userID": "137",
                "email": "email@abc.com",
                "fromEmailName": "Third ISP Brand Sales Team",
                "phoneNumber": "+852.74464544",
                "ext": "",
                "contactType": "sales",
                "key": null,
                "value": null,
                "businessName": "Third ISP Brand22"
            },
            "support": {
                "id": "78",
                "userID": "137",
                "email": "support@abc.com",
                "fromEmailName": "Third ISP Brand Support Team",
                "phoneNumber": "+44.1144144",
                "ext": "",
                "contactType": "support",
                "key": "deskurl",
                "value": "",
                "businessName": "Third ISP Brand22"
            },
            "billing": {
                "id": "79",
                "userID": "137",
                "email": "billing@abc.com",
                "fromEmailName": "Third ISP Brand Billing Team",
                "phoneNumber": "+81.9820903702",
                "ext": "",
                "contactType": "billing",
                "key": null,
                "value": null,
                "businessName": "Third ISP Brand22"
            },
            "abuse": {
                "id": "80",
                "userID": "137",
                "email": "abuse@abc.com",
                "fromEmailName": "Third ISP Brand Abuse Team",
                "phoneNumber": "+504.1444122",
                "ext": "666",
                "contactType": "abuse",
                "key": "deskurl",
                "value": "",
                "businessName": "Third ISP Brand22"
            }
        },
        "allowipv4address": [

        ],
        "availableGateways": {
            "3": {
                "id": "3",
                "userID": "137",
                "moduleIdentifier": "OmniPay",
                "gatewayIdentifier": "PayPal_Express",
                "description": "PayPal (Visa, Master, PayPal)",
                "rank": "1",
                "info": {
                    "username": "abc.com",
                    "password": "abc123",
                    "signature": "AFcWxggdhkfdAdfdfYYRCpdfsdSSRl31AvfXfts2re2-zX5dfdULH3QpAs",
                    "testMode": "yes"
                },
                "creditCustomerNetAmount": 0,
                "creditIspNetAmount": 1,
                "sendReminder": 1,
                "creatorID": "137",
                "updaterID": "137",
                "active": 1,
                "gateTypeId": "4",
                "name": "PayPal Express Checkout",
                "redirectFlag": 1,
                "created": "2014-05-20T12:39:11.270",
                "updated": "2014-05-20T14:08:01.647",
                "logo": "\/user-payment-gateway-type\/logo\/4.png",
                "currencies": [
                    "USD"
                ],
                "gatewayID": "3",
                "gatewayAccessForCustomerOption": "allowalltransaction",
                "gatewayAccessForCustomerValue": "allcustomers",
                "gatewayAccessForIspOption": "allowalltransaction",
                "gatewayAccessForIspValue": "allisps",
                "creditCustomerWithNetAmt": 0,
                "creditIspWithNetAmt": 0,
                "reminderNoOfDays": "0",
                "gatewayAccessOption": "allowalltransaction"
            },
            "5": {
                "id": "5",
                "userID": "137",
                "moduleIdentifier": "OmniPay",
                "gatewayIdentifier": "Stripe",
                "description": "Visa, Master, Amex, Discover, JCB",
                "rank": "2",
                "info": {
                    "apiKey": "sk_tedf_eqHdasZ8ydfdfdfdy"
                },
                "creditCustomerNetAmount": 0,
                "creditIspNetAmount": 1,
                "sendReminder": 1,
                "creatorID": "137",
                "updaterID": "137",
                "active": 1,
                "gateTypeId": "10",
                "name": "Stripe",
                "redirectFlag": 0,
                "created": "2014-05-25T10:35:36.197",
                "updated": "2014-05-25T14:19:26.120",
                "logo": "\/user-payment-gateway-type\/logo\/10.png",
                "currencies": [
                    "USD"
                ],
                "gatewayID": "5",
                "gatewayAccessForCustomerOption": "allowalltransaction",
                "gatewayAccessForCustomerValue": "allcustomers",
                "gatewayAccessForIspOption": "allowalltransaction",
                "gatewayAccessForIspValue": "allisps",
                "creditCustomerWithNetAmt": 0,
                "creditIspWithNetAmt": 0,
                "reminderNoOfDays": "0",
                "gatewayAccessOption": "allowalltransaction"
            },
            "94": {
                "id": "94",
                "userID": "137",
                "moduleIdentifier": "Paypal",
                "gatewayIdentifier": "Payflow_Pro",
                "description": "Test payflow pro",
                "rank": "2",
                "info": {
                    "username": "fdfdadf",
                    "password": "fdfdfd)fd#",
                    "vendor": "dfordomainsllc",
                    "partner": "PayPal",
                    "testMode": "yes",
                    "fixedFeeChargeCurrency": "USD",
                    "fixedFeeChargeAmount": "125",
                    "fluctuatingFeeChargePercentage": "20"
                },
                "creditCustomerNetAmount": 0,
                "creditIspNetAmount": 1,
                "sendReminder": 0,
                "creatorID": "137",
                "updaterID": "137",
                "active": 1,
                "gateTypeId": "27",
                "name": "Payflow Pro",
                "redirectFlag": 0,
                "created": "2014-07-15T13:15:09.990",
                "updated": "2014-09-15T13:13:27.453",
                "logo": "\/user-payment-gateway-type\/logo\/27.png",
                "currencies": [
                    "USD"
                ],
                "gatewayID": "94",
                "gatewayAccessForCustomerOption": "allowalltransaction",
                "gatewayAccessForCustomerValue": "allcustomers",
                "gatewayAccessForIspOption": "allowalltransaction",
                "gatewayAccessForIspValue": "allisps",
                "creditCustomerWithNetAmt": 0,
                "creditIspWithNetAmt": 0,
                "reminderNoOfDays": "0",
                "gatewayAccessOption": "allowalltransaction"
            },
            "102": {
                "id": "102",
                "userID": "137",
                "moduleIdentifier": "OmniPay",
                "gatewayIdentifier": "Payu",
                "description": "Test Gateway",
                "rank": "2",
                "info": {
                    "key": "fdfdfd",
                    "SALT": "fdfaereSdf",
                    "creditCard": "0.5",
                    "dinrCard": "1",
                    "amexCard": "2",
                    "debitLTCard": "4",
                    "debitGTCard": "8",
                    "netBanking": "16",
                    "testMode": "yes"
                },
                "creditCustomerNetAmount": 1,
                "creditIspNetAmount": 1,
                "sendReminder": 1,
                "creatorID": "137",
                "updaterID": "137",
                "active": 1,
                "gateTypeId": "34",
                "name": "PayU India Redirect",
                "redirectFlag": 1,
                "created": "2014-10-25T12:48:34.317",
                "updated": "2014-10-25T13:00:36.807",
                "logo": "\/user-payment-gateway-type\/logo\/34.png",
                "currencies": [
                    "INR"
                ],
                "gatewayID": "102",
                "gatewayAccessForCustomerOption": "allowalltransaction",
                "gatewayAccessForCustomerValue": "allcustomers",
                "gatewayAccessForIspOption": "allowalltransaction",
                "gatewayAccessForIspValue": "allisps",
                "creditCustomerWithNetAmt": 0,
                "creditIspWithNetAmt": 0,
                "reminderNoOfDays": "0",
                "gatewayAccessOption": "allowalltransaction"
            },
            "106": {
                "id": "106",
                "userID": "137",
                "moduleIdentifier": "OmniPay",
                "gatewayIdentifier": "Payumoney",
                "description": "PATest Money",
                "rank": "1",
                "info": {
                    "key": "SAAadsdSd",
                    "SALT": "SXdfdDsdfd",
                    "creditCard": "1",
                    "dinrCard": "2",
                    "amexCard": "3",
                    "debitLTCard": "4",
                    "debitGTCard": "5",
                    "netBanking": "3.3",
                    "testMode": "yes"
                },
                "creditCustomerNetAmount": 1,
                "creditIspNetAmount": 1,
                "sendReminder": 0,
                "creatorID": "137",
                "updaterID": "137",
                "active": 1,
                "gateTypeId": "35",
                "name": "PayU Money Redirect",
                "redirectFlag": 1,
                "created": "2014-10-31T12:26:08.417",
                "updated": "2014-11-03T10:33:59.863",
                "logo": "\/user-payment-gateway-type\/logo\/35.png",
                "currencies": [
                    "INR"
                ],
                "gatewayID": "106",
                "gatewayAccessForCustomerOption": "allowalltransaction",
                "gatewayAccessForCustomerValue": "allcustomers",
                "gatewayAccessForIspOption": "allowalltransaction",
                "gatewayAccessForIspValue": "allisps",
                "creditCustomerWithNetAmt": 0,
                "creditIspWithNetAmt": 0,
                "reminderNoOfDays": "0",
                "gatewayAccessOption": "allowalltransaction"
            }
        },
        "parentBrandName": [
            {
                "brandname": "Third ISP Brand22",
                "userID": "137",
                "id": "137"
            }
        ]
    }
}
````