## HTTP Headers

### Request Headers
The Bigcommerce API supports various HTTP headers which are used for authorization, controlling content type. Some headers can be also used for purposes such as increasing performance of your application by only returning responses when content has been modified.
<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div ><p> Header </p></div></th>
<th  data-column="1"><div ><p> Operations </p></div></th>
<th  data-column="2"><div ><p> Allowed Values </p></div></th>
<th  data-column="3"><div ><p> Description </p></div></th>
<th  data-column="4"><div ><p> Required </p></div></th>
<th  data-column="5"><div ><p> Example </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> Accept <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests) <br class="atl-forced-newline"> </p></td>
<td ><p> The MIME type for the format you want to receive a response in. See the <a href="/display/API/Data+Formats">Data Formats</a> page for details. <br class="atl-forced-newline"> </p></td>
<td ><p>&nbsp;</p></td>
<td ><p> application/xml <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> Authorization <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> Basic <br class="atl-forced-newline"> </p></td>
<td ><p> The user credentials for accessing the API. See the Yes<a href="/display/API/Authentication">Authentication</a> page for details. <br class="atl-forced-newline"> </p></td>
<td ><p> &nbsp; Yes <br class="atl-forced-newline"> </p></td>
<td ><p> Basic&nbsp;YWRtaW46cGFzc3dvcmQ= <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> Content-Type <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests) <br class="atl-forced-newline"> </p></td>
<td ><p> The MIME type of the request body. Use to validate and parse the request to the API. </p></td>
<td ><p> &nbsp; Yes <br class="atl-forced-newline"> </p></td>
<td ><p> application/json </p></td>
</tr>
<tr>
<td ><p> If-Modified-Since </p></td>
<td ><p> GET <br class="atl-forced-newline"> </p></td>
<td ><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td ><p> If supplied, then only resources modified since the specified date will be returned. If there are no modified objects, then a <strong>304 Not Modified</strong> response will be sent. Please refer to the individual resource pages for support for this header. </p></td>
<td ><p>&nbsp;</p></td>
<td ><p> Tue, 15 Nov 2011 12:45:26 GMT <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> User-Agent </p></td>
<td ><p> All </p></td>
<td ><p> String </p></td>
<td ><p> While it is not required, we ask that you specify a user agent which identifies your integration/client with your requests. </p></td>
<td ><p>&nbsp;</p></td>
<td ><p>&nbsp;</p></td>
</tr>
</tbody></table>

### Response Headers

<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div ><p> Header </p></div></th>
<th  data-column="1"><div ><p> Operations </p></div></th>
<th  data-column="2"><div ><p> Possible Values <br class="atl-forced-newline"> </p></div></th>
<th  data-column="3"><div ><p> Description </p></div></th>
<th  data-column="4"><div ><p> Example </p></div></th>
</tr></thead><tbody>

<tr>
<td ><p> Date <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td ><p> The date the response was sent. <br class="atl-forced-newline"> </p></td>
<td ><p> Tue, 15 Nov 2011 12:45:26 GMT </p></td>
</tr>
<tr>
<td ><p> Last-Modified </p></td>
<td ><p> GET, PUT, POST </p></td>
<td ><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td ><p> The date the resource was last modified. Please refer to the individual resource pages for support for this header. </p></td>
<td ><p> Tue, 15 Nov 2011 12:45:26 GMT </p></td>
</tr>
<tr>
<td ><p> Content-Type <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests, or if no extension is supplied) </p></td>
<td ><p> The MIME type of the response, dependent on the extension of the endpoint that was requested. <br class="atl-forced-newline"> </p></td>
<td ><p> application/json </p></td>
</tr>
<tr>
<td ><p> Content-Location <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> A URI. <br class="atl-forced-newline"> </p></td>
<td ><p> Sent if the request was redirected. <br class="atl-forced-newline"> </p></td>
<td ><p> /api/v2/orders/5.json <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> WWW-Authenticate <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> Basic <br class="atl-forced-newline"> </p></td>
<td ><p> Indicates the authentication scheme that should be used to access the API. Sent with a&nbsp;<strong>401 Unauthorized</strong> response if HTTP Basic authentication credentials weren't supplied. <br class="atl-forced-newline"> </p></td>
<td ><p> Basic <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> Location <br class="atl-forced-newline"> </p></td>
<td ><p> POST <br class="atl-forced-newline"> </p></td>
<td ><p> A URI. <br class="atl-forced-newline"> </p></td>
<td ><p> The URI of a newly created resource. Sent with a&nbsp;<strong>201 Created</strong> response. <br class="atl-forced-newline"> </p></td>
<td ><p> /api/v2/products/7 <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> X-BC-ApiLimit-Remaining <br class="atl-forced-newline"> </p></td>
<td ><p> All <br class="atl-forced-newline"> </p></td>
<td ><p> An integer. <br class="atl-forced-newline"> </p></td>
<td ><p> The number of API requests remaining for the current period (rolling 1 hour). <br class="atl-forced-newline"> </p></td>
<td ><p> 987 <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td ><p> X-BC-Store-Version<br class="atl-forced-newline"> </p></td>
<td ><p> All<br class="atl-forced-newline"> </p></td>
<td ><p> A version code.<br class="atl-forced-newline"> </p></td>
<td ><p> The version of BigCommerce the store is running on. This header is available from versions 7.3.6+.<br class="atl-forced-newline"> </p></td>
<td ><p> 7.3.6<br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>
