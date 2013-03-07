## Responses
The API responds to requests with different HTTP status codes depending on the result from the request. As with regular HTTP requests, the responses are categorized according into the following classes. Error responses may also include an error message in the body to assist the client in resolving the problem.

## 2xx Success
These codes are returned for requests that were understood and processed successfully.

<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div class="tablesorter-header-inner"><p> Code </p></div></th>
<th  data-column="1"><div class="tablesorter-header-inner"><p> Definition </p></div></th>
<th  data-column="2"><div class="tablesorter-header-inner"><p> Purpose </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> 200 </p></td>
<td ><p> OK </p></td>
<td ><p> For successful GET/PUT requests. </p></td>
</tr>
<tr>
<td ><p> 201 </p></td>
<td ><p> Created </p></td>
<td ><p> For a successful POST request. </p></td>
</tr>
<tr>
<td ><p> 202 </p></td>
<td ><p> Accepted </p></td>
<td ><p> For a request that resulted in a scheduled task being created to perform the actual request. </p></td>
</tr>
<tr>
<td ><p> 204 <br class="atl-forced-newline"> </p></td>
<td ><p> No Content <br class="atl-forced-newline"> </p></td>
<td ><p> For a successful request that produced no response (such as DELETE requests). <br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>

## 3xx Redirection
These codes are returned for requests that have resulted in the client needing to take further action to complete the request.
<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div class="tablesorter-header-inner"><p> Code </p></div></th>
<th  data-column="1"><div class="tablesorter-header-inner"><p> Definition </p></div></th>
<th  data-column="2"><div class="tablesorter-header-inner"><p> Purpose </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> 301 </p></td>
<td ><p> Moved Permanently </p></td>
<td ><p> When the API routes have changed (unlikely) or if the incoming request is not secure (http) then it will be redirect to the secure (https) version. </p></td>
</tr>
<tr>
<td ><p> 302 <br class="atl-forced-newline"> </p></td>
<td ><p> Found <br class="atl-forced-newline"> </p></td>
<td ><p> When the resource was found at a different location. When a request to a deprecated version of the API is received, a 302 Found response will be issued to the current API version. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 304 <br class="atl-forced-newline"> </p></td>
<td ><p> Not Modified <br class="atl-forced-newline"> </p></td>
<td ><p> If an If-Modified-Since header is sent in the request and the resource has not been modified since the specified date, then this response will be sent. NB. See resource specific pages for support for the If-Modified-Since header. <br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>

## 4xx Client Error
<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div class="tablesorter-header-inner"><p> Code </p></div></th>
<th  data-column="1"><div class="tablesorter-header-inner"><p> Definition </p></div></th>
<th  data-column="2"><div class="tablesorter-header-inner"><p> Purpose </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> 400 <br class="atl-forced-newline"> </p></td>
<td ><p> Bad Request <br class="atl-forced-newline"> </p></td>
<td ><p> Issued when a malformed request was sent. Such as due to invalid syntax or missing required data. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 401 <br class="atl-forced-newline"> </p></td>
<td ><p> Unauthorized <br class="atl-forced-newline"> </p></td>
<td ><p> This response is sent when either the clients credentials are not provided or are incorrect. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 403 <br class="atl-forced-newline"> </p></td>
<td ><p> Forbidden <br class="atl-forced-newline"> </p></td>
<td ><p> When the user doesn't have permission to perform a specific operation on a resource (eg. edit a product). Permissions can be set through the store control panel. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 404 </p></td>
<td ><p> Not Found </p></td>
<td ><p> When a particular resource doesn't exist or couldn't be found. </p></td>
</tr>
<tr>
<td ><p> 405 <br class="atl-forced-newline"> </p></td>
<td ><p> Method Not Allowed <br class="atl-forced-newline"> </p></td>
<td ><p> The resource was found, but doesn't support the request method. Issued when either a specific method isn't yet implemented on a resource, or the resource doesn't support the method at all (eg. PUT on /orders is invalid, but PUT on /orders/{id} is valid). <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 406 <br class="atl-forced-newline"> </p></td>
<td ><p> Not Acceptable <br class="atl-forced-newline"> </p></td>
<td ><p> When the client specifies a response content type in the Accept header that is not supported. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 409 </p></td>
<td ><p> Conflict </p></td>
<td ><p> A change requested by the client is being rejected due to a condition imposed by the server. The exact reasons response for this will vary from one resource to the next. Examples may include attempting to delete a Category which would result in Products being orphaned. Additional information about the conflict and how to resolve it may be available in the <code>details</code> section of the response. </p></td>
</tr>
<tr>
<td ><p> 413 <br class="atl-forced-newline"> </p></td>
<td ><p> Request Entity Too Large <br class="atl-forced-newline"> </p></td>
<td ><p> When the client requests too many objects. eg. the&nbsp;<strong>limit</strong> parameter was above the maximum allowed. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 415 <br class="atl-forced-newline"> </p></td>
<td ><p> Unsupported Media Type <br class="atl-forced-newline"> </p></td>
<td ><p> When the client specifies a content type in the Content-Type header that is not supported by the API. <br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>

## 5xx Server Error
These codes are returned for requests that could not be processed due to an internal error with the API or server.
<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div class="tablesorter-header-inner"><p> Code </p></div></th>
<th  data-column="1"><div class="tablesorter-header-inner"><p> Definition </p></div></th>
<th  data-column="2"><div class="tablesorter-header-inner"><p> Purpose </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> 500 </p></td>
<td ><p> Internal Server Error </p></td>
<td ><p> When an error has occurred within the API. </p></td>
</tr>
<tr>
<td ><p> 501 </p></td>
<td ><p> Not Implemented </p></td>
<td ><p> When a request method is sent that is not supported by the API (eg. TRACE, PATCH). </p></td>
</tr>
<tr>
<td ><p> 503 <br class="atl-forced-newline"> </p></td>
<td ><p> Service Unavailable <br class="atl-forced-newline"> </p></td>
<td ><p> When the store is marked as "Down for Maintenance" or the store is being upgraded to a new version. <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 507 <br class="atl-forced-newline"> </p></td>
<td ><p> Insufficient Storage <br class="atl-forced-newline"> </p></td>
<td ><p> When the store has reached a limitation for the resource according to their Bigcommerce plan (eg 500 product limit). <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> 509 <br class="atl-forced-newline"> </p></td>
<td ><p> Bandwidth Limit Exceeded <br class="atl-forced-newline"> </p></td>
<td ><p> When the requests-per-hour limitations for the API have been reached. <br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>
