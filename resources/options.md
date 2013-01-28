## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-optionsjson">GET  /options.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-optionsjson">POST /options.json </a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsidjson">GET /options/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-optionsidjson">PUT /options/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionscountjson">GET /options/count.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsjson">DELETE /options.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-optionsidjson">DELETE /options/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET options.json
GET options from a store

#### Request
These fields can be used to filter the query. By default, without any filters, the GET request returns all the options.

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
     
     <td>The name of the option. Must be unique.</td>
   </tr>
   <tr>
     <td>display_name</td>
     <td>string</td>
     
     <td>Friendly name displayed to the customer</td>
   </tr>
   <tr>
     <td>type</td>
     <td>enum</td>
     
     <td>The type of option (N, D, MT, C, F, T, RB, RT, S, P, PI, CS)
      <ul>
        <li> N - Numbers only text </li>
        <li> D - Date </li>
        <li> MT - Multiline text </li>
        <li> C - Checkbox </li>
        <li> F - File </li>
        <li> T - Text </li>
        <li> RB - Radio list </li>
        <li> RT - Rectangle list </li>
        <li> S - Select box </li>
        <li> P - Product list </li>
        <li> PI - Product list with images </li>
        <li> CS - Swatch </li>
      </ul>
     </td>
   </tr>
   
  </tbody>
</table>

#### Response
List of options
<pre>
[
  {
      "id": 3,
      "name": "Colors",
      "display_name": "Color",
      "type": "CS",
      "values": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/3/values.json",
          "resource": "/options/3/values"
      }
  },
  {
      "id": 4,
      "name": "Screen Sizes",
      "display_name": "Screen Sizes",
      "type": "RT",
      "values": {
          "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/4/values.json",
          "resource": "/options/4/values"
      }
  },
  ...
]
</pre>

### POST options.json
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
     <td>name</td>
     <td>string</td>
     
     <td>The name of the option. Must be unique.</td>
   </tr>
   <tr>
     <td>display_name</td>
     <td>string</td>
     
     <td>Friendly name displayed to the customer</td>
   </tr>
   <tr class="mandatory">
     <td>type</td>
     <td>enum</td>
     
     <td>The type of option (N, D, MT, C, F, T, RB, RT, S, P, PI, CS)
      <ul>
        <li> N - Numbers only text </li>
        <li> D - Date </li>
        <li> MT - Multiline text </li>
        <li> C - Checkbox </li>
        <li> F - File </li>
        <li> T - Text </li>
        <li> RB - Radio list </li>
        <li> RT - Rectangle list </li>
        <li> S - Select box </li>
        <li> P - Product list </li>
        <li> PI - Product list with images </li>
        <li> CS - Swatch </li>
      </ul>
     </td>
   </tr>
   
  </tbody>
</table>

#### Response
Creates an option
<pre>
{
    "id": 18,
    "name": "Xmen toys",
    "display_name": "xmen toys",
    "type": "T",
    "values": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/18/values.json",
        "resource": "/options/18/values"
    }
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
    "id": 3,
    "name": "Colors",
    "display_name": "Color",
    "type": "CS",
    "values": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/3/values.json",
        "resource": "/options/3/values"
    }
}
</pre>    

### <a id="options_r4"></a>PUT options/id.json
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
     <td>name</td>
     <td>string</td>
     
     <td>The name of the option. Must be unique.</td>
   </tr>
   <tr>
     <td>display_name</td>
     <td>string</td>
     
     <td>Friendly name displayed to the customer</td>
   </tr>
   <tr >
     <td>type</td>
     <td>enum</td>
     
     <td>The type of option (N, D, MT, C, F, T, RB, RT, S, P, PI, CS)
      <ul>
        <li> N - Numbers only text </li>
        <li> D - Date </li>
        <li> MT - Multiline text </li>
        <li> C - Checkbox </li>
        <li> F - File </li>
        <li> T - Text </li>
        <li> RB - Radio list </li>
        <li> RT - Rectangle list </li>
        <li> S - Select box </li>
        <li> P - Product list </li>
        <li> PI - Product list with images </li>
        <li> CS - Swatch </li>
      </ul>
     </td>
   </tr>
   
  </tbody>
</table>

#### Response
A successful put udpates a option in the store 
<pre>
{
    "id": 18,
    "name": "Xmen toys",
    "display_name": "xmen extreme toys",
    "type": "T",
    "values": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/options/18/values.json",
        "resource": "/options/18/values"
    }
}
</pre>
### GET options/count.json
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

### DELETE options.json
DELETE all options

### DELETE options/id.json
DELETE a option
