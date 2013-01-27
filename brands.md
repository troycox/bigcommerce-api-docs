## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#brands_r1">GET  /brands.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r2">POST /brands.json </a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r3">GET /brands/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r4">PUT /brands/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r5">GET /brands/count.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r6">DELETE /brands.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r7">DELETE /brands/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### <a id="brands_r1"></a>GET brands.json
GET brands from a store

#### Request
These fields can be used to filter the query. By default, without any filters, the GET request returns all the brands.

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
     <td>string(255)</td>
     
     <td>The name of the brand. Must be unique.</td>
   </tr>
   
 </tbody>
</table>

#### Response
List of brands
  [
      {
      "id": 1,
      "name": "Apple",
      "page_title": "",
      "meta_keywords": "",
      "meta_description": "",
      "image_file": "",
      "search_keywords": ""
    },
    {
    "id": 2,
    "name": "Microsoft",
    "page_title": "",
    "meta_keywords": "",
    "meta_description": "",
    "image_file": "",
    "search_keywords": ""
  }
  ]
   

### <a id="brands_r2"></a>POST brands.json
Create brands in a store

#### Request
The POST request allows following fields. Mandatory fields are styled blue.
<style>
tr.mandatory {
  color: aliceblue;
}
</style>

<table class="table table-bordered">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
 </thead>
 <tbody>
   
   <tr class="mandatory">
     <td >name</td>
     <td>string</td>
     
     <td>The name of the brand. Must be unique.</td>
   </tr>
   <tr>
     <td>page_title</td>
     <td>string</td>
     
     <td>The title shown in the browser while viewing the brand</td>
   </tr>
   <tr>
     <td>meta_keywords</td>
     <td>text</td>
     
     <td>Comma separated list of meta keywords to include in the HTML</td>
   </tr>
   <tr>
     <td>meta_description</td>
     <td>text</td>
     
     <td>A meta description to include</td>
   </tr>
   <tr class="mandatory">
     <td >image_file</td>
     <td>string</td>
     
     <td>A valid image</td>
   </tr>
   <tr>
     <td>search_keywords</td>
     <td>string</td>
     
     <td>A comma separated list of keywords that can be used to locate this brand</td>
   </tr>
   
 </tbody>
</table>

#### Response
Creates a brand

  {
  "id": 10,
  "name": "Xmen",
  "page_title": "X men brand",
  "meta_keywords": null,
  "meta_description": null,
  "image_file": "t/apirmzk0a__43675.jpg",
  "search_keywords": "xmen, awesomeness"
  }
   

### <a id="brands_r3"></a>GET brands/id.json
GET a brand from a store

#### Request
This GET request does not take any parameters.

#### Response
Brand by ID

  {
    "id": 1,
    "name": "Apple",
    "page_title": "",
    "meta_keywords": "",
    "meta_description": "",
    "image_file": "",
    "search_keywords": ""
  }
    

### <a id="brands_r4"></a>PUT brands/id.json
UPDATE a brand from a store

#### Request
This PUT request does not take any parameters.
<table class="table table-bordered">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
 </thead>
 <tbody>
   
<tr class="">
  <td >name</td>
  <td>string</td>

  <td>The name of the brand. Must be unique.</td>
</tr>
<tr>
  <td>page_title</td>
  <td>string</td>
  <td>The title shown in the browser while viewing the brand</td>
</tr>
<tr>
  <td>meta_keywords</td>
  <td>text</td>
  <td>Comma separated list of meta keywords to include in the HTML</td>
</tr>
<tr>
  <td>meta_description</td>
  <td>text</td>
  <td>A meta description to include</td>
</tr>
<tr class="">
  <td >image_file</td>
  <td>string</td>
  <td>A valid image</td>
</tr>
<tr>
  <td>search_keywords</td>
  <td>string</td>
  <td>A comma separated list of keywords that can be used to locate this brand</td>
</tr>
 
</tbody>
</table>

#### Response
A successful put udpates a brand in the store 

  {
    "id": 10,
    "name": "Xmen",
    "page_title": "X men brand",
    "meta_keywords": null,
    "meta_description": null,
    "image_file": "t/apirmzk0a__43675.jpg",
    "search_keywords": "xmen, awesomeness"
  }

### <a id="brands_r5"></a>GET brands/count.json
Get a total number of brands in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of brands in the store 

  {
    "count": 10
  }

Here are resources to delete brands. This is a potentially destrutive operation. Remember that you cannot recover deleted brands.

### <a id="brands_r6"></a>DELETE brands.json
DELETE all brands

### <a id="brands_r7"></a>DELETE brands/id.json
DELETE a brand
