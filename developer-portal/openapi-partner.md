This API represents your business partner (which are either customer, supplier or both roles simultaneously). It lets you get the information about the contact and it will act as a basis on whom the document will be referred to.

<H2 fontWeight="{400}">Partner Behavior</H2>

Please bear in mind as well that the main attribute that will be unique and act as identifier for each partners are:

    1. ID
    2. Phone number
    3. Email address

Therefore, it is strongly recommended to check whether there is duplicate on the phone number and email address or not before creating or updating the partners.
Use id as the reference to your existing Customer. If no Partner (Customer or Supplier) with the id exists, a new one will be created when you are calling the API.

**CAUTION :** If a partner already exists with the id, its metadata will be updated with the one in the response body.