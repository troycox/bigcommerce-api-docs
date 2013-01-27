## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-ordersidshippingaddressesjson">GET orders/id/shippingaddresses.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidshippingaddressesidjson">GET orders/id/shippingaddresses/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidshippingaddressescountjson">GET orders/id/shippingaddresses/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET orders/id/shippingaddresses.json
GET shippingaddresses for an order

#### Request
There are no fields to filter for this request

#### Response
List of shippingaddresses
<pre>
[
    {
        "id": 15,
        "order_id": 114,
        "first_name": "Julie",
        "last_name": "Bishop",
        "company": "Yamia",
        "street_1": "988 Comanche Circle",
        "street_2": "",
        "city": "Cypress",
        "zip": "77426-2265",
        "country": "United States",
        "country_iso2": "US",
        "state": "Wyoming",
        "email": "",
        "phone": "5-(248)906-2014",
        "items_total": 1,
        "items_shipped": 0,
        "shipping_method": "None",
        "base_cost": "0.0000",
        "cost_ex_tax": "0.0000",
        "cost_inc_tax": "0.0000",
        "cost_tax": "0.0000",
        "cost_tax_class_id": 2,
        "base_handling_cost": "0.0000",
        "handling_cost_ex_tax": "0.0000",
        "handling_cost_inc_tax": "0.0000",
        "handling_cost_tax": "0.0000",
        "handling_cost_tax_class_id": 2,
        "shipping_zone_id": 1,
        "shipping_zone_name": "Default Zone"
    }
] 
</pre>


### GET orders/id/shippingaddresses/id.json
GET a shippingaddress for an order

#### Request
This GET request does not take any parameters.

#### Response
shippingaddress by ID
<pre>
{
    "id": 15,
    "order_id": 114,
    "first_name": "Julie",
    "last_name": "Bishop",
    "company": "Yamia",
    "street_1": "988 Comanche Circle",
    "street_2": "",
    "city": "Cypress",
    "zip": "77426-2265",
    "country": "United States",
    "country_iso2": "US",
    "state": "Wyoming",
    "email": "",
    "phone": "5-(248)906-2014",
    "items_total": 1,
    "items_shipped": 0,
    "shipping_method": "None",
    "base_cost": "0.0000",
    "cost_ex_tax": "0.0000",
    "cost_inc_tax": "0.0000",
    "cost_tax": "0.0000",
    "cost_tax_class_id": 2,
    "base_handling_cost": "0.0000",
    "handling_cost_ex_tax": "0.0000",
    "handling_cost_inc_tax": "0.0000",
    "handling_cost_tax": "0.0000",
    "handling_cost_tax_class_id": 2,
    "shipping_zone_id": 1,
    "shipping_zone_name": "Default Zone"
}
</pre>    


### GET orders/id/shippingaddresses/count.json
Get a total number of shippingaddresses in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of shippingaddresses in the store 
<pre>
  {
    "count": 10
  }
</pre>
