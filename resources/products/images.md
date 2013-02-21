## Resources

<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>

   <tr>
     <td><a href="#get-productsidimagesjson">GET /products/id/images.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#post-productsidimagesjson">POST /products/id/images.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidimagesidjson">GET /products/id/images/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#put-productsidimagesidjson">PUT /products/id/images/id.json</a></td>
     
   </tr>
   <tr>
     <td><a href="#get-productsidimagescountjson">GET /products/id/images/count.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-productsidimagesjson">DELETE /products/id/images.json</a></td>
     
   </tr>

   <tr>
     <td><a href="#delete-productsidimagesidjson">DELETE /products/id/images/id.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description

### GET products/id/images.json
GET all images for an product

#### Request
This GET request does not take any parameters.

#### Response
product by ID
<pre>
[
    {
        "id": 5,
        "product_id": 28,
        "image_file": "sample_images/picture_1__48492.png",
        "is_thumbnail": true,
        "sort_order": 0,
        "description": "",
        "date_created": "Mon, 26 Oct 2009 05:08:32 +0000"
    },
    {
        "id": 6,
        "product_id": 28,
        "image_file": "sample_images/overview_hero__21040.jpg",
        "is_thumbnail": false,
        "sort_order": 1,
        "description": "",
        "date_created": "Mon, 26 Oct 2009 05:08:32 +0000"
    },
    ...
]
</pre> 

### POST products/id/images.json
create a product image

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
   <td >product_id</td>
   <td>integer</td>
   
   <td>The ID of the product the image belongs to</td>
 </tr>
 <tr class="mandatory">
   <td >image_file</td>
   <td>string</td>
   
   <td>When specifying a product image, the image_file should be specified as either: A path to an image already uploaded via FTP in the import directory and the path should be relative from the import directory. It can be a URL to an image accessible on the internet.</td>
 </tr>
 <tr >
   <td >is_thumbnail</td>
   <td>boolean</td>
   
   <td>If true, the image is used as product thumbnail</td>
 </tr>
 <tr >
   <td >sort_order</td>
   <td>integer</td>
   
   <td>The order in which the image will be displayed on the product page. When updating if the image is given a lower priority, all image with a sort_order the same or greater than the images new sort_order value will have their sort_order reordered</td>
 </tr>
 <tr >
   <td >description</td>
   <td>text</td>
   
   <td>The description for the image</td>
 </tr>
 
</tbody>
</table>

#### Response
new image for an product
<pre>
{
    "id": 116,
    "product_id": 29,
    "image_file": "p/022/astonishing-x-men-1-100k__36562.jpg",
    "is_thumbnail": false,
    "sort_order": 0,
    "description": "",
    "date_created": "Fri, 21 Dec 2012 18:54:04 +0000"
}
</pre> 


### GET products/id/images/id.json
GET a specific image


#### Request
This GET request does not take any parameters.


#### Response
product image by ID
<pre>
{
    "id": 116,
    "product_id": 29,
    "image_file": "p/022/astonishing-x-men-1-100k__36562.jpg",
    "is_thumbnail": false,
    "sort_order": 0,
    "description": "",
    "date_created": "Fri, 21 Dec 2012 18:54:04 +0000"
}
</pre>

### PUT products/id/images/id.json
update a specific image


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

 <tr >
   <td >image_file</td>
   <td>string</td>
   
   <td>When specifying a product image, the image_file should be specified as either: A path to an image already uploaded via FTP in the import directory and the path should be relative from the import directory. It can be a URL to an image accessible on the internet.</td>
 </tr>
 <tr >
   <td >is_thumbnail</td>
   <td>boolean</td>
   
   <td>If true, the image is used as product thumbnail</td>
 </tr>
 <tr >
   <td >sort_order</td>
   <td>integer</td>
   
   <td>The order in which the image will be displayed on the product page. When updating if the image is given a lower priority, all image with a sort_order the same or greater than the images new sort_order value will have their sort_order reordered</td>
 </tr>
 <tr >
   <td >description</td>
   <td>text</td>
   
   <td>The description for the image</td>
 </tr>
 
</tbody>
</table>

#### Response
Update product image by ID
<pre>
{
    "id": 118,
    "product_id": 30,
    "image_file": "k/392/ud2vk0n1l0zcfr7gtlqi__43888.png",
    "is_thumbnail": false,
    "sort_order": 1,
    "description": "",
    "date_created": "Fri, 21 Dec 2012 19:01:03 +0000"
}  
</pre>

### GET products/id/images/count.json
Get a total number of images in the store

#### Request
This request does not take any parameters.

#### Response
Returns the number of product images in the store 
<pre>
  {
    "count": 2
  }
</pre>

### DELETE products/id/images.json
DELETE all product images

### DELETE products/id/images/id.json
DELETE an product image
