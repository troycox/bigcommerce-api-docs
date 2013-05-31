## API changelog

### v2 changes

#### 27 May 2013
1. [Orders resource](https://developer.bigcommerce.com/api/orders). Added POST support.
2. [Orders resource](https://developer.bigcommerce.com/api/orders). Fixed a bug where GET was returning the inc tax value in the 'total_ex_tax' field.

#### 20 May 2013
1. [Coupons resource](https://developer.bigcommerce.com/api/coupons). Fixed a bug where, regardless of the value specified for 'type', the API was always setting the value to 'per_item_discount'.
2. [Coupons resource](https://developer.bigcommerce.com/api/coupons). Fixed a bug where 500 error was returned on JSON POST when 'applies_to' field was not supplied.
3. [Coupons resource](https://developer.bigcommerce.com/api/coupons). Fixed a bug where the API was wrongly allowing duplicate coupon names on PUT and POST.
4. [Orders resource](https://developer.bigcommerce.com/api/orders). Added 'order_product_id' field.

#### 14 May 2013
1. [Coupons resource](https://developer.bigcommerce.com/api/coupons). Fixed a bug where the 'amount' field was seen as invalid on XML POST if there were zeros after the decimal point

#### 3 Apr 2013
1. [Customers resource](https://developer.bigcommerce.com/api/customers) - Added POST/PUT/DELETE support for Customers resource

#### 12 Feb 2013
1. [Coupons resource](https://developer.bigcommerce.com/api/coupons). A new resource with support for POST/PUT/GET/DELETE.
2. [Store resource](https://developer.bigcommerce.com/api/store). A new resource with support for GET.

