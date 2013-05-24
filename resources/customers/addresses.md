## About
This endpoint provides you the ability to manage a customers *shipping* addresses.

## Resources

<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-customers-address">GET /customers/{id}/addresses/{id}</a></td>
   </tr>
   <tr>
     <td><a href="#get-customer-address">GET /customers/addresses/{id}</a></td>
   </tr>
   <tr>
     <td><a href="#get-customer-address-count">GET /customers/{id}/addresses/count</a></td>
   </tr>

   <tr>
     <td><a href="#create-customer-address">POST /customers/{id}/addresses</a></td>
   </tr>

   <tr>
     <td><a href="#update-customer-address">PUT /customers/{id}/addresses/{id}</a></td>
   </tr>

   <tr>
     <td><a href="#delete-customer-address">DELETE /customers/{id}/addresses/{id}</a></td>
   </tr>
   <tr>
     <td><a href="#delete-customer-addresses">DELETE /customers/{id}/addresses</a></td>
   </tr>
   
 </tbody>
</table>
   
## Description

### Get Customers Address
GET a address by customer ID and address ID : /customers/{id}/addresses/{id}

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

### Get Customer Address
GET a specific address : /customers/addresses/{id}

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


### Get Customer Address Count
Get a total number of addresses in the store : /customers/{id}/addresses/count

#### Request
This request does not take any parameters.

#### Response
Returns the number of addresses in the store 
<pre>
  {
    "count": 2
  }
</pre>

### Create Customer Address
Create a shipping address for a customer : /customers/{id}/addresses

#### Request
<pre>
    {
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "phone": ""
    }
</pre>

#### Response
<pre>
    {
        "id": 1,
        "customer_id": 1,
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

### Update Customer Address
Update a customers shipping address : /customers/{id}/addresses/{id}

#### Request
<pre>
    {
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "phone": ""
    }
</pre>

#### Response
<pre>
    {
        "id": 1,
        "customer_id": 1,
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

### Delete Customer Address
Delete a customers shipping address : /customers/{id}/addresses/{id}

#### Request
No parameters can be sent to a delete.

#### Response
A status code of 204 is returned with an empty body.

### Delete Customer Addresses
Delete all shipping addresses for a customer : /customers/{id}/addresses

#### Request
No parameters can be sent to a delete.

#### Response
A status code of 204 is returned with an empty body.

