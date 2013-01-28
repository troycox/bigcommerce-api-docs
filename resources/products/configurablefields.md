## Resources
<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-productsidconfigurablefieldsjson">GET products/id/configurablefields.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidconfigurablefieldsidjson">GET products/id/configurablefields/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidconfigurablefieldscountjson">GET products/id/configurablefields/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET products/id/configurablefields.json
GET configurablefields for an product

#### Request
There are no fields to filter for this request

#### Response
List of configurablefields
<pre>
[
    {
        "id": 1,
        "product_id": 30,
        "name": "Manufacturing Country",
        "type": "T",
        "allowed_file_types": "",
        "max_size": 0,
        "select_options": "",
        "is_required": true,
        "sort_order": 1
    }
] 
</pre>


### GET products/id/configurablefields/id.json
GET a configurablefield from a store

#### Request
This GET request does not take any parameters.

#### Response
configurablefield by ID
<pre>
{
    "id": 1,
    "product_id": 30,
    "name": "Manufacturing Country",
    "type": "T",
    "allowed_file_types": "",
    "max_size": 0,
    "select_options": "",
    "is_required": true,
    "sort_order": 1
}
</pre>    


### GET products/id/configurablefields/count.json
Get a total number of configurablefields in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of configurablefields in the store 
<pre>
  {
    "count": 10
  }
</pre>
