## Resources

<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-ordersidshipmentsjson">GET /orders/id/shipments.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-ordersidshipmentsjson">POST /orders/id/shipments.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidshipmentsidjson">GET /orders/id/shipments/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-ordersidshipmentsidjson">PUT /orders/id/shipments/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidshipmentscountjson">GET /orders/id/shipments/count.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-ordersidshipmentsjson">DELETE /orders/id/shipments.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-ordersidshipmentsidjson">DELETE /orders/id/shipments/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description

### GET orders/id/shipments.json
GET all shipments for an order

#### Request
This GET request does not take any parameters.

#### Response
order by ID
<pre>
[
    {
        "id": 1,
        "order_id": 115,
        "customer_id": 0,
        "order_address_id": 16,
        "date_created": "Wed, 19 Dec 2012 17:17:10 +0000",
        "tracking_number": "111222333444",
        "shipping_method": "None",
        "comments": "A sample shipment for order 115",
        "billing_address": {
            "first_name": "Louise",
            "last_name": "Dean",
            "company": "Skiptube",
            "street_1": "147 Meadow Vale Way",
            "street_2": "",
            "city": "Fullerton",
            "state": "Rhode Island",
            "zip": "74674",
            "country": "United States",
            "country_iso2": "US",
            "phone": "7-(086)085-9448",
            "email": ""
        },
        "shipping_address": {
            "first_name": "Louise",
            "last_name": "Dean",
            "company": "Skiptube",
            "street_1": "147 Meadow Vale Way",
            "street_2": "",
            "city": "Fullerton",
            "state": "Rhode Island",
            "zip": "74674",
            "country": "United States",
            "country_iso2": "US",
            "phone": "7-(086)085-9448",
            "email": ""
        },
        "items": [
            {
                "order_product_id": 16,
                "product_id": 0,
                "quantity": 1
            }
        ]
    }
]
</pre> 

### POST orders/id/shipments.json
create an order shipment

#### Request
This request allows the following fields
<!-- do not change this. for rendering on the main site -->
<style type="text/css">
tr.mandatory {
  color: aliceblue;
}
</style>
<!-- style complete -->

<table class="table table-bordered">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   <tr >
     <td >tracking_number</td>
     <td>string</td>
     
     <td>Tracking number of the shipment</td>
   </tr>
   <tr >
     <td >order_date</td>
     <td>date</td>
     
     <td>Date when the order was placed</td>
   </tr>
   <tr >
     <td >comments</td>
     <td>text</td>
     
     <td>Comments the shipper wishes to add</td>
   </tr>
   <tr class="mandatory">
     <td >order_address_id</td>
     <td>int</td>
     
     <td>ID of the order address the shipment is associated with</td>
   </tr>
   <tr class="mandatory">
     <td >items</td>
     <td>object</td>
     
     <td>The items in the shipment. Is an object. Look at the items table. A sample value can be <code>[{"order_product_id":15,"quantity":2}]</code></td>
   </tr>
   
   
  </tbody>
</table>

#### Response
new shipment for an order
<pre>
{
    "id": 18,
    "order_id": 113,
    "customer_id": 0,
    "order_address_id": 14,
    "date_created": "Wed, 19 Dec 2012 19:49:15 +0000",
    "tracking_number": "",
    "shipping_method": "None",
    "comments": null,
    "billing_address": {
        "first_name": "Henry",
        "last_name": "Boyd",
        "company": "Kare",
        "street_1": "009 Corben Pass",
        "street_2": "",
        "city": "Laguna Niguel",
        "state": "New Hampshire",
        "zip": "57762",
        "country": "United States",
        "country_iso2": "US",
        "phone": "0-(245)121-8702",
        "email": ""
    },
    "shipping_address": {
        "first_name": "Henry",
        "last_name": "Boyd",
        "company": "Kare",
        "street_1": "009 Corben Pass",
        "street_2": "",
        "city": "Laguna Niguel",
        "state": "New Hampshire",
        "zip": "57762",
        "country": "United States",
        "country_iso2": "US",
        "phone": "0-(245)121-8702",
        "email": ""
    },
    "items": [
        {
            "order_product_id": 14,
            "product_id": 0,
            "quantity": 1
        }
    ]
}
</pre> 

If the quantity is invalid, you might see a response with status code 400.

<pre>
[
{
    "status": 400,
    "message": "The field 'quantity' is invalid.",
    "details": {
        "invalid_reason": "The quantity specified is greater than the quantity of the product that is available to ship.",
        "available_quantity": 0,
        "order_product_id": 14
    }
}
]
</pre>

### GET orders/id/shipments/id.json
GET a specific shipment


#### Request
This GET request does not take any parameters.


#### Response
order shipment by ID
<pre>
{
    "id": 12,
    "order_id": 114,
    "customer_id": 0,
    "order_address_id": 15,
    "date_created": "Wed, 19 Dec 2012 18:18:23 +0000",
    "tracking_number": "123-123-123",
    "shipping_method": "None",
    "comments": null,
    "billing_address": {
        "first_name": "Julie",
        "last_name": "Bishop",
        "company": "Yamia",
        "street_1": "988 Comanche Circle",
        "street_2": "",
        "city": "Cypress",
        "state": "Wyoming",
        "zip": "77426-2265",
        "country": "United States",
        "country_iso2": "US",
        "phone": "5-(248)906-2014",
        "email": ""
    },
    "shipping_address": {
        "first_name": "Julie",
        "last_name": "Bishop",
        "company": "Yamia",
        "street_1": "988 Comanche Circle",
        "street_2": "",
        "city": "Cypress",
        "state": "Wyoming",
        "zip": "77426-2265",
        "country": "United States",
        "country_iso2": "US",
        "phone": "5-(248)906-2014",
        "email": ""
    },
    "items": [
        {
            "order_product_id": 15,
            "product_id": 0,
            "quantity": 1
        }
    ]
}
</pre>

### PUT orders/id/shipments/id.json
update a specific shipment


#### Request
This PUT request takes following parameters.
<table class="table table-bordered">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   <tr >
     <td >tracking_number</td>
     <td>string</td>
     
     <td>Tracking number of the shipment</td>
   </tr>
   <tr >
     <td >order_date</td>
     <td>date</td>
     
     <td>Date when the order was placed</td>
   </tr>
   <tr >
     <td >comments</td>
     <td>text</td>
     
     <td>Comments the shipper wishes to add</td>
   </tr>
   <tr >
     <td >order_address_id</td>
     <td>int</td>
     
     <td>ID of the order address the shipment is associated with</td>
   </tr>
   
  </tbody>
</table>

#### Response
Update order shipment by ID
<pre>
{
    "id": 12,
    "order_id": 114,
    "customer_id": 0,
    "order_address_id": 16,
    "date_created": "Wed, 19 Dec 2012 18:18:23 +0000",
    "tracking_number": "fedex1245",
    "shipping_method": "None",
    "comments": null,
    "billing_address": {
        "first_name": "Julie",
        "last_name": "Bishop",
        "company": "Yamia",
        "street_1": "988 Comanche Circle",
        "street_2": "",
        "city": "Cypress",
        "state": "Wyoming",
        "zip": "77426-2265",
        "country": "United States",
        "country_iso2": "US",
        "phone": "5-(248)906-2014",
        "email": ""
    },
    "shipping_address": {
        "first_name": "Julie",
        "last_name": "Bishop",
        "company": "Yamia",
        "street_1": "988 Comanche Circle",
        "street_2": "",
        "city": "Cypress",
        "state": "Wyoming",
        "zip": "77426-2265",
        "country": "United States",
        "country_iso2": "US",
        "phone": "5-(248)906-2014",
        "email": ""
    },
    "items": [
        {
            "order_product_id": 15,
            "product_id": 0,
            "quantity": 1
        }
    ]
} 
</pre>

### GET orders/id/shipments/count.json
Get a total number of shipments in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of order shipments in the store 
<pre>
  {
    "count": 2
  }
</pre>

### DELETE orders/id/shipments.json
DELETE all order shipments

### DELETE orders/id/shipments/id.json
DELETE an order shipment
