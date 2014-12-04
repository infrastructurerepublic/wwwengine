Description
=============

Definition
------------
Purchase a managed dns of enterprise dns.

Usage
------------
*The Purchase command enables direct real-time purchases.
*The Purchase command is typically used for a single-name purchase and returns an immediate success/failure response.
*Purchase a managed dns of enterprise dns is divided into: ** Create Invoice ** Charge Invoice

Availability
-------------
All ISPs have access to this command.

Constraints
=============
````
\Schemas::$list['managedDnsZone'] = array(
	'meta' => array('name' => 'managed dns zone'),
	'soldTo' => array('type' => 'int'),
	'soldBy' => array('type' => 'int'),
	'transactionType' => array('type' => 'string', 'valid' => array('buy', 'renew')),
	'productIdentifier' => array('type' => 'genericstring', 'valid' => array('managed-dns')),
	'name' => array('type' => 'domain'),
	'period' => array('type' => 'int')
);
````

Domain names must meet the following requirements:
------------
* The Username and Password must be valid.
* The domain name(s) to which privacy is to be purchase must be valid. (See requirements under the Check Availablity.)
* WWWengine must be able to sell the name you are trying to register.

Create Invoice Input Parameters
==================================

| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
| @domainName | Required | Domain Name entered by user with TLD | 63 |
|	soldBy	|	Required	|	User ID of dns enterprise sold by user	|		|
|	SoldTo	|	Required	|	User ID of domain sold to user	|		|
|	period	|	Required	|	Number of Years the domain needs to be registered for	|	64	|
|	name	|	Required	|	domain name for which privacy applyin |	-	|
|	transactionType	|	Required	|	Transaction Type of process	|	64	|
|	productIdentifier	|	Required	|	product type managed dns 	|	-	|
|	type	|	Required	|	Type of product	|	64	|
|	@userID	|	Required	|	Acting User ID	|		|
|	@publicApiKey	|	Required	|	Public API key for each user generated by system.	|	64	|
|	@privateApiKey	|	Required	|	 Private API key of user.	|	64	|
|	@queryString	|	Required	|	'actingUserID=' . @userID . '&auth=' . @publicApiKey;	|	-	|
|	@hash	|	Required	|	It is  generated by algorithm hash('sha256()', @privateApiKey .  @queryString);	|	-	|
|	@tld	|	Required	|	Tld for which you are adding contact details	|	20	|


URL
===========
```html
https://api.wwwengine.net/invoice/order/dns-enterprise?@queryString&hash=@hash
```
Method
========
POST

Create Invoice Return Parameters
---------------------

| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |
| Message | Message returned from response |
| id | ID of invoice generated for domain |
| OrderID | ID of order generated for domain |


Example
=========
````
@domainName: zeneregistries.com
@userID: 1
@publicApiKey: 38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae
@privateApiKey: 1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
@queryString: 'actingUserID=' . @userID . '&auth=' . @publicApiKey;
@hash: it is generated by algorithm hash('sha256()', @privateApiKey . @queryString);
````
Method
----------

POST

URL
----------

````html
https://api.wwwengine.net/registrar/dns-enterprise?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
````
Create Invoice JSON POST Parameters
---------------------

````json
{
    "soldBy": "46476",
    "soldTo": "47846",
    "period": "1",
    "name": "zeneregistries.com",
    "transactionType": "buy",
    "productIdentifier": "managed-dns",
    "type": "dns-enterprise",
    "head": {
        "userIpAddress": "114.143.136.255"
    }
}
````

Create Invoice JSON POST Response
-----------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": 20625,
        "orderID": 57003
    }
}
````

Charge Invoice Input Parameters
==================================

| Param Name | Obligation | Definition | Max Size |
| ------------- | ------------- | ------------- | ------------- |
|	@InvoiceID	|	Required	|	Invoice ID return from first step i.e create invoice	|	63	|
|	@userID	|	Required	|	Acting User ID	|		|
|	@publicApiKey	|	Required	|	Public API key for each user generated by system.	|	64	|
|	@privateApiKey	|	Required	|	 Private API key of user.	|	64	|
|	@queryString	|	Required	|	'actingUserID=' . @userID . '&auth=' . @publicApiKey;	|	-	|
|	@hash	|	Required	|	it is  generated by algorithm hash('sha256()', @privateApiKey .  @queryString);	|	-	|
|	@tld	|	Required	|	Tld for which you are adding contact details	|	20	|

Charge Invoice URL
----------

```html
http://api.wwwengine.net/invoice/charge/@invoiceID?@queryString&hash=@hash
```

Charge Invoice Method
----------
PUT

Charge Invoice Return Parameters
---------------------

| Param Name| Definition |
| ------------- | ------------- |
| resultCode | Result status code |
| response | Actual response |
| Message | Message returned from response |
| id | ID of domain |
| Name | Name of domain |
| CrDate | Creation Date of Domain |
| ExDate | Expiry Date of Domain |

Charge Invoice Example
-------------------------

This is an example of charging invoice of domain registration and creating order of domain registration.

URL
------

```html
https://api.wwwengine.net/invoice/charge/20515?actingUserID=1&auth=38f9c45022de9ccd105545423b77e950af7dbc5eb31660d6bf1160431513f5ae&hash=1ca9b5502935824ea5674e3d8f69663e3dcd077fab85b3810aadcf2ae3fda5d7
```

Charge Invoice JSON PUT Parameters
---------------------

None

Charge Invoice JSON PUT Response
-----------

````json
{
    "resultCode": 1,
    "message": "Changes saved",
    "response": {
        "id": 45891,
        "name": "zeneregisteries.com",
        "crDate": "2014-10-08T14:15:51.0409Z",
        "exDate": "2015-10-08T14:15:51.0409Z"
    }
}
````