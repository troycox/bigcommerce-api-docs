## Overview
The HTTP OPTIONS method can be used to discover the capabilities and requirements of resources in the BigCommerce API. The OPTIONS method itself is defined as follows according to the HTTP/1.1 spec:

	The OPTIONS method represents a request for information about the communication options available on the request/response chain identified by the Request-URI. This method allows the client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without implying a resource action or initiating a resource retrieval.

	http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html

The BigCommerce API uses the OPTIONS method to describe the methods which are available for a certain resource (such as GET, POST, PUT and DELETE) as well as the resource-specific fields and their various properties. A smart or dynamic client can utilise this method to discover which methods are available for a resource, which fields are available or required for a method and the data requirements for each field.

Unless noted otherwise, the OPTIONS method is available for all BigCommerce API resources.

The response headers for an OPTIONS request will contain an Allow header describing (as a CSV) a list of permitted HTTP methods for the requested resource, while the response-body will contain a list of fields entities as described below.

It is important to note that the methods and fields described by OPTIONS will most certainly differ between a listing resource and it's related entity resources (such as <code>/brands.xml</code> versus <code>/brands/1.xml</code>). This is demonstrated in the examples below.

## Fields

<table class="confluenceTable tablesorter"><thead><tr class="sortableHeader">
<th class="confluenceTh sortableHeader" data-column="0"><div class="tablesorter-header-inner"><p> API Field </p></div></th>
<th class="confluenceTh sortableHeader" data-column="1"><div class="tablesorter-header-inner"><p> API Data Type </p></div></th>
<th class="confluenceTh sortableHeader" data-column="2"><div class="tablesorter-header-inner"><p> Field Description </p></div></th>
</tr></thead><tbody>

<tr>
<td class="confluenceTd"><p> name </p></td>
<td class="confluenceTd"><p> string </p></td>
<td class="confluenceTd"><p> The name of the API field being described. This name maps directly to the input and output fields for the resource. </p></td>
</tr>
<tr>
<td class="confluenceTd"><p> type </p></td>
<td class="confluenceTd"><p> string </p></td>
<td class="confluenceTd"><p> The API Data Type of the field being described. The types referred to by this field can be seen in the <a href="/display/API/Data+Types">Data Types</a> documentation. </p></td>
</tr>
<tr>
<td class="confluenceTd"><p> length </p></td>
<td class="confluenceTd"><p> int | string </p></td>
<td class="confluenceTd"><p> For types which are limited in length, this described the length limitation of this field. For example, a string field with a length of 50 will only accept up to 50 characters, while a decimal field with a length of "20,4" will only accept numbers up to 20 total digits (including the digits after the decimal point). For more information, please refer to the <a href="/display/API/Data+Types">Data Types</a> documentation. <br class="atl-forced-newline">
<br class="atl-forced-newline">
The length will not be present for field types where the length is not applicable (such as text fields and the various integer types). </p></td>
</tr>
<tr>
<td class="confluenceTd"><p> writable_methods </p></td>
<td class="confluenceTd"><p> array </p></td>
<td class="confluenceTd"><p> A list of HTTP methods for which this field can be written to. This list may be empty for fields which are completely read-only - the <code>id</code> field is a typical example of this. </p></td>
</tr>
<tr>
<td class="confluenceTd"><p> required_methods </p></td>
<td class="confluenceTd"><p> array </p></td>
<td class="confluenceTd"><p> A list of HTTP methods for which this field is a required field. For example, the <code>name</code> field on the <code>brands</code> resource is required for <code>POST</code> requests. </p></td>
</tr>
</tbody></table>

## Examples

### OPTIONS Response for a Listing Resource

An OPTIONS request on the optionsets listing may look something like this.
	
	curl --user apiUsername:apiToken --request OPTIONS https://www.example.com/api/v2/optionsets.xml

	HTTP/1.1 200 OK
	Status: 200 OK
	Allow: GET, POST, DELETE, HEAD, OPTIONS
	Content-Type: application/xml

	<?xml version="1.0" encoding="UTF-8"?>
	<options>
	  <fields>
	    <field>
	      <name>id</name>
	      <type>int</type>
	      <writable_methods/>
	      <required_methods/>
	    </field>
	    <field>
	      <name>name</name>
	      <type>string</type>
	      <length>255</length>
	      <writable_methods>
	        <value>POST</value>
	      </writable_methods>
	      <required_methods>
	        <value>POST</value>
	      </required_methods>
	    </field>
	    <field>
	      <name>options</name>
	      <type>resource</type>
	      <writable_methods/>
	      <required_methods/>
	    </field>
	  </fields>
	</options>

### OPTIONS Response for an Entity Resource

An OPTIONS request on an optionsets entity resource may look something like this. Note the difference in the responses between <code>/optionsets.xml</code> and <code> /optionsets/123.xml </code>.

	curl --user apiUsername:apiToken --request OPTIONS https://www.example.com/api/v2/optionsets/123.xml

	
	<?xml version="1.0" encoding="UTF-8"?>
	<options>
	  <fields>
	    <field>
	      <name>id</name>
	      <type>int</type>
	      <writable_methods/>
	      <required_methods/>
	    </field>
	    <field>
	      <name>name</name>
	      <type>string</type>
	      <length>255</length>
	      <writable_methods>
	        <value>PUT</value>
	      </writable_methods>
	      <required_methods>
	        <value>PUT</value>
	      </required_methods>
	    </field>
	    <field>
	      <name>options</name>
	      <type>resource</type>
	      <writable_methods/>
	      <required_methods/>
	    </field>
	  </fields>
	</options>