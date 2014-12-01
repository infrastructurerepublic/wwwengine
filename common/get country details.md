Description
=============

Definition
------------
Gets list of Country Codes, Country Name, Currency Code, Dialling Code, Base 64 image of Country Flag, List of States, State Id.

Usage
------------
Use this command to get country list details.

Availability
-------------
The get command is available to every ISP.

Constraints
=============

Input Parameters
=================
| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
| @userID | Required | Acting User ID | |
| @publicApiKey | Required | Public API key for each ISP generated by WWWengine | 64 |
| @privateApiKey | Required | Private API key for each ISP generated by WWWengine | 64 |
| @queryString | Required | 'actingUserID=' . @userID . '&auth=' . @publicApiKey; | - |
| @hash | Required | Generated by algorithm hash('sha256()', @privateApiKey . @queryString); | - |

URL
===========
```html
https://api.wwwengine.net/registrar/domain-parking/@domainName?@queryString&hash=@hash
```
Method
========
GET

Return Parameters
=================
| Param Name| Definition |
| ------------- | ------------- |
| id | id of country |
| active | status in of country in pannel |
| code |code of country |
| name | full name fo country |
| currencyCode | currency code of country  |
| currencyName | currency Name of country  |
| diallingCode | dailing code of country |
| base64Flag | country flag |
| states | states array of country |
| name | name of states |
| id | id of states |
Example
=========
````
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
https://api.wwwengine.net/country?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````
JSON Response
--------------------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": [
        {
            "id": "31",
            "active": 1,
            "code": "AF",
            "name": "Afghanistan",
            "currencyCode": "AFN",
            "currencyName": "Afghani",
            "diallingCode": "+93",
            "base64Flag": "iVBORw0KGgoAAAANSUhEUgAAABAAAAALCAIAAAD5gJpuAAAABGdBTUEAAK\/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAHuSURBVHjaYtTU1Pz06RMDGPz69evF69f\/WFn\/\/f4N5P4BC1aJMkxMYGD4AZQGcQECiOXdu3dNTU1A1t9\/IMjw+zfjn7\/Mv3\/9\/\/2b7ffvf79+BSj+\/63+9dffXz\/\/\/lw8ezFAALEAAVD1y1ev\/vz+\/efPH6C6\/79+\/f\/56\/+vn\/9\/\/vz38+d79v+3JT79\/P1DgksSaAlAALH8+\/fv79+\/QNVA5b9\/gQz+z8DwLzHh\/98\/\/\/ce+H\/yGFDg++\/vv37\/\/PXnJ9BhAAEonHcjAEAQCKKMhdGIVZI7lqXc4Q+DTd9sye+EGUGA38atlb3R7KgeRwDZXI5NGfIEEMuPb9\/+gM3+BTTk5w+ge\/5xcvwxM2P4\/oORg+3\/jx9\/fvz7\/uf7D6Ak2AaAAGL5+uMH0DlA5T\/BAOjLv\/fvMolL\/uPm+XP9BuO3b8AAA2r69ecXSMMvBoAAYmH4D3T27x8\/fkD0\/Pvx4\/+OXT\/ERP\/\/\/sN25ToD0FygM3\/\/BOr5\/e83UANAALFAgh8IgHqAGoBu+H\/tOuf5C\/\/Amv+C3M\/w4+\/3X8Bw+QvSABBAIA1AdULCwhBPM\/z8xfDrJ+OvX4w\/fzL+\/g0MEz5xBkVe4d9\/fv\/59wfoaYAAYmRABQ+BYQqOYzjyAMaSOjimgRwuBoAAAwD7RWlTjl53wAAAAABJRU5ErkJggg==",
            "languageCodes": [

            ],
            "states": [
                {
                    "name": "Badakhshan",
                    "id": "8378"
                },
                {
                    "name": "Badghis",
                    "id": "8379"
                },
                {
                    "name": "Baghlan",
                    "id": "8380"
                },
                {
                    "name": "Balkh",
                    "id": "8381"
                },
                {
                    "name": "Bamian",
                    "id": "8382"
                },
                {
                    "name": "Daykondi",
                    "id": "8383"
                },
                {
                    "name": "Farah",
                    "id": "8384"
                },
                {
                    "name": "Faryab",
                    "id": "8385"
                },
                {
                    "name": "Ghazni",
                    "id": "8386"
                },
                {
                    "name": "Ghowr",
                    "id": "8387"
                },
                {
                    "name": "Helmand",
                    "id": "8388"
                },
                {
                    "name": "Herat",
                    "id": "8389"
                },
                {
                    "name": "Jowzjan",
                    "id": "8390"
                },
                {
                    "name": "Kabul [Kabol]",
                    "id": "8391"
                },
                {
                    "name": "Kandahar",
                    "id": "8392"
                },
                {
                    "name": "Kapisa",
                    "id": "8393"
                },
                {
                    "name": "Khowst",
                    "id": "8394"
                },
                {
                    "name": "Konar [Kunar]",
                    "id": "8395"
                },
                {
                    "name": "Kondoz [Kunduz]",
                    "id": "8396"
                },
                {
                    "name": "Laghman",
                    "id": "8397"
                },
                {
                    "name": "Lowgar",
                    "id": "8398"
                },
                {
                    "name": "Nangrahar [Nangarhar]",
                    "id": "8399"
                },
                {
                    "name": "Nimruz",
                    "id": "8400"
                },
                {
                    "name": "Nurestan",
                    "id": "8401"
                },
                {
                    "name": "Oruzgan [Uruzgan]",
                    "id": "8402"
                },
                {
                    "name": "Paktia",
                    "id": "8404"
                },
                {
                    "name": "Paktika",
                    "id": "8405"
                },
                {
                    "name": "Panjshir",
                    "id": "8403"
                },
                {
                    "name": "Parwan",
                    "id": "8406"
                },
                {
                    "name": "Samangan",
                    "id": "8407"
                },
                {
                    "name": "Sar-e Pol",
                    "id": "8408"
                },
                {
                    "name": "Takhar",
                    "id": "8409"
                },
                {
                    "name": "Wardak [Wardag]",
                    "id": "8410"
                },
                {
                    "name": "Zabol [Zabul]",
                    "id": "8411"
                }
            ]
        }
}

````