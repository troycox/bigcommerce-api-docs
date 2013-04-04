## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-ordersjson">GET  /orders.json</a></td>
     
   </tr>
   
   <tr>
     <td><a href="#get-ordersidjson">GET /orders/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-ordersidjson">PUT /orders/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-orderscountjson">GET /orders/count.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-ordersjson">DELETE /orders.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#delete-ordersidjson">DELETE /orders/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET orders.json
GET orders from a store

#### Request
These fields can be used to filter the query. By default, without any filters, the GET request returns all the orders.

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
    <td > id </td>
    <td > int </td>
    <td > The ID of the order. This is auto-generated for new orders. </td>
    </tr>

    <tr>
    <td > customer_id </td>
    <td > int </td>
    <td > The ID of the customer that placed the order or 0 if it was a guest order. </td>
    </tr>

    <tr>
    <td > date_created </td>
    <td > date </td>
    <td > The date the order was placed. If not supplied, the current date will be used. Please note that orders processed by live online payment gateways first arrive in the orders data with an "Incomplete" <strong>status</strong> and are then updated (see the <strong>date_modified</strong> field) with final payment information. If your application relies on the arrival of new orders you may need to check both <strong>date_created</strong> and <strong>status</strong> fields (or <strong>status_id</strong>). </td>
    </tr>
   <tr>
    <td > total_inc_tax </td>
    <td > decimal  </td>
    <td > The total of the order including tax. </td>
    </tr>

    <tr>
    <td > status_id </td>
    <td > int </td>
    <td > The status of the order. A list of available statuses can be retrieved from Order Statuses resource </td>
    </tr>

    <tr>
  <td > payment_method </td>
  <td > string </td>
  <td > The payment method used for the order. </td>
  </tr>

  <tr>
  <td > is_deleted </td>
  <td > boolean </td>
  <td > Indicates if the order was deleted (archived). </td>
  </tr>
  </tbody>
</table>

#### Response
List of orders
<pre>
[
  {
    "id": 100,
    "customer_id": 10,
    "date_created": "Wed, 14 Nov 2012 19:26:23 +0000",
    "date_modified": "Wed, 14 Nov 2012 19:26:23 +0000",
    "date_shipped": "",
    "status_id": 11,
    "status": "Awaiting Fulfillment",
    "subtotal_ex_tax": "79.0000",
    "subtotal_inc_tax": "79.0000",
    "subtotal_tax": "0.0000",
    "base_shipping_cost": "0.0000",
    "shipping_cost_ex_tax": "0.0000",
    "shipping_cost_inc_tax": "0.0000",
    "shipping_cost_tax": "0.0000",
    "shipping_cost_tax_class_id": 2,
    "base_handling_cost": "0.0000",
    "handling_cost_ex_tax": "0.0000",
    "handling_cost_inc_tax": "0.0000",
    "handling_cost_tax": "0.0000",
    "handling_cost_tax_class_id": 2,
    "base_wrapping_cost": "0.0000",
    "wrapping_cost_ex_tax": "0.0000",
    "wrapping_cost_inc_tax": "0.0000",
    "wrapping_cost_tax": "0.0000",
    "wrapping_cost_tax_class_id": 3,
    "total_ex_tax": "79.0000",
    "total_inc_tax": "79.0000",
    "total_tax": "0.0000",
    "items_total": 1,
    "items_shipped": 0,
    "payment_method": "cash",
    "payment_provider_id": null,
    "payment_status": "",
    "refunded_amount": "0.0000",
    "order_is_digital": false,
    "store_credit_amount": "0.0000",
    "gift_certificate_amount": "0.0000",
    "ip_address": "50.58.18.2",
    "geoip_country": "",
    "geoip_country_iso2": "",
    "currency_id": 1,
    "currency_code": "USD",
    "currency_exchange_rate": "1.0000000000",
    "default_currency_id": 1,
    "default_currency_code": "USD",
    "staff_notes": "",
    "customer_message": "",
    "discount_amount": "0.0000",
    "coupon_discount": "0.0000",
    "shipping_address_count": 1,
    "is_deleted": false,
    "billing_address": {
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "country_iso2": "US",
        "phone": "",
        "email": "elsie@example.com"
    },
    "products": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/products.json",
        "resource": "/orders/100/products"
    },
    "shipping_addresses": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/shippingaddresses.json",
        "resource": "/orders/100/shippingaddresses"
    },
    "coupons": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/coupons.json",
        "resource": "/orders/100/coupons"
    }
  }
]
</pre>

### GET orders/id.json
GET a order from a store

#### Request
This GET request does not take any parameters.

#### Response
order by ID
<pre>
{
    "id": 100,
    "customer_id": 10,
    "date_created": "Wed, 14 Nov 2012 19:26:23 +0000",
    "date_modified": "Wed, 14 Nov 2012 19:26:23 +0000",
    "date_shipped": "",
    "status_id": 11,
    "status": "Awaiting Fulfillment",
    "subtotal_ex_tax": "79.0000",
    "subtotal_inc_tax": "79.0000",
    "subtotal_tax": "0.0000",
    "base_shipping_cost": "0.0000",
    "shipping_cost_ex_tax": "0.0000",
    "shipping_cost_inc_tax": "0.0000",
    "shipping_cost_tax": "0.0000",
    "shipping_cost_tax_class_id": 2,
    "base_handling_cost": "0.0000",
    "handling_cost_ex_tax": "0.0000",
    "handling_cost_inc_tax": "0.0000",
    "handling_cost_tax": "0.0000",
    "handling_cost_tax_class_id": 2,
    "base_wrapping_cost": "0.0000",
    "wrapping_cost_ex_tax": "0.0000",
    "wrapping_cost_inc_tax": "0.0000",
    "wrapping_cost_tax": "0.0000",
    "wrapping_cost_tax_class_id": 3,
    "total_ex_tax": "79.0000",
    "total_inc_tax": "79.0000",
    "total_tax": "0.0000",
    "items_total": 1,
    "items_shipped": 0,
    "payment_method": "cash",
    "payment_provider_id": null,
    "payment_status": "",
    "refunded_amount": "0.0000",
    "order_is_digital": false,
    "store_credit_amount": "0.0000",
    "gift_certificate_amount": "0.0000",
    "ip_address": "50.58.18.2",
    "geoip_country": "",
    "geoip_country_iso2": "",
    "currency_id": 1,
    "currency_code": "USD",
    "currency_exchange_rate": "1.0000000000",
    "default_currency_id": 1,
    "default_currency_code": "USD",
    "staff_notes": "",
    "customer_message": "",
    "discount_amount": "0.0000",
    "coupon_discount": "0.0000",
    "shipping_address_count": 1,
    "is_deleted": false,
    "billing_address": {
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "country_iso2": "US",
        "phone": "",
        "email": "elsie@example.com"
    },
    "products": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/products.json",
        "resource": "/orders/100/products"
    },
    "shipping_addresses": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/shippingaddresses.json",
        "resource": "/orders/100/shippingaddresses"
    },
    "coupons": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/coupons.json",
        "resource": "/orders/100/coupons"
    }
}  
</pre>    

### PUT orders/id.json
UPDATE a order from a store

#### Request
This PUT request allows updating an order. At this time, only the following fields are supported.
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
    <td > status_id </td>
    <td > int </td>
    <td > The status id for the order. This is a number from 0-12. Check the <a href="#orderstatus"> Order status </a> endpoint for more info. </td>
    </tr>
    <tr>
    <td > is_deleted </td>
    <td > boolean </td>
    <td > Indicates if the order was deleted (archived). </td>
    </tr>
    
  </tbody>
</table>



#### Response
A successful put udpates a order in the store 
<pre>
{
    "id": 100,
    "customer_id": 10,
    "date_created": "Wed, 14 Nov 2012 19:26:23 +0000",
    "date_modified": "Wed, 19 Dec 2012 12:30:35 +0000",
    "date_shipped": "",
    "status_id": 0,
    "status": null,
    "subtotal_ex_tax": "79.0000",
    "subtotal_inc_tax": "79.0000",
    "subtotal_tax": "0.0000",
    "base_shipping_cost": "0.0000",
    "shipping_cost_ex_tax": "0.0000",
    "shipping_cost_inc_tax": "0.0000",
    "shipping_cost_tax": "0.0000",
    "shipping_cost_tax_class_id": 2,
    "base_handling_cost": "0.0000",
    "handling_cost_ex_tax": "0.0000",
    "handling_cost_inc_tax": "0.0000",
    "handling_cost_tax": "0.0000",
    "handling_cost_tax_class_id": 2,
    "base_wrapping_cost": "0.0000",
    "wrapping_cost_ex_tax": "0.0000",
    "wrapping_cost_inc_tax": "0.0000",
    "wrapping_cost_tax": "0.0000",
    "wrapping_cost_tax_class_id": 3,
    "total_ex_tax": "79.0000",
    "total_inc_tax": "79.0000",
    "total_tax": "0.0000",
    "items_total": 1,
    "items_shipped": 0,
    "payment_method": "cash",
    "payment_provider_id": null,
    "payment_status": "",
    "refunded_amount": "0.0000",
    "order_is_digital": false,
    "store_credit_amount": "0.0000",
    "gift_certificate_amount": "0.0000",
    "ip_address": "50.58.18.2",
    "geoip_country": "",
    "geoip_country_iso2": "",
    "currency_id": 1,
    "currency_code": "USD",
    "currency_exchange_rate": "1.0000000000",
    "default_currency_id": 1,
    "default_currency_code": "USD",
    "staff_notes": "",
    "customer_message": "",
    "discount_amount": "0.0000",
    "coupon_discount": "0.0000",
    "shipping_address_count": 1,
    "is_deleted": true,
    "billing_address": {
        "first_name": "Trisha",
        "last_name": "McLaughlin",
        "company": "",
        "street_1": "12345 W Anderson Ln",
        "street_2": "",
        "city": "Austin",
        "state": "Texas",
        "zip": "78757",
        "country": "United States",
        "country_iso2": "US",
        "phone": "",
        "email": "elsie@example.com"
    },
    "products": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/products.json",
        "resource": "/orders/100/products"
    },
    "shipping_addresses": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/shippingaddresses.json",
        "resource": "/orders/100/shippingaddresses"
    },
    "coupons": {
        "url": "https://store-bwvr466.mybigcommerce.com/api/v2/orders/100/coupons.json",
        "resource": "/orders/100/coupons"
    }
}  
</pre>
### GET orders/count.json
Get a total number of orders in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of orders in the store 
<pre>
  {
    "count": 10
  }
</pre>
Here are resources to delete orders. This is a potentially destrutive operation. Remember that you cannot recover deleted orders.

### DELETE orders.json
DELETE all orders

### DELETE orders/id.json
DELETE a order
