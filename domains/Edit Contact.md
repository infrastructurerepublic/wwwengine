Description
=============

Definition
------------
Edit existing domain's contact details.

Usage
------------
Use this command to edit an existing domain's contact details.

Availability
-------------
This command is available to every ISP.

Constraints
=============

The actingUserID , authKey and hash must be valid.

Input Parameters
=================

| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
|	PostalInfo	|	Required	|	This object contain postal info of user	|	-	|
|	Name	|	Required	|	Name of user	|	65	|
|	Organization	|	Required	|	Organization of user	|	50	|
|	address	|	Required	|	Address of user	|		|
|	Street	|	Required	|	Street of user	|		|
|	city	|	Required	|	City of user	|		|
|	State	|	Required	|	State of user	|		|
|	countryCode	|	Required	|	Country Code of user	|		|
|	postalCode	|	Required	|	Postalof user	|		|
|	Misc	|	Optional	|	Miscleneuse details	|	object	|
|	mobilePhone	|	Optional	|	Mobile phone nynbers of users	|	Array	|
|	contactPhone	|	Optinal	|	Contact phone number type	|	50	|
|	Voice	|	Required	|	Phone number of user	|		|
|	Number	|	Required	|	Phone number	|		|
|	ext	|	Required	|	Extention	|		|
|	Fax	|	Required	|	Fax number of user	|		|
|	number	|	Required	|	Fax number	|		|
|	ext	|	Required	|	Extention	|		|
|	ContactID	|	Required	|	ContactID of this contact	|	25	|
|	Email	|	Required	|	Email id of user	|	20	|
|	@contactID	|	Required	|	ContactID which you want to edit	|	20	|
|	@userID	|	Required	|	Acting User ID	|		|
|	@publicApiKey	|	Required	|	it is publick api key for each user generated by system.	|	64	|
|	@privateApiKey	|	Required	|	 It is private key of user.	|	64	|
|	@queryString	|	Required	|	'actingUserID=' . @userID . '&auth=' . @publicApiKey;	|	-	|
|	@hash	|	Required	|	it is  generated by algorithm hash('sha256()', @privateApiKey .  @queryString);	|	-	|
|	@tld	|	Required	|	Tld for which you are adding contact details	|	20	|


URL
===========
```html
https://api.wwwengine.net/registrar/contact/@tld/@contactID?@queryString&hash=@hash
```
Method
========
POST

Return Parameters
=================

| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |
| id | Id of data |
| ContactID | Actual contactId of domain |
| CrDate | Creation Date |

Example
=========

This is an example for editing domain's registarnt, admin, billing, techincal contacts.

Method
----------

PUT

URL
----------

````html
https://api.wwwengine.net/registrar/contact/com/@d_137445454?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````

JSON POST Parameters
--------------------

````json
{
    "postalInfo": {
        "address": {
            "street": [
                "22 Mumbai Samachar marg",
                "II floor,above George restaurant",
                ""
            ],
            "city": "Mumbai",
            "postalCode": "400023",
            "countryCode": "IN",
            "state": "Maharashtra"
        },
        "firstName": "Abc",
        "lastName": " Xyz",
        "name": " Abc  Xyz",
        "organization": "Abc Xyz"
    },
    "misc": {
        "mobilePhone": [],
        "contactPhone": "homePhone"
    },
    "voice": {
        "number": "+91.225585221"
    },
    "fax": {
        "number": "+91.2222721542"
    },
    "contactID": "df!@d_1374384523",
    "email": "amc@gmail.com",
    "head": {
        "userIpAddress": "206.183.111.25"
    }
}
````


JSON Response
--------------------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": 93206,
        "contactID": "01c12fe78a587ee2",
        "crDate": "2014-08-24UTC18:14:24.08240"
    }
}
````
