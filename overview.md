#Overview

The Bigcommerce API can both accept requests and respond in JSON or XML. Requests should be encoded using the UTF-8 character set. Other character sets may have unpredictable results. In this document, the examples are shown in the JSON format.

## Request content type 
When performing a request that contains a body (eg. POST or PUT), the type of content you are sending needs to be specified in the Content-Type header. The values for this header are specified in the data types below. For example, to send an xml body, the header would be: Content-Type: application/xml 
