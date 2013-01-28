## Resources
<table class="table table-bproducted ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#get-productsidvideosjson">GET products/id/videos.json</a></td>
     
   </tr>
   
   <tr>
     <td><a href="#get-productsidvideoscountjson">GET products/id/videos/count.json</a></td>
     
   </tr>
   
 </tbody>
</table>
   
## Description
### GET products/id/videos.json
GET videos for an product

#### Request
There are no fields to filter for this request

#### Response
List of videos
<pre>
[
    {
        "id": "UmhvxsOwhqk",
        "product_id": 30,
        "sort_order": 0,
        "name": "X-Men Evolution: Season 1, Episode 1"
    }
]
</pre>

### GET products/id/videos/count.json
Get a total number of videos for the product

#### Request
This request does not take any parameters.

#### Response
Returns the number of videos for the product 
<pre>
  {
    "count": 10
  }
</pre>
