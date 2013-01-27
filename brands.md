## Resources
<table class="table table-bordered ">
  <thead>
   <tr>
     <th>Resource</th>
   </tr>
 </thead>
 <tbody>
   <tr>
     <td><a href="#brands_r1"><span class="label label-info">GET </span> <%= "#{base_url}brands.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r2"><span class="label label-success">POST </span> <%= "#{base_url}brands.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r3"><span class="label label-info">GET </span> <%= "#{base_url}brands/id.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r4"><span class="label label-warning">PUT </span> <%= "#{base_url}brands/id.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r5"><span class="label label-info">GET </span> <%= "#{base_url}brands/count.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r6"><span class="label label-important">DELETE </span> <%= "#{base_url}brands.json" %></a></td>
     
   </tr>
   <tr>
     <td><a href="#brands_r7"><span class="label label-important">DELETE </span> <%= "#{base_url}brands/id.json" %></a></td>
     
   </tr>
   
 </tbody>
</table>
   
   
   
   <br/>
   <h2>Description</h3>
    <h4 id="brands_r1"><span class="label label-info">GET </span> <%= "#{base_url}brands.json" %></h4>
    <p>GET brands from a store</p>
    <%if api_key %>
    <%= link_to "Try this out", "https://"+user_name+":"+api_key+"@"+store_url+"/brands.json", :target => "_blank", :class => "btn btn-info"%>
    <% end %>
    <!-- <h4>{GET,PUT,DELETE} store/api/v2/brands/id.json</h4> -->

    <h3> Request </h3>
    <p> These fields can be used to filter the query. By default, without any filters, the GET request returns all the brands. </p>

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
   <h4> Response </h4>
   
   <p> The request returns the list of brands in the store </p>
   <pre class="prettyprint">
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
</pre>


<h4 id="brands_r2"><span class="label label-success">POST </span> <%= "#{base_url}brands.json" %></h4>
<p>create a brand</p>

<h3> Request </h3>
<p> Mandatory fields are highlighted blue </p>

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
<h4> Response </h4>
<p> A successful post creates a brand in the store </p>
<pre class="prettyprint">
  {
  "id": 10,
  "name": "Xmen",
  "page_title": "X men brand",
  "meta_keywords": null,
  "meta_description": null,
  "image_file": "t/apirmzk0a__43675.jpg",
  "search_keywords": "xmen, awesomeness"
}
</pre>
<p> If the image_file is invalid, you might see a response with status code 400. </p>
<pre class="prettyprint">
  [
  {
  "status": 400,
  "message": "The field 'image_file' is invalid.",
  "details": {
  "invalid_reason": "The resource at 'http://cdn1.Bigcommerce.com/server800/1vbhafz/products/28/images/6/overview_hero__21040.1349822426.1280.1280.jpg' could not be downloaded and may be invalid."
}
}
]
</pre>
<h4 id="brands_r3"><span class="label label-info">GET </span> <%= "#{base_url}brands/{id}.json" %></h4>
<p>GET brands by id</p>
<%if @api_key%>
<%= link_to "Try this out", "https://"+user_name+":"+api_key+"@"+store_url+"/brands/1.json", :target => "_blank", :class => "btn btn-info"%>
<% end %>
<!-- <h4>{GET,PUT,DELETE} store/api/v2/brands/id.json</h4> -->

<h3> Request </h3>
<p> These fields can be used to filter the query. By default, without any filters, the GET request returns all the brands. </p>

<h4> Response </h4>


<p> The request returns the requested brand </p>
<pre class="prettyprint">
  
  {
  "id": 1,
  "name": "Apple",
  "page_title": "",
  "meta_keywords": "",
  "meta_description": "",
  "image_file": "",
  "search_keywords": ""
}

</pre>
<h4 id="brands_r4"><span class="label label-warning">PUT </span> <%= "#{base_url}brands/1.json" %></h4>
<p>update a brand</p>

<h3> Request </h3>


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
<h4> Response </h4>
<p> A successful put udpates a brand in the store </p>
<pre class="prettyprint">
  {
  "id": 10,
  "name": "Xmen",
  "page_title": "X men brand",
  "meta_keywords": null,
  "meta_description": null,
  "image_file": "t/apirmzk0a__43675.jpg",
  "search_keywords": "xmen, awesomeness"
}
</pre>

<h4 id="brands_r5"><span class="label label-info">GET </span> <%= "#{base_url}brands/count.json" %></h4>
<p>GET a count brands from a store</p>
<%if api_key%>
<%= link_to "Try this out", "https://"+user_name+":"+api_key+"@"+store_url+"/brands/count.json", :target => "_blank", :class => "btn btn-info"%>
<% end %>
<!-- <h4>{GET,PUT,DELETE} store/api/v2/brands/id.json</h4> -->


<h4> Response </h4>


<p> The request returns the number of brands in the store </p>
<pre class="prettyprint">
  {
  "count": 10
}
</pre>
<p> Here are resources to delete brands. This is a potentially destrutive operation. Remember that you cannot recover deleted brands. </p>
<h4 id="brands_r6"><span class="label label-important">DELETE </span> <%= "#{base_url}brands.json" %></h4>
<p>DELETE all brands from a store</p>
<h4 id="brands_r7"><span class="label label-important">DELETE </span> <%= "#{base_url}brands/id.json" %></h4>
<p>DELETE a brand by ID from a store</p>