An invoice represents the sales transaction issued by you to your customer. In Paper.id, an invoice must be tied to a Partner and in the case of Sales Invoice partner entity will be tied to an object named Customer.

<H2 fontWeight="{400}">Customer</H2>

A Customer is a Partner object with type "Customer". A Customer has to be created before a Sales Invoice is created and assigned to the Customer. You can create, view and edit Partner via Paper.id dashboard.

<h3 fontWeight="{400}">Partner Referencing</h3>

**IMPORTANT**: To properly track transactions between you and your Customer  properly, please ensure the right Customer id is inserted. This will be critical for tracking payment history as well as credit limit.

Use id as the reference to your existing Customer. If no Partner (Customer or both) with the id exists, a new one will be created when you are calling the API. The creation of a new id is made upon the insertion of email, address, or phone number.

CAUTION: If a partner already exists with the id, its metadata will be updated with the one in the response body.

<h3 fontWeight="{400}">Status Referencing</h3>

On Paper.id, we use “status” on documents to help users identify the state of the document. There are 2 types of status, document status and acceptance status. The status may vary depending on the document type as well. For example:
Sales Invoice:
Payment status = “paid, unpaid, partially paid, overdue”
Acceptance status =’accept, reject, sent, void”
Purchase Order:
Document status = “confirmed, completed, 

<H2 fontWeight="{400}">Invoice Amount Behavior</H2>
While the Invoice amount can be calculated from summing the subtotal of the invoice items, we will regard the amount in the total key as the true Invoice amount. If you want to insert additional information such as shipping amount or discount amount, you can do so in the additional_info object.
You can refer to the example below:

```
"items": [
{
    "name": "item 01",
    "code":"P.0001",
    "description": "color is black",
    "quantity": 2,
    "price": 10000,
    "discount": 0,
    "tax": 0,
},
],
"additional_fee":
{
    "delivery_fee": 20000
},
"total": 25000,   
// If the amount in the total key is different, then the system will assign the total amount of the Invoice from this key rather than subtotal calculation of the Invoice. 
// (Eg: The actual amount calculated of this invoice is IDR 40.000, however it will override to IDR 25.000 as it is.
"additional_info": {
    "cabang": "Sunter",
    "project": "Stadium GBK"
}
]
```