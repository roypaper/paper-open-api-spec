An order represents the purchase issued by you to your supplier. 

<h3 fontWeight="{400}">Partner Referencing</h3>

**IMPORTANT**: To properly track transactions between you and your Supplier properly, please ensure the right Supplier id is inserted. This will be critical for tracking payment history as well as credit limit.

Use id as the reference to your existing Supplier. If no Partner (Supplier or both) with the id exists, a new one will be created when you are calling the API. The creation of a new id is made upon the insertion of email, address, or phone number.

**CAUTION**: If a partner already exists with the id, its metadata will be updated with the one in the response body.
Order Amount Behavior
While the Order amount can be calculated from summing the subtotal of the invoice items, we will regard the amount in the total key as the true Order amount. If you want to insert additional information such as discount amount, you can do so in the discount object outside the item.

You can refer to the example below.
```
"items":[
{
"item_name": "SKU0001 - AC LG",
"code": "SKU0001",
"item_description": "AC LG",
"quantity": "1",
"uom": "pcs",
"discount": 0,
"delivery_fee":10000
"price": 1000000,
"total": 1000000,
"tax_total": 0
}
],
"discount": 10000
```
 
<h3 fontWeight="{400}">Register Callback URL</h3>

You need to provide a callback URL endpoint in your system to receive callback from us. With the Callback URL the HTTPS connection will be terminated immediately and a unique id will be returned in the response body. PAPER.ID will POST a message to the callback_url specified in your request in a JSON format application/json. The ID in the response will reflect the ID in the results posted to your Callback URL.
