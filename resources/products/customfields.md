## Resources
<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-productsidcustomfieldsjson">GET products/id/customfields.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidcustomfieldsidjson">GET products/id/customfields/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidcustomfieldscountjson">GET products/id/customfields/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET products/id/customfields.json
GET customfields for an product

#### Request
There are no fields to filter for this request

#### Response
List of customfields
<pre>
[
    {
        "id": 2,
        "product_id": 30,
        "name": "Toy manufactured in",
        "text": "USA"
    }
]  
</pre>


### GET products/id/customfields/id.json
GET a customfield from a store

#### Request
This GET request does not take any parameters.

#### Response
customfield by ID
<pre>
{
    "id": 2,
    "product_id": 30,
    "name": "Toy manufactured in",
    "text": "USA"
}
</pre>    


### GET products/id/customfields/count.json
Get a total number of customfields in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of customfields in the store 
<pre>
  {
    "count": 10
  }
</pre>
