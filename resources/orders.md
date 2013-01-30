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
This PUT request takes following mandatory parameters.
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

A full list of allowed fields is described below.
<table class="table table-bordered"><thead><tr class="sortableHeader">
<th  data-column="0"><div class="tablesorter-header-inner"> API Field </div></th>
<th  data-column="1"><div class="tablesorter-header-inner"> API Data Type </div></th>
<th  data-column="6"><div class="tablesorter-header-inner"> Field Description </div></th>
</tr></thead><tbody>

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
<td > date_modified </td>
<td > date </td>
<td > The date the order was last modified. </td>
</tr>

<tr>
<td > subtotal_ex_tax </td>
<td > decimal  </td>
<td > The subtotal of the order excluding tax. </td>
</tr>

<tr>
<td > subtotal_inc_tax </td>
<td > decimal  </td>
<td > The subtotal of the order including tax. </td>
</tr>

<tr>
<td > subtotal_tax </td>
<td > decimal  </td>
<td > The amount of tax on the subtotal. </td>
</tr>

<tr>
<td > total_tax </td>
<td > decimal  </td>
<td > The total tax for the order. </td>
</tr>

<tr>
<td > base_shipping_cost </td>
<td > decimal  </td>
<td > The base shipping cost of the order. The base shipping cost is the sum of all of the shipping costs minus any discount amounts to the shipping costs. It may be inc or ex tax depending on the "Prices Entered With Tax?" tax setting.The base shipping * cost is the sum of all of the base shipping costs on each address. A * base shipping cost is a price entered by the store owner, either inc or * ex tax. </td>
</tr>

<tr>
<td > shipping_cost_ex_tax </td>
<td > decimal  </td>
<td > The total shipping cost of the order excluding tax. </td>
</tr>

<tr>
<td > shipping_cost_inc_tax </td>
<td > decimal  </td>
<td > The total shipping cost of the order including tax. </td>
</tr>

<tr>
<td > shipping_cost_tax </td>
<td > decimal  </td>
<td > The total tax for the shipping cost. </td>
</tr>

<tr>
<td > shipping_cost_tax_class_id </td>
<td > int </td>
<td > The ID of the tax class used for taxing shipping costs. </td>
</tr>

<tr>
<td > base_handling_cost </td>
<td > decimal  </td>
<td > The base handling cost of the order. The base handling cost is the sum of the all the handling costs. It may be inc or ex tax depending on the "Prices Entered With Tax?" tax setting. </td>
</tr>

<tr>
<td > handling_cost_ex_tax </td>
<td > decimal  </td>
<td > The handling cost of the order excluding tax. </td>
</tr>

<tr>
<td > handling_cost_inc_tax </td>
<td > decimal  </td>
<td > The handing cost of the order including tax. </td>
</tr>

<tr>
<td > handling_cost_tax </td>
<td > decimal  </td>
<td > The total tax for the handling cost. </td>
</tr>

<tr>
<td > handling_cost_tax_class_id </td>
<td > int </td>
<td > The ID of the tax class used for taxing handling costs. </td>
</tr>

<tr>
<td > base_wrapping_cost </td>
<td > decimal  </td>
<td > The base wrapping cost of the order. The base wrapping cost is the sum of all the wrapping costs on the items. It may be inc or ex tax depending on the "Prices Entered With Tax?" tax setting. </td>
</tr>

<tr>
<td > wrapping_cost_ex_tax </td>
<td > decimal  </td>
<td > The wrapping cost of the order including tax. </td>
</tr>

<tr>
<td > wrapping_cost_inc_tax </td>
<td > decimal  </td>
<td > The wrapping cost of the order excluding tax. </td>
</tr>

<tr>
<td > wrapping_cost_tax </td>
<td > decimal  </td>
<td > The total tax for the wrapping cost. </td>
</tr>

<tr>
<td > wrapping_cost_tax_class_id </td>
<td > int </td>
<td > The ID of the tax class used for taxing wrapping costs. </td>
</tr>

<tr>
<td > total_ex_tax </td>
<td > decimal  </td>
<td > The total of the order excluding tax. </td>
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
<td > status  </td>
<td > string  </td>
<td > The textual description of the status.  </td>
</tr>

<tr>
<td > items_total </td>
<td > int </td>
<td > The total quantity of the items (sum of products * quantity) in the order. </td>
</tr>

<tr>
<td > items_shipped </td>
<td > int  </td>
<td > The quantity of items that have been shipped. </td>
</tr>

<tr>
<td > payment_method </td>
<td > string </td>
<td > The payment method used for the order. </td>
</tr>

<tr>
<td > payment_provider_id </td>
<td > string </td>
<td > The ID or reference number of a payment from the payment provider/gateway. </td>
</tr>

<tr>
<td > payment_status </td>
<td > enum </td>
<td > The status of the payment. A payment status may be one of the following, depending on the payment method used: 
<ul>
  <li>authorized</li>
  <li>captured</li>
  <li>refunded</li>
  <li>partially refunded</li>
  <li>voided</li>
</ul>
</td>
</tr>

<tr>
<td > refunded_amount </td>
<td > decimal  </td>
<td > The amount that that has been refunded for the order. </td>
</tr>

<tr>
<td > order_is_digital </td>
<td > boolean </td>
<td > Indicates if the order contains purely digital delivery products. </td>
</tr>

<tr>
<td > date_shipped </td>
<td > date </td>
<td > The date the order was shipped. </td>
</tr>

<tr>
<td > store_credit_amount </td>
<td > decimal  </td>
<td > The amount of store credit the customer used to pay for the order. </td>
</tr>

<tr>
<td > gift_certificate_amount </td>
<td > decimal  </td>
<td > The amount of a gift certificate the customer used to pay for the order. </td>
</tr>

<tr>
<td > ip_address </td>
<td > string </td>
<td > The IP address of the user that placed the order. </td>
</tr>

<tr>
<td > geoip_country </td>
<td > string </td>
<td > The country the order was placed from as determined by GeoIP location. </td>
</tr>

<tr>
<td > geoip_country_iso2 </td>
<td > country code </td>
<td > The country code of the geoip_country field. </td>
</tr>

<tr>
<td > currency_id </td>
<td > int </td>

<td > The ID of the currency used by the customer to place the order. </td>
</tr>

<tr>
<td > currency_code </td>
<td > string(3) </td>
<td > The 3 letter currency code of the currency used to place the order. (Store version 7.3.6+) </td>
</tr>

<tr>
<td > default_currency_id </td>
<td > int </td>
<td > The ID of the store's default currency at the time of the order. </td>
</tr>

<tr>
<td > default_currency_code  </td>
<td > string  </td>
<td > The 3 letter currency code of the store's default currency at the time of the order. (Store version 7.3.6+)  </td>
</tr>

<tr>
<td > currency_exchange_rate </td>
<td > decimal </td>
<td > The exchange rate of the currency used to place the order. </td>
</tr>

<tr>
<td > staff_notes </td>
<td > text </td>
<td > Staff notes on the order. </td>
</tr>

<tr>
<td > customer_message </td>
<td > text </td>
<td > An order message left by the customer when placing the order. </td>
</tr>

<tr>
<td > discount_amount </td>
<td > decimal </td>
<td > The total discounts applied to the order, excluding coupons. </td>
</tr>

<tr>
<td > shipping_address_count </td>
<td > int </td>
<td > The amount of addresses that items were shipped to for the order. </td>
</tr>

<tr>
<td > coupon_discount </td>
<td > decimal </td>
<td > The total discount given on the order due to applied coupons. </td>
</tr>

<tr>
<td > is_deleted </td>
<td > boolean </td>
<td > Indicates if the order was deleted (archived). </td>
</tr>

<tr>
<td > billing_address  </td>
<td > object  </td>
<td > The address that the order is billed to. See the Billing Address section below for a definition of this object.  </td>
</tr>

<tr>
<td > shipping_addresses  </td>
<td > resource   </td>
<td > The address (or addresses if multi-address shipping was used) that the products were shipped to. See the Shipping Addresses resource for details.   
NB. Purely digital delivery orders will not have any shipping addresses. </td>
</tr>

<tr>
<td > products  </td>
<td > resource   </td>
<td > The list of products purchased in the order. See the Products sub-resource for a definition of this object.  </td>
</tr>

<tr>
<td > coupons  </td>
<td > resource   </td>
<td > A list of coupons applied to the order. See the Coupons resource for details. </td>
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
