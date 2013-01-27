## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-ordersidcouponsjson">GET orders/id/coupons.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidcouponsidjson">GET orders/id/coupons/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-ordersidcouponscountjson">GET orders/id/coupons/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET orders/id/coupons.json
GET coupons for an order

#### Request
There are no fields to filter for this request

#### Response
List of coupons
<pre>
[
    {
        "id": 1,
        "coupon_id": 1,
        "order_id": 115,
        "code": "557D2DEA0CCAFA1",
        "amount": "5.0000",
        "type": 1,
        "discount": "4.6600"
    }
]
</pre>


### GET orders/id/coupons/id.json
GET a coupon from a store

#### Request
This GET request does not take any parameters.

#### Response
coupon by ID
<pre>
{
    "id": 1,
    "coupon_id": 1,
    "order_id": 115,
    "code": "557D2DEA0CCAFA1",
    "amount": "5.0000",
    "type": 1,
    "discount": "4.6600"
}
</pre>    


### GET orders/id/coupons/count.json
Get a total number of coupons in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of coupons in the store 
<pre>
  {
    "count": 10
  }
</pre>
