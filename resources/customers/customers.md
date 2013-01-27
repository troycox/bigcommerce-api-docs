## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-customersjson">GET  /customers.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-customersidjson">GET /customers/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-customerscountjson">GET /customers/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET customers.json
GET customers from a store

#### Request
These fields can be used to filter the query. By default, without any filters, the GET request returns all the customers.

<table class="table table-bordered ">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   <tr>
     <td>min_id</td>
     <td>int</td>
     
     <td>minimum ID of the customer</td>
   </tr>

   <tr>
     <td>max_id</td>
     <td>int</td>
     
     <td>maximum ID of the customer</td>
   </tr>

   <tr>
     <td>first_name</td>
     <td>string</td>
     
     <td>First name of customer</td>
   </tr>

   <tr>
     <td>last_name</td>
     <td>string</td>
     
     <td>Last name of customer</td>
   </tr>

   <tr>
     <td>company</td>
     <td>string</td>
     
     <td>Company customer is part of</td>
   </tr>
   <tr>
     <td>email</td>
     <td>string</td>
     
     <td>Email address of the customer</td>
   </tr>
   <tr>
     <td>phone</td>
     <td>string</td>
     
     <td>Phone number of customer</td>
   </tr>

   <tr>
     <td>store_credit</td>
     <td>decimal</td>
     
     <td>The amount of credit the customer has</td>
   </tr>

   <tr>
     <td>customer_group_id</td>
     <td>int</td>
     
     <td>The group the customer belongs to</td>
   </tr>
   <tr>
     <td>min_date</td>
     <td>date</td>
     
     <td>The minimum creation date of the customer</td>
   </tr>
   <tr>
     <td>max_date</td>
     <td>date</td>
     
     <td>The maximumn creation date of the customer</td>
   </tr>
   
   
  </tbody>
</table>

#### Response
List of customers
<pre>
[
  {
      "id": 1,
      "company": "",
      "first_name": "Random ",
      "last_name": "Joe Bob",
      "email": "random.joebob@example.com",
      "phone": "252-101-2010",
      "date_created": "Tue, 13 Nov 2012 21:16:41 +0000",
      "date_modified": "Tue, 13 Nov 2012 21:16:41 +0000",
      "store_credit": "0.0000",
      "registration_ip_address": "50.58.18.2",
      "customer_group_id": 0,
      "notes": "",
      "addresses": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/customers/1/addresses.json",
          "resource": "/customers/1/addresses"
      }
  },
  {
      "id": 2,
      "company": "",
      "first_name": "Test",
      "last_name": "Customer",
      "email": "foo@randomcustomer.com",
      "phone": "",
      "date_created": "Wed, 14 Nov 2012 04:47:28 +0000",
      "date_modified": "Wed, 14 Nov 2012 04:47:28 +0000",
      "store_credit": "0.0000",
      "registration_ip_address": "99.191.105.74",
      "customer_group_id": 0,
      "notes": "",
      "addresses": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/customers/2/addresses.json",
          "resource": "/customers/2/addresses"
      }
  }
  ...
]
</pre>


### GET customers/id.json
GET a customer from a store

#### Request
This GET request does not take any parameters.

#### Response
customer by ID
<pre>
{
    "id": 1,
    "company": "",
    "first_name": "Random ",
    "last_name": "Joe Bob",
    "email": "random.joebob@example.com",
    "phone": "252-101-2010",
    "date_created": "Tue, 13 Nov 2012 21:16:41 +0000",
    "date_modified": "Tue, 13 Nov 2012 21:16:41 +0000",
    "store_credit": "0.0000",
    "registration_ip_address": "50.58.18.2",
    "customer_group_id": 0,
    "notes": "",
    "addresses": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/customers/1/addresses.json",
        "resource": "/customers/1/addresses"
    }
}
</pre>    


### GET customers/count.json
Get a total number of customers in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of customers in the store 
<pre>
  {
    "count": 10
  }
</pre>
