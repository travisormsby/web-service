# Client vs. Server

A client is an application that sends a request for a resource to some other application and receives that resource in response. That other application is called a server. Sometimes people use the words “client” and “server” to refer to the machines on which these applications run, but it is more accurate to say that clients and servers are software, not hardware. It might even be the case that a single application sometimes acts as a client by sending requests and sometimes acts as a server by responding to requests.

In the ArcGIS system, clients are typically a web browser, [ArcGIS Pro](https://www.esri.com/en-us/arcgis/products/arcgis-pro/overview), or a mobile app. When you type a URL into the browser or drag a portal content item into a map, you are using the client to make a request on that resource. [ArcGIS Online](https://www.esri.com/en-us/landing-page/product/2019/arcgis-online/overview) and [ArcGIS Enterprise](https://www.esri.com/en-us/arcgis/products/arcgis-enterprise/overview) are typically the servers. They will receive a request from the client and provide the resource.

![Client-Server relationship](images/client-server.png)

## Exercise: Make a request for a resource (5 minutes)
0.	[Navigate to the Areas Served by Wastewater Facilities in Minneosta](https://gis.data.mn.gov/datasets/86ec22a22b9b46f6b1172dbf659b72c3_0/explore) in the Minnesota Geospatial Commons.
0.	Download the geopackage version of this data set
0. Answer these questions
    0. What was the resource that was requested when you clicked Download?
    0. Which application was the client that sent the request?
    0. Which application was the server that sent the resource?

## Summary
|              | Client    | Server    |
| ------------ | --------- | --------- |
| **Sends**    | Requests  | Responses | 
| **Receives** | Responses | Requests  |
