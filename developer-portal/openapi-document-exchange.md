# Document Exchange

Document Exchange allows you to create and send business documents exchanged between companies. The main document that we will be covering is invoices with other documents such as Sales Invoice, Purchase Order, Digital Payment, etc. Other documents will be updated later.
Partner Referencing


**IMPORTANT :** To properly track transactions between you and your Supplier properly, please ensure the right Supplier id is inserted. This will be critical for tracking payment history as well as credit limit.
Use id as the reference to your existing Supplier. If no Partner (Customer or Supplier) with the id exists, a new one will be created when you are calling the API. The creation of a new id is made upon the insertion of email, address, or phone number.


**CAUTION :** If a partner already exists with the id, its metadata will be updated with the one in the response body.

<H2 fontWeight="{400}">Register Callback URL</H2>

You need to provide a callback URL endpoint in your system to receive callback from us. With the Callback URL the HTTPS connection will be terminated immediately and a unique id will be returned in the response body. PAPER.ID will POST a message to the callback_url specified in your request in a JSON format application/json. The ID in the response will reflect the ID in the results posted to your Callback URL.

<H2 fontWeight="{400}">Partner Referencing</H2>

**IMPORTANT :** To properly track transactions between you and your Supplier properly, please ensure the right Supplier id is inserted. This will be critical for tracking payment history as well as credit limit.


Use id as the reference to your existing Supplier. If no Partner (Supplier or both) with the id exists, a new one will be created when you are calling the API. The creation of a new id is made upon the insertion of email, address, or phone number.


**CAUTION :** If a partner already exists with the id, its metadata will be updated with the one in the response body.

```
{
    "number": "0037",
    "name": "George Cafe",
    "email": "georgecafe@ymail.com",
    "phone": "0182737123",
    "address1": "jl. Jati Sari no.8a rt03/007",
    "address2": "Jakarta Utara 12540",
    "account_receivable_id": "58e31ce1-88c3-4df3-9ece-5141e6211a1b",
    "account_payable_id": "443b93d3-b919-4404-abdc-26c5013cb5c5",
    "city": "Kota Jakarta Timur",
    "state": "DKI Jakarta",
    "postal_code": 10293,
    "type": "Both",
    "partner_company_type": "perorangan",
    "bank_accounts": [
        {
            "bank_account_no": "0027799977",
            "bank_account_name": "PAKAR DIGITAL GLOBAL PT",
            "bank_branch_name": null,
            "bank_city_name": "",
            "bank_name": "Bank Central Asia (BCA)"
        }
    ]
}
```

<H2 fontWeight="{400}">Item UOM</H2>

Item UOM can be inputted in Paper.id dashboard first and its code can be referenced in the API. For example, “Piece” UOM’s code `PC` can be referenced in the API.

**CAUTION :** if you input a `code` in the `items` to reference a product, the UOM in the API needs to correspond to the UOM of the product

<H2 fontWeight="{400}">Order Amount Behavior</H2>

While the Order amount can be calculated from summing the subtotal of the invoice items, we will regard the amount in the total key as the true Order amount. If you want to insert additional information such as discount amount, you can do so in the discount object outside the item.

You can refer to the example below.


```

"items": [
    {
    "item_name": "SKU0001 - AC LG",
    "code": "SKU0001",
    "item_description": "AC LG",
    "quantity": "1",
    "uom": "pcs",
    "discount": 0,
    “delivery_fee”:10000
    "price": 1000000,
    "total": 1000000,
    "tax_total": 0
    }
],
"discount": 0

```


**Additional Info**


Paper.id allows you to add additional key-value pairs of your own in the document level and item level.


**Additional Fee**


Additional Fee can be used to add fee after the subtotal line. A fee needs to be defined beforehand in Paper.id Custom Field. 


**Incoterm**


The Incoterms or International Commercial Terms are a series of pre-defined commercial terms usually agreed upon by international suppliers and buyers. The valid acceptable incoterm codes or values in the Purchase Order API are:


| Code | Description                       |
|------|-----------------------------------|
| EXW  | Ex Works                          |
| FCA  | Free Carrier                      |
| FAS  | Free Alongside Ship               |
| FOB  | Free On Board                     |
| CFR  | Cost and Freight                  |
| CIF  | Cost, Insurance & Freight         |
| CPT  | Carriage Paid To                  |
| CIP  | Carriage & Insurance Paid To      |
| DPU  | Delivered At Place Unloaded       |
| DAP  | Delivered At Place                |
| DDP  | Delivered Duty Paid               |
