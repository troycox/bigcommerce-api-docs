## HTTP Headers

### Request Headers
The BigCommerce API supports various HTTP headers which are used for authorization, controlling content type. Some headers can be also used for purposes such as increasing performance of your application by only returning responses when content has been modified.
<table class=""><thead><tr class="">
<th class="" data-column="0"><div class=""><p> Header </p></div></th>
<th class="" data-column="1"><div class=""><p> Operations </p></div></th>
<th class="" data-column="2"><div class=""><p> Allowed Values </p></div></th>
<th class="" data-column="3"><div class=""><p> Description </p></div></th>
<th class="" data-column="4"><div class=""><p> Required </p></div></th>
<th class="" data-column="5"><div class=""><p> Example </p></div></th>
</tr></thead><tbody>

<tr>
<td class=""><p> Accept <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests) <br class="atl-forced-newline"> </p></td>
<td class=""><p> The MIME type for the format you want to receive a response in. See the <a href="/display/API/Data+Formats">Data Formats</a> page for details. <br class="atl-forced-newline"> </p></td>
<td class=""><p>&nbsp;</p></td>
<td class=""><p> application/xml <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> Authorization <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> Basic <br class="atl-forced-newline"> </p></td>
<td class=""><p> The user credentials for accessing the API. See the ?<a href="/display/API/Authentication">Authentication</a> page for details. <br class="atl-forced-newline"> </p></td>
<td class=""><p> &nbsp; ? <br class="atl-forced-newline"> </p></td>
<td class=""><p> Basic&nbsp;YWRtaW46cGFzc3dvcmQ= <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> Content-Type <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests) <br class="atl-forced-newline"> </p></td>
<td class=""><p> The MIME type of the request body. Use to validate and parse the request to the API. </p></td>
<td class=""><p> &nbsp; ? <br class="atl-forced-newline"> </p></td>
<td class=""><p> application/json </p></td>
</tr>
<tr>
<td class=""><p> If-Modified-Since </p></td>
<td class=""><p> GET <br class="atl-forced-newline"> </p></td>
<td class=""><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td class=""><p> If supplied, then only resources modified since the specified date will be returned. If there are no modified objects, then a <strong>304 Not Modified</strong> response will be sent. Please refer to the individual resource pages for support for this header. </p></td>
<td class=""><p>&nbsp;</p></td>
<td class=""><p> Tue, 15 Nov 2011 12:45:26 GMT <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> User-Agent </p></td>
<td class=""><p> All </p></td>
<td class=""><p> String </p></td>
<td class=""><p> While it is not required, we ask that you specify a user agent which identifies your integration/client with your requests. </p></td>
<td class=""><p>&nbsp;</p></td>
<td class=""><p>&nbsp;</p></td>
</tr>
</tbody></table>

### Response Headers

<table class=""><thead><tr class="">
<th class="" data-column="0"><div class=""><p> Header </p></div></th>
<th class="" data-column="1"><div class=""><p> Operations </p></div></th>
<th class="" data-column="2"><div class=""><p> Possible Values <br class="atl-forced-newline"> </p></div></th>
<th class="" data-column="3"><div class=""><p> Description </p></div></th>
<th class="" data-column="4"><div class=""><p> Example </p></div></th>
</tr></thead><tbody>

<tr>
<td class=""><p> Date <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td class=""><p> The date the response was sent. <br class="atl-forced-newline"> </p></td>
<td class=""><p> Tue, 15 Nov 2011 12:45:26 GMT </p></td>
</tr>
<tr>
<td class=""><p> Last-Modified </p></td>
<td class=""><p> GET, PUT, POST </p></td>
<td class=""><p> An <a href="http://tools.ietf.org/html/rfc2822#section-3.3" class="external-link" rel="nofollow">RFC 2822</a> date. <br class="atl-forced-newline"> </p></td>
<td class=""><p> The date the resource was last modified. Please refer to the individual resource pages for support for this header. </p></td>
<td class=""><p> Tue, 15 Nov 2011 12:45:26 GMT </p></td>
</tr>
<tr>
<td class=""><p> Content-Type <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> application/json (for .json requests) <br class="atl-forced-newline">
application/xml (for .xml requests, or if no extension is supplied) </p></td>
<td class=""><p> The MIME type of the response, dependent on the extension of the endpoint that was requested. <br class="atl-forced-newline"> </p></td>
<td class=""><p> application/json </p></td>
</tr>
<tr>
<td class=""><p> Content-Location <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> A URI. <br class="atl-forced-newline"> </p></td>
<td class=""><p> Sent if the request was redirected. <br class="atl-forced-newline"> </p></td>
<td class=""><p> /api/v2/orders/5.json <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> WWW-Authenticate <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> Basic <br class="atl-forced-newline"> </p></td>
<td class=""><p> Indicates the authentication scheme that should be used to access the API. Sent with a&nbsp;<strong>401 Unauthorized</strong> response if HTTP Basic authentication credentials weren't supplied. <br class="atl-forced-newline"> </p></td>
<td class=""><p> Basic <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> Location <br class="atl-forced-newline"> </p></td>
<td class=""><p> POST <br class="atl-forced-newline"> </p></td>
<td class=""><p> A URI. <br class="atl-forced-newline"> </p></td>
<td class=""><p> The URI of a newly created resource. Sent with a&nbsp;<strong>201 Created</strong> response. <br class="atl-forced-newline"> </p></td>
<td class=""><p> /api/v2/products/7 <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> X-BC-ApiLimit-Remaining <br class="atl-forced-newline"> </p></td>
<td class=""><p> All <br class="atl-forced-newline"> </p></td>
<td class=""><p> An integer. <br class="atl-forced-newline"> </p></td>
<td class=""><p> The number of API requests remaining for the current period (rolling 1 hour). <br class="atl-forced-newline"> </p></td>
<td class=""><p> 987 <br class="atl-forced-newline"> </p></td>
</tr>
<tr>
<td class=""><p> X-BC-Store-Version<br class="atl-forced-newline"> </p></td>
<td class=""><p> All<br class="atl-forced-newline"> </p></td>
<td class=""><p> A version code.<br class="atl-forced-newline"> </p></td>
<td class=""><p> The version of BigCommerce the store is running on. This header is available from versions 7.3.6+.<br class="atl-forced-newline"> </p></td>
<td class=""><p> 7.3.6<br class="atl-forced-newline"> </p></td>
</tr>
</tbody></table>