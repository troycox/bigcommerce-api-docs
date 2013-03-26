## API changelog

### v2 changes
#### 2/12/2013
1. Coupons API rolled out. This update gives an ability to create and manage coupons via API.
2. GET Store settings via API. This update gives an ability to query store data via API.

#### Things that are different in v2 API compared to v1

<table class="table table-bordered"><thead><tr >
<th  data-column="0"><div ><p> Change </p></div></th>
<th  data-column="1"><div ><p> v1 </p></div></th>
<th  data-column="2"><div ><p> v2 </p></div></th>

</tr></thead><tbody>

<tr>
<td ><p> Requesting data  </p></td>
<td ><p> In v1, requesting store data was always a POST operation. The API credentials were sent as part of XML payload</p></td>
<td ><p> In v2, basic auth is used for authentication. The API is RESTful, supports GET, POST, PUT and DELETE verbs</p></td>
</tr>

<tr>
<td ><p> Resources </p></td>
<td ><p> In v1, API methods were part of the XML payload. All request were directed to a single endpoint. The resource name was specified under <code> <requestmethod>GetOrders</requestmethod></code></p></td>
<td ><p> In v2, the resources are specified by request uri</p></td>
</tr>

<tr>
<td ><p> Response </p></td>
<td ><p> In v1, XML was the only supported response</code></p></td>
<td ><p> In v2, responses can be requested in JSON and XML</p></td>
</tr>

<tr>
<td ><p> Errors </p></td>
<td ><p> In v1, the errors were sent via XML payload with a node - STATUS that indicated failure</p></td>
<td ><p> In v2, the errors comply with standard HTTP conventions as it is norm with REST APIs</p></td>
</tr>

<tr>
<td ><p> Endpoint </p></td>
<td ><p> In v1, the base url for API access was https://store.com/xml.php</p></td>
<td ><p> In v2, the base url for API access is https://store.com/api/v2</p></td>
</tr>

<tr>
<td ><p> Resources </p></td>
<td ><p> In v1, the API supported products, orders and customers resources.</p></td>
<td ><p> In v2, the API supports an extended set of resources.</p></td>
</tr>

</tbody></table>