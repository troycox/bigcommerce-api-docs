## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-optionsetoptionsjson">GET  optionsets/options.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-optionsetoptionsjson">POST optionsets/options.json </a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsetoptionsidjson">GET optionsets/options/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-optionsetoptionsidjson">PUT optionsets/id/options/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsetoptionscountjson">GET optionsets/options/count.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsetoptionsjson">DELETE optionsets/options.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsetoptionsidjson">DELETE /optionsets/options/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET optionsets/options.json
GET options for an option set

#### Request

Filtering is not supported on the option set options resource.

#### Response
List of options
<pre>
[
  {
      "id": 4,
      "option_id": 5,
      "option_set_id": 2,
      "display_name": "Clock Speeds (CPU)",
      "sort_order": 0,
      "is_required": true,
      "option": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/5.json",
          "resource": "/options/5"
      }
  },
  {
      "id": 5,
      "option_id": 6,
      "option_set_id": 2,
      "display_name": "HDD Sizes",
      "sort_order": 1,
      "is_required": true,
      "option": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/6.json",
          "resource": "/options/6"
      }
  },
  ...
]
</pre>

### POST optionsets/options.json
Create options in a store

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
     <td>option_id</td>
     <td>int</td>
     
     <td>The id of the option this optionset refers to</td>
   </tr>
   
   <tr >
     <td>display_name</td>
     <td>string</td>
     
     <td>The friendly name used for this optionset</td>
   </tr>

   <tr >
     <td>sort_order</td>
     <td>integer</td>
     
     <td>The order in which the option is displayed on the product page</td>
   </tr>

   <tr >
     <td>is_required</td>
     <td>boolean</td>
     
     <td>Specifies whether customer is required to enter value for this option before they can add the product to their cart</td>
   </tr>
   
  </tbody>
</table>

#### Response
Creates an option
<pre>
{
    "id": 69,
    "option_id": 10,
    "label": "appearance",
    "sort_order": 0,
    "value": "appearance"
}
</pre>   

### GET options/id.json
GET a option from a store

#### Request
This GET request does not take any parameters.

#### Response
option by ID
<pre>
{
      "id": 4,
      "option_id": 5,
      "option_set_id": 2,
      "display_name": "Clock Speeds (CPU)",
      "sort_order": 0,
      "is_required": true,
      "option": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/5.json",
          "resource": "/options/5"
      }
}
</pre>    

### PUT optionsets/options/id.json
UPDATE a option from a store

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
     <td>display_name</td>
     <td>string</td>
     
     <td>The friendly name used for this optionset</td>
   </tr>

   <tr >
     <td>sort_order</td>
     <td>integer</td>
     
     <td>The order in which the option is displayed on the product page</td>
   </tr>

   <tr >
     <td>is_required</td>
     <td>boolean</td>
     
     <td>Specifies whether customer is required to enter value for this option before they can add the product to their cart</td>
   </tr>
   
  </tbody>
</table>

#### Response
A successful put udpates a option in the store 
<pre>
{
    "id": 69,
    "option_id": 10,
    "label": "appearance",
    "sort_order": 0,
    "value": "appearance"
}
</pre>
### GET optionsets/options/count.json
Get a total number of options in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of options in the store 
<pre>
  {
    "count": 10
  }
</pre>
Here are resources to delete options. This is a potentially destrutive operation. Remember that you cannot recover deleted options.

### DELETE optionsets/options.json
DELETE all options

### DELETE optionsets/options/id.json
DELETE a option
