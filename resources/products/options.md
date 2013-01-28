## Resources
<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-productsidoptionsjson">GET products/id/options.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidoptionsidjson">GET products/id/options/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidoptionscountjson">GET products/id/options/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET products/id/options.json
GET options for an product

#### Request
There are no fields to filter for this request

#### Response
List of options
<pre>
[
    {
        "id": 13,
        "option_id": 8,
        "display_name": "Ipod Capacities",
        "sort_order": 0,
        "is_required": true
    },
    {
        "id": 14,
        "option_id": 9,
        "display_name": "Accessories",
        "sort_order": 1,
        "is_required": false
    }
]
</pre>


### GET products/id/options/id.json
GET a option for a product

#### Request
This GET request does not take any parameters.

#### Response
option by ID
<pre>
{
    "id": 14,
    "option_id": 9,
    "display_name": "Accessories",
    "sort_order": 1,
    "is_required": false
}
</pre>    


### GET products/id/options/count.json
Get a total number of options for the product

#### Request
This request does not take any parameters.

#### Response
Returns the number of options for the product 
<pre>
  {
    "count": 10
  }
</pre>
