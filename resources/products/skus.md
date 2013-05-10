## Resources

<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-productsidskusjson">GET /products/id/skus.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-productsidskusjson">POST /products/id/skus.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidskusidjson">GET /products/id/skus/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-productsidskusidjson">PUT /products/id/skus/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidskuscountjson">GET /products/id/skus/count.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-productsidskusjson">DELETE /products/id/skus.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-productsidskusidjson">DELETE /products/id/skus/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description

### GET products/id/skus.json
GET all skus for an product

#### Request
This GET request returns all the SKUs by default. It can be filtered by following fields.

<table class="table table-bordered">
  <thead>
   <tr>
     <th style="width: 100px;">Field</th>
     <th style="width: 50px;">Type</th>
     <th>description</th>
   </tr>
  </thead>
  <tbody>
   <tr >
     <td >min_id</td>
     <td>integer</td>
     
     <td>The min sku ID</td>
   </tr>
   <tr >
     <td >max_id</td>
     <td>integer</td>
     
     <td>The max sku ID</td>
   </tr>
   <tr >
     <td >sku</td>
     <td>string</td>
     
     <td>The unique sku</td>
   </tr>
   <tr >
     <td >upc</td>
     <td>string</td>
     
     <td>The upc for the product combination</td>
   </tr>
   <tr >
     <td >inventory_level</td>
     <td>int</td>
     
     <td>The inventory level for the product</td>
   </tr>
   <tr >
     <td >inventory_warning_level</td>
     <td>int</td>
     
     <td>The inventory warning level for the product</td>
   </tr>
   <tr >
     <td >bin_picking_number</td>
     <td>string</td>
     
     <td>The BIN picking number</td>
   </tr>
   
   <tr >
     <td >min_inventory_level</td>
     <td>integer</td>
     
     <td>The min inventory level</td>
   </tr>
   <tr >
     <td >max_inventory_level</td>
     <td>integer</td>
     
     <td>The max inventory level</td>
   </tr>
   
  </tbody>
</table>

#### Response
sku by ID
<pre>
[
    {
        "id": 1,
        "product_id": 5,
        "sku": "MB-1",
        "cost_price": "0.0000",
        "upc": "",
        "inventory_level": 0,
        "inventory_warning_level": 0,
        "bin_picking_number": "",
        "options": [
            {
                "product_option_id": 15,
                "option_value_id": 17
            },
            {
                "product_option_id": 16,
                "option_value_id": 28
            }
        ]
    },
    {
        "id": 2,
        "product_id": 5,
        "sku": "MB-2",
        "cost_price": "0.0000",
        "upc": "",
        "inventory_level": 0,
        "inventory_warning_level": 0,
        "bin_picking_number": "",
        "options": [
            {
                "product_option_id": 15,
                "option_value_id": 18
            },
            {
                "product_option_id": 16,
                "option_value_id": 26
            }
        ]
    },
    ...
]
</pre> 

### POST products/id/skus.json
create a product sku

#### Request
This request allows the following fields
<!-- do not change this. for rendering on the main site -->
<style type="text/css">
tr.mandatory {
  color: aliceblue;
}
</style>
<!-- style complete -->

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
     <td >sku</td>
     <td>string</td>
     
     <td>The unique sku</td>
   </tr>
   <tr >
     <td >upc</td>
     <td>string</td>
     
     <td>The upc for the product combination</td>
   </tr>
   <tr >
     <td >cost_price</td>
     <td>decimal</td>
     
     <td>The cost price of the product</td>
   </tr>
   <tr >
     <td >inventory_level</td>
     <td>int</td>
     
     <td>The inventory level for the product</td>
   </tr>
   <tr >
     <td >inventory_warning_level</td>
     <td>int</td>
     
     <td>The inventory warning level for the product</td>
   </tr>
   <tr >
     <td >bin_picking_number</td>
     <td>string</td>
     
     <td>The BIN picking number</td>
   </tr>
   <tr class="mandatory">
     <td >options</td>
     <td>object</td>
     
     <td>This is an object {"product_option_id": int, "option_value_id":int}</td>
   </tr>
   
  </tbody>
</table>

#### Response
new sku for an product
<pre>
{
    "id": 5,
    "product_id": 7,
    "sku": "MBA-1atest",
    "cost_price": "0.0000",
    "upc": "",
    "inventory_level": 0,
    "inventory_warning_level": 0,
    "bin_picking_number": "",
    "options": [
        {
            "product_option_id": 20,
            "option_value_id": 51
        }
    ]
}
</pre> 


### GET products/id/skus/id.json
GET a specific sku


#### Request
This GET request does not take any parameters.


#### Response
product sku by ID
<pre>
{
    "id": 5,
    "product_id": 7,
    "sku": "MBA-1atest",
    "cost_price": "0.0000",
    "upc": "",
    "inventory_level": 0,
    "inventory_warning_level": 0,
    "bin_picking_number": "",
    "options": [
        {
            "product_option_id": 20,
            "option_value_id": 51
        }
    ]
}
</pre>

### PUT products/id/skus/id.json
update a specific sku


#### Request
This PUT request takes following parameters.
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
     <td >sku</td>
     <td>string</td>
     
     <td>The unique sku</td>
   </tr>
   <tr >
     <td >upc</td>
     <td>string</td>
     
     <td>The upc for the product combination</td>
   </tr>
   <tr >
     <td >cost_price</td>
     <td>decimal</td>
     
     <td>The cost price of the product</td>
   </tr>
   <tr >
     <td >inventory_level</td>
     <td>int</td>
     
     <td>The inventory level for the product</td>
   </tr>
   <tr >
     <td >inventory_warning_level</td>
     <td>int</td>
     
     <td>The inventory warning level for the product</td>
   </tr>
   <tr >
     <td >bin_picking_number</td>
     <td>string</td>
     
     <td>The BIN picking number</td>
   </tr>
   <tr class="mandatory">
     <td >options</td>
     <td>object</td>
     
     <td>This is an object {"product_option_id": int, "option_value_id":int}</td>
   </tr>
   
  </tbody>
</table>

#### Response
Update product sku by ID
<pre>
{
    "id": 5,
    "product_id": 7,
    "sku": "MBA-1atest",
    "cost_price": "2.9900",
    "upc": "",
    "inventory_level": 0,
    "inventory_warning_level": 0,
    "bin_picking_number": "",
    "options": [
        {
            "product_option_id": 20,
            "option_value_id": 51
        }
    ]
}
</pre>

### GET products/id/skus/count.json
Get a total number of skus 

#### Request
This request does not take any parameters.

#### Response
Returns the number of product skus  
<pre>
  {
    "count": 2
  }
</pre>

### DELETE products/id/skus.json
DELETE all product skus

### DELETE products/id/skus/id.json
DELETE an product sku
