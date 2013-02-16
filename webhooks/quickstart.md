## Bigcommerce Webhooks Quickstart
=======
This document presents an overview on what webhooks are and how how you can use it with a Bigcommerce store.

### Webhooks
Think push notification for the web. Assume you want to track various events that occur in a Bigcommerce store - checkout, order, price change, shipping events, etc. You might have built a kick-ass backend service that can act on these events and run some sort of script and analytics. Webhooks enable you to accomplish this.

In a nutshell, you are telling Bigcommerce to notify you when an event occurs in a Bigcommerce store. For this notification to be successful, you provide a script hosted on your web servers (potentially being part of your existing web app).

#### Endpoint
Currently the beta test endpoint for webhooks is at https://hooks-beta.bigcommerce.com

#### Events/Scopes currently available
1. store/order/* (all events on the order resource)
2. store/order/created
3. store/order/updated
4. store/order/archived
5. store/order/statusUpdated
6. store/product/* (all events on the product resource)
7. store/product/created
8. store/product/updated
9. store/product/deleted
10. store/customer/* (all events on the customer resource)
10. store/customer/created
11. store/customer/updated
12. store/customer/deleted
13. store/app/uninstalled

<a href="/api/event_triggers.md">This page</a> describes in detail the specific triggers for each of the event scopes.

### Provisioning webhooks
Currently webhoooks is in beta and access is by invite only. If you have a strong use case and require access to webhooks, please get in touch with us. When you navigate to https://devportal.bigcommerce.com/beta/wehooks you will be able to provision webhooks for your account. 

![Image](images/webhooks_provision.png?raw=true) 

A client ID and secret will be created for you in your dashboard as shown in the screenshot above.

Once you have provisioned webhooks, you can start subscribing to events from the above events list. However, before doing that, you need an 'access_token'. You can generate the access token via a POST request on the /token endpoint. The POST request will contain the fields - client_id, client_secret, user, token, store_domain. The client_id and client_secret are provided to you by the dev portal where as user, token and store_domain are your API credentials that you have traditionally used to make API requests.

<pre>
   curl -XPOST -d '{"client_id":"client123","client_secret":"client123secret","user":"admin","token":"xxxx","store_domain":"https://store-xxxx.mybigcommerce.com"}' https://hooks-beta.bigcommerce.com/token 
</pre>

This will provide a response that contains the access_token and a producer, which is the same as the store id.

<pre> {"access_token":"12345","producer":"store/foobar123"} </pre>

### Events

To subscribe to events you would make a POST request with the following fields - producer, scope, deliverymethod, destination. You also need to define two header fields <code>X_AUTH_CLIENT_ID</code> whose value will be the client_id you generated for your app via the Dev Portal (as described above) and <code>X_AUTH_TOKEN</code> which has the above generated access_token's value.

<pre>
    curl -XPOST -d '{"producer":"store/xxxx","scope":"products/*","deliverymethod":"HTTP_POST","destination":{"url":"http://requestb.in/nf4nqbnf"}}' -H 'X_AUTH_CLIENT_ID: client123' -H 'X_AUTH_TOKEN: 12345' https://hooks-beta.bigcommerce.com
</pre>

The above example demonstrates how you can subscribe for product updates. Make a note of the "destination" field in the request. This is a JSON object containing a "url" field. Make sure you point this to the location where Bigcommerce sends you notifications. If everything goes well, you will see the following response -

<pre>
    {"client_id":"client123","created_at":"2013-02-12T17:33:04+00:00","deliverymethod":"HTTP_POST","destination":{"url":"http://requestb.in/nf4nqbnf"},"id":33,"producer":"store/xxxx","scope":"products/*","updated_at":"2013-02-12T17:33:04+00:00"}
</pre>

### Things to remember regarding Payload

1. In the postback, we send a light payload with only minimum details regarding the events that got triggered. It's up to you how you want to handle the notification in your application. For instance, we will send you details indicating that a product was updated, and you might want to handle it by fetching the new product via an API call.
2. Bulk data imports will trigger the relevant events for every record affected. For example, if you have a hook on store/product/create and then the merchant imports 2,000 products, then there will be 2,000 event postbacks. 
3. Payloads are serialized per hook per store. We are looking at enabling a replay feature down the road. What this means is, based on the serialized payload IDs, 3rd parties can detect if they've missed certain postbacks and then they, via a future update, you will be able call a replay method to get the missing events. 
