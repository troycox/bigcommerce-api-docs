## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-couponsjson">GET  /shipping/methods.json</a></td>
   </tr>
</tbody>
</table>

## Description

### GET /shipping/methods.json

GET configured shipping methods from a store

#### Request

These fields can be used to filter the query. By default, without any filters, the GET request returns all the configured shipping methods.

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
     <td>id</td>
     <td>integer</td>
     <td>shipping method id</td>
   </tr>
   <tr>
     <td>name</td>
     <td>string</td>
     <td>display name for shipping method</td>
   </tr>
   <tr>
     <td>method_name</td>
     <td>string</td>
     <td>shipping method name</td>
   </tr>
   <tr>
     <td>min_id</td>
     <td>string</td>
     <td>methods with id greater than min_id</td>
   </tr>
   <tr>
     <td>max_id</td>
     <td>string</td>
     <td>methods with id less than max_id</td>
   </tr>
  </tbody>
</table>


#### Response
List of shipping methods

<pre>
[{
    "id": 1,
    "name": "Australia Post",
    "method_name": "shipping_auspost"
}]
</pre>

### GET /shipping/methods/id.json
GET a shipping method from a store

#### Request
This GET request does not take any parameters.

#### Response
shipping method by ID

<pre>
[{
    "id": 1,
    "name": "Australia Post",
    "method_name": "shipping_auspost"
}]
</pre>

