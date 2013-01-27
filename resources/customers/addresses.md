## Resources

<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-customersidaddressesidjson">GET /customers/id/addresses/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-customersaddressesidjson">GET /customers/addresses/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-customersidaddressescountjson">GET /customers/id/addresses/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description

### GET customers/id/addresses/id.json
GET a address by ID

#### Request
This GET request does not take any parameters.

#### Response
customer by ID
<pre>
[
    {
        "id": 1,
        "customer_id": 10,
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "country_iso2": "US",
        "phone": ""
    }
]
</pre> 

### GET customers/addresses/id.json
GET a specific address

#### Request
This GET request does not take any parameters.

#### Response
customer address by ID
<pre>
{
    "id": 1,
    "customer_id": 10,
    "first_name": "Trisha",
    "last_name": "McLaughlin",
    "company": "",
    "street_1": "12345 W Anderson Ln",
    "street_2": "",
    "city": "Austin",
    "state": "Texas",
    "zip": "78757",
    "country": "United States",
    "country_iso2": "US",
    "phone": ""
}
</pre>    


### GET customers/id/addresses/count.json
Get a total number of addresses in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of addresses in the store 
<pre>
  {
    "count": 2
  }
</pre>
