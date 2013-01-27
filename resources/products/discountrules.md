## Resources
<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-productsiddiscountrulesjson">GET products/id/discountrules.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsiddiscountrulesidjson">GET products/id/discountrules/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsiddiscountrulescountjson">GET products/id/discountrules/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET products/id/discountrules.json
GET discountrules for an product

#### Request
There are no fields to filter for this request

#### Response
List of discountrules
<pre>
[
    {
        "id": "1",
        "product_id": 30,
        "min": 100,
        "max": 500,
        "type": "price",
        "type_value": "2.0000"
    }
]   
</pre>


### GET products/id/discountrules/id.json
GET a discountrule from a store

#### Request
This GET request does not take any parameters.

#### Response
discountrule by ID
<pre>
{
    "id": "1",
    "product_id": 30,
    "min": 100,
    "max": 500,
    "type": "price",
    "type_value": "2.0000"
}
</pre>    


### GET products/id/discountrules/count.json
Get a total number of discountrules in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of discountrules in the store 
<pre>
  {
    "count": 10
  }
</pre>
