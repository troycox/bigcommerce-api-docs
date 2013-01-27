## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-orderstatusesjson">GET  /orderstatuses.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-orderstatusesidjson">GET /orderstatuses/id.json</a></td>
     
   </tr>
   
   
 </tbody>
</table>
   
## Description
### GET orderstatuses.json
GET orderstatuses from a store

#### Request
There are no filtering fields for this request



#### Response
List of orderstatuses
<pre>
[
    {
        "id": 0,
        "name": "Incomplete",
        "order": 0
    },
    {
        "id": "1",
        "name": "Pending",
        "order": "1"
    },
    {
        "id": "2",
        "name": "Shipped",
        "order": "8"
    },
    {
        "id": "3",
        "name": "Partially Shipped",
        "order": "6"
    },
    {
        "id": "4",
        "name": "Refunded",
        "order": "11"
    },
    {
        "id": "5",
        "name": "Cancelled",
        "order": "9"
    },
    {
        "id": "6",
        "name": "Declined",
        "order": "10"
    },
    {
        "id": "7",
        "name": "Awaiting Payment",
        "order": "2"
    },
    {
        "id": "8",
        "name": "Awaiting Pickup",
        "order": "5"
    },
    {
        "id": "9",
        "name": "Awaiting Shipment",
        "order": "4"
    },
    {
        "id": "10",
        "name": "Completed",
        "order": "7"
    },
    {
        "id": "11",
        "name": "Awaiting Fulfillment",
        "order": "3"
    },
    {
        "id": "12",
        "name": "Manual Verification Required",
        "order": "12"
    }
]  
</pre>


### GET orderstatuses/id.json
GET a orderstatus from a store

#### Request
This GET request does not take any parameters.

#### Response
orderstatus by ID
<pre>
{
    "id": "12",
    "name": "Manual Verification Required",
    "order": "12"
}
</pre>    


