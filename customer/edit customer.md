Description
=============

Definition
------------
Edit Customer details under an ISP.

Usage
------------
Use this command to edit Customer details under an ISP.

Availability
-------------
This command is available to every ISP.

Constraints
=============

The actingUserID, authKey and hash must be valid.

Input Parameters
=================

| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
|	contactInfo	|	Required	|	User's contact Info	|		|
|	PostalInfo	|	Required	|	User's postal Info	|		|
|	title	|	Required	|	Title of user (Mr./Mrs./Other)	|		|
|	organization	|	Required	|	Organization of user	|		|
|	firstName	|	Required	|	FirstName of user	|		|
|	LastName	|	Required	|	Last name of user	|		|
|	address	|	Required	|	Address of user	|		|
|	Street	|	Required	|	Streets1,Streets2,Streets3	|		|
|	city	|	Required	|	City of user	|		|
|	State	|	Required	|	State of user	|		|
|	countryCode	|	Required	|	Country Code of user	|		|
|	postalCode	|	Required	|	Postalof user	|		|
|	Voice	|	Required	|	Phone number of user	|		|
|	Number	|	Required	|	Phone number	|		|
|	ext	|	Required	|	Extention	|		|
|	cell	|	Required	|	User 'sCell phone	|		|
|	Type	|	Required	|	Type of cellphone(e.g. Window)	|		|
|	Number	|	Required	|	Phone number	|		|
|	ext	|	Required	|	Extention cell number	|		|
|	countryCode	|	Required	|	Country Code of user's cell number	|		|
|	callInPin	|	Required	|	User's call in pin	|		|
|	Fax	|	Required	|	Fax number of user	|		|
|	number	|	Required	|	Fax number	|		|
|	ext	|	Required	|	Extention	|		|
|	Email	 | Required	| Email of the user |
|	Preference	|	Required	|	User's phone number preferance	|		|
|	phoneNoType	|	Required	|	User's phone numer type	|		|
|	@id	|	Required	|	ID of user to be edited	|		|
|	@userID	|	Required	|	Acting User ID	|		|
|	@publicApiKey	|	Required	|	Public API key for each user generated by system.	|	64	|
|	@privateApiKey	|	Required	|	 Private API key of user.	|	64	|
|	@queryString	|	Required	|	'actingUserID=' . @userID . '&auth=' . @publicApiKey;	|	-	|
|	@hash	|	Required	|	it is  generated by algorithm hash('sha256()', @privateApiKey .  @queryString);	|	-	|

URL
===========
```html
https://api.wwwengine.net/user/@id?@queryString&hash=@hash
```
Method
========
PUT

Return Parameters
=================
| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |

Example
=========

This is an example of editing a Customer under an ISP.

Method
----------

PUT

URL
----------

````html
https://api.wwwengine.net/user/@id?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````
JSON PUT Parameters
--------------------

````json
{
    "contactInfo": {
        "postalInfo": {
            "title": "Mr.",
            "firstName": "Abc",
            "lastName": "Xyz",
            "organization": "ABC",
            "address": {
                "street": [
                    "Ax Palace,",
                    "118, Old Hanuman sd, ",
                    "Kalbadevi Road,"
                ],
                "city": "Mumbai",
                "postalCode": "400002",
                "countryCode": "IN",
                "state": "Maharashtra"
            }
        },
        "cell": {
            "type": "android",
            "number": "+91.8885242124",
            "countrycode": "29",
            "2FactorAuth": "0"
        },
        "voice": {
            "number": "+91.12121233",
            "countrycode": "29"
        },
        "fax": {
            "number": "+91.2222421239",
            "countrycode": "29"
        }
    },
    "email": "abc@gmail.com",
    "preferences": {
        "phoneNoType": "work"
    },
    "head": {
        "userIpAddress": "10.10.11.77"
    }
}
````

JSON PUT Response
-----------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": true
}
````
