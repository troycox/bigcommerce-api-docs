## Resources

<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-optionsidvaluesjson">GET /options/id/values.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-optionsidvaluesjson">POST /options/id/values.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsvaluesidjson">GET /options/values/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-optionsidvaluescountjson">GET /options/id/values/count.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-optionsvaluesjson">DELETE /options/values.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-optionsvaluesidjson">DELETE /options/values/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description

### GET options/id/values.json
GET a value by ID

#### Request
This GET request does not take any parameters.

#### Response
option by ID
<pre>
[
  {
      "id": 7,
      "option_id": 3,
      "label": "Silver",
      "sort_order": 1,
      "value": "#cccccc"
  },
  {
      "id": 8,
      "option_id": 3,
      "label": "Black",
      "sort_order": 2,
      "value": "#000000"
  },
  ...
]
</pre> 

### POST options/id/values.json
create an option value

#### Request
This request allows the following fields
<!-- do not change this. for rendering on the main site -->
<style type="text/css">
tr.mandatory {
  color: aliceblue;
}
</style>
<!-- style complete -->

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
     <td>label</td>
     <td>string</td>
     
     <td>The name of the label</td>
   </tr>
   
   <tr class="mandatory">
     <td>value</td>
     <td>variable</td>
     
     <td>Value generally depends on option type
      <ul>
        <li> RB - String to be displayed to the customer </li>
        <li> RT - String to be displayed to the customer </li>
        <li> S - String to be displayed to the customer </li>
        <li> P - Product ID </li>
        <li> PI - Product ID </li>
        <li> CS - 
          <p> Hexadecimal color code to create a color option (#0f0000) </p>
          <p> A CSS 2.1 color name eg blue </p>
          <p> Up to three hexadeciaml color codes or color names spearated by a pipe #FF0000|lime|#0000FF </p>
          <p> URL to an image to create a texture http://store.com/images/myimg.png </p>
          <p> Nam eof an image file in the store's import folder eg myimg.png </p>
        </li>
      </ul>
     </td>
   </tr>
   
  </tbody>
</table>

#### Response
option by ID
<pre>
{
  "id": 68,
  "option_id": 3,
  "label": "white",
  "sort_order": 0,
  "value": "#FFFFFF"
}
</pre> 

### GET options/values/id.json
GET a specific value


#### Request
This GET request does not take any parameters.


#### Response
option value by ID
<pre>
{
    "id": 9,
    "option_id": 3,
    "label": "Purple",
    "sort_order": 3,
    "value": "#700170"
}
</pre>

### PUT options/values/id.json
update a specific value


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
     <td>label</td>
     <td>string</td>
     
     <td>The name of the label</td>
   </tr>
   
   <tr >
     <td>value</td>
     <td>variable</td>
     
     <td>Value generally depends on option type
      <ul>
        <li> RB - String to be displayed to the customer </li>
        <li> RT - String to be displayed to the customer </li>
        <li> S - String to be displayed to the customer </li>
        <li> P - Product ID </li>
        <li> PI - Product ID </li>
        <li> CS - 
          <p> Hexadecimal color code to create a color option (#0f0000) </p>
          <p> A CSS 2.1 color name eg blue </p>
          <p> Up to three hexadeciaml color codes or color names spearated by a pipe #FF0000|lime|#0000FF </p>
          <p> URL to an image to create a texture http://store.com/images/myimg.png </p>
          <p> Nam eof an image file in the store's import folder eg myimg.png </p>
        </li>
      </ul>
     </td>
   </tr>
   
  </tbody>
</table>

#### Response
Update option value by ID
<pre>
{
  "id": 68,
  "option_id": 3,
  "label": "whitish",
  "sort_order": 0,
  "value": "#FFFFEF"
}
</pre>

### GET options/id/values/count.json
Get a total number of values in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of option values in the store 
<pre>
  {
    "count": 2
  }
</pre>

### DELETE options/values.json
DELETE all option values

### DELETE options/values/id.json
DELETE an option value