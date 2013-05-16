## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-ordersidproductsjson">GET orders/{id}/products.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidproductsidjson">GET orders/{id}/products/{id}.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidproductscountjson">GET orders/{id}/products/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET orders/{id}/products.json
GET products for an order

#### Request
There are no fields to filter for this request

#### Response
List of products
<pre>
[
    {
        "id": 16,
        "order_id": 115,
        "product_id": 0,
        "order_address_id": 16,
        "name": "Cynthia Gilbert Signature Collection",
        "sku": "",
        "type": "physical",
        "base_price": "93.1800",
        "price_ex_tax": "93.1800",
        "price_inc_tax": "93.1800",
        "price_tax": "0.0000",
        "base_total": "93.1800",
        "total_ex_tax": "93.1800",
        "total_inc_tax": "93.1800",
        "total_tax": "0.0000",
        "weight": "0",
        "quantity": 1,
        "base_cost_price": "0.0000",
        "cost_price_inc_tax": "0.0000",
        "cost_price_ex_tax": "0.0000",
        "cost_price_tax": "0.0000",
        "is_refunded": false,
        "refund_amount": "0.0000",
        "return_id": 0,
        "wrapping_name": "",
        "base_wrapping_cost": "0.0000",
        "wrapping_cost_ex_tax": "0.0000",
        "wrapping_cost_inc_tax": "0.0000",
        "wrapping_cost_tax": "0.0000",
        "wrapping_message": "",
        "quantity_shipped": 0,
        "event_name": null,
        "event_date": "",
        "fixed_shipping_cost": "0.0000",
        "ebay_item_id": "",
        "ebay_transaction_id": "",
        "option_set_id": null,
        "parent_order_product_id": null,
        "is_bundled_product ": false,
        "bin_picking_number": "",
        "applied_discounts": [
            {
                "id": "coupon",
                "amount": 4.66
            }
        ],
        "product_options": [],
        "configurable_fields": []
    }
] 
</pre>


### GET orders/{id}/products/{id}.json
GET a product by id for the order

#### Request
This GET request does not take any parameters.

#### Response
product by ID
<pre>
{
    "id": 16,
    "order_id": 115,
    "product_id": 0,
    "order_address_id": 16,
    "name": "Cynthia Gilbert Signature Collection",
    "sku": "",
    "type": "physical",
    "base_price": "93.1800",
    "price_ex_tax": "93.1800",
    "price_inc_tax": "93.1800",
    "price_tax": "0.0000",
    "base_total": "93.1800",
    "total_ex_tax": "93.1800",
    "total_inc_tax": "93.1800",
    "total_tax": "0.0000",
    "weight": "0",
    "quantity": 1,
    "base_cost_price": "0.0000",
    "cost_price_inc_tax": "0.0000",
    "cost_price_ex_tax": "0.0000",
    "cost_price_tax": "0.0000",
    "is_refunded": false,
    "refund_amount": "0.0000",
    "return_id": 0,
    "wrapping_name": "",
    "base_wrapping_cost": "0.0000",
    "wrapping_cost_ex_tax": "0.0000",
    "wrapping_cost_inc_tax": "0.0000",
    "wrapping_cost_tax": "0.0000",
    "wrapping_message": "",
    "quantity_shipped": 0,
    "event_name": null,
    "event_date": "",
    "fixed_shipping_cost": "0.0000",
    "ebay_item_id": "",
    "ebay_transaction_id": "",
    "option_set_id": null,
    "parent_order_product_id": null,
    "is_bundled_product ": false,
    "bin_picking_number": "",
    "applied_discounts": [
        {
            "id": "coupon",
            "amount": 4.66
        }
    ],
    "product_options": [],
    "configurable_fields": []
}
</pre>    


### GET orders/{id}/products/count.json
Get a total number of products for an order

#### Request
This request does not take any parameters.

#### Response
Returns the number of products for the order
<pre>
  {
    "count": 10
  }
</pre>
