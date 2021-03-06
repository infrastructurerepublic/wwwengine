Description
=============

Definition
------------
Add Child Name Servers to an existing domain.

Usage
------------
Use this command to add Child Name Servers to an existing domain.

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
| name | Required | Host Name | - |
| ipAddresses | Required | IP addresses of host | Array |
| version | Required | Version of IP address | - |
| address | Required | IP address | 255 |
| metadata | Required | Meta info of Child Name Server | - |
| UserID | Required | UserID of domain | 65 |
| @userID | Required | Acting User ID |  |
| @publicApiKey | Required | Public API key for each ISP generated by WWWengine | 64 |
| @privateApiKey | Required | Private API key for each ISP generated by WWWengine | 64 |
| @queryString | Required | 'actingUserID=' . @userID . '&auth=' . @publicApiKey; | - |
| @hash | Required | Generated by algorithm hash('sha256()', @privateApiKey . @queryString); | - |
|	@tld	|	Required	|	Tld for which you are adding Child Name Server	|	20	|

URL
===========
```html
https://api.wwwengine.net/registrar/host/@tld?@queryString&hash=@hash
```
Method
========
POST

Return Parameters
=================
| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Response returned as true or false |
| Message | Message returned in the response |
| Id | Id of child name servers entry |
| Name | Host name |
| crDate | Creation date |

Example
=========

Adds child name servers to a domain.

Method
----------

POST

URL
----------

````html
https://api.wwwengine.net/registrar/host/com?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````

JSON POST Parameters
---------------------

````json
{
    "name": "ns1.lovephp.net",
    "ipAddresses": [
        {
            "version": "v4",
            "address": "122.25.25.25"
        }
    ],
    "metadata": {
        "userID": "47721"
    },
    "head": {
        "userIpAddress": "206.183.111.25"
    }
}
````

JSON POST Response
--------------------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": 927,
        "name": "ns1.lovephp.com",
        "crDate": "2014-09-25T04:00:00.0000Z"
    }
}
````
