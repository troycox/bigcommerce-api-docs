## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-optionsetsjson">GET  /optionsets.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-optionsetsjson">POST /optionsets.json </a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsetsidjson">GET /optionsets/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-optionsetsidjson">PUT /optionsets/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsetscountjson">GET /optionsets/count.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsetsjson">DELETE /optionsets.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsetsidjson">DELETE /optionsets/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>

## About
It is useful to understand the relationship between optionsets, options and products. The following diagram is meant to illustrate that.

![options relationship](https://github.com/bigcommerce/bigcommerce-api-docs/raw/master/images/options.png)
   
## Description
### GET optionsets.json
GET optionsets from a store

#### Request
These fields can be used to filter the query. By default, without any filters, the GET request returns all the optionsets.

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
     <td>name</td>
     <td>string</td>
     
     <td>The name of the optionset. Must be unique.</td>
   </tr>
   
   
  </tbody>
</table>

#### Response
List of optionsets
<pre>
[
  {
      "id": 2,
      "name": "MacBook",
      "options": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/optionsets/2/options.json",
          "resource": "/optionsets/2/options"
      }
  },
  {
      "id": 4,
      "name": "PixelSkin Case",
      "options": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/optionsets/4/options.json",
          "resource": "/optionsets/4/options"
      }
  },
  ...
]
</pre>

### POST optionsets.json
Create optionsets in a store

#### Request
The POST request allows following fields. Mandatory fields are styled blue.
<style type="text/css">
tr.mandatory {
  color: aliceblue;
}
</style>

<table class="table table-bordered ">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   
   <tr class="mandatory">
     <td>name</td>
     <td>string</td>
     
     <td>The name of the optionset. Must be unique.</td>
   </tr>
   
  </tbody>
</table>

#### Response
Creates a optionset
<pre>
{
    "id": 13,
    "name": "Xmen",
    "options": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/optionsets/13/options.json",
        "resource": "/optionsets/13/options"
    }
}
</pre>   

### GET optionsets/id.json
GET a optionset from a store

#### Request
This GET request does not take any parameters.

#### Response
optionset by ID
<pre>
{
    "id": 13,
    "name": "Xmen",
    "options": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/optionsets/13/options.json",
        "resource": "/optionsets/13/options"
    }
}
</pre>    

### PUT optionsets/id.json
UPDATE a optionset from a store

#### Request
This PUT request takes following parameters.
<table class="table table-bordered ">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   
   <tr >
     <td>name</td>
     <td>string</td>
     
     <td>The name of the optionset. Must be unique.</td>
   </tr>
   
   
  </tbody>
</table>

#### Response
A successful put udpates a optionset in the store 
<pre>
  {
      "id": 13,
      "name": "XmenO",
      "options": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/optionsets/13/options.json",
          "resource": "/optionsets/13/options"
      }
  }
</pre>
### GET optionsets/count.json
Get a total number of optionsets in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of optionsets in the store 
<pre>
  {
    "count": 10
  }
</pre>
Here are resources to delete optionsets. This is a potentially destrutive operation. Remember that you cannot recover deleted optionsets.

### DELETE optionsets.json
DELETE all optionsets

### DELETE optionsets/id.json
DELETE a optionset
