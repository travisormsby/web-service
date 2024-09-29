# Answers

## Client vs. Server
0. What was the resource that was requested when you clicked Download? **The .zip archive file**
0. Which application was the client that sent the request? **My browser**
0. Which application was the server that sent the resource? **Minnesota Geospatial Commons**

## “Portal” vs. “Server”
0. If somebody says “That item isn’t shared to any groups in the portal”, what do they likely mean by “portal”? **Content management capabilities provided by the Portal for ArcGIS software**
0. If somebody says “I installed Server” what do they likely mean by “Server”? **The ArcGIS Server software**
0. If somebody says “Go into the portal, click organization, then click members.” what do they likely mean by “portal”? **The portal Home web app**

## Service vs. Layer item
0. What is the Item ID of the first layer item you created? **Values will vary, but it should be a 32-character alphanumeric string**
0. How many new content items were created? **2**
0. How many of them were layer items? **1**
0. What is the URL of the REST endpoint for the service you published? **Values will vary, but it should start end `/FeatureServer`**
0. Why is the REST endpoint of the service accessible without logging in? **Because the sharing level on the associated layer item was set to Everyone.**
0. Among the supported operations for the layer, which editing capabilities are supported? **None**

## Layer item vs. Layer
0. How many layers does this sublayer item have? **1**
0. How does the REST endpoint URL referenced by the first sublayer compare to the REST endpoint referenced by layer item that contains the sublayer? **It is Similar, but with a /0 at the end**
0. What is the Layer ID of the first sublayer? **0**
0. How would you prevent people from viewing the first sublayer without logging in? **Change the sharing settings on the layer item the layer is contained in**

## Map service vs. Feature service
0. What kind of service is the first REST endpoint? **Map Service**
0. How can you be sure of the type of service a REST endpoint provides access for? **Because the URL ends with MapServer**
0. Is Export Map a supported operation for the second REST endpoint?
0. How did the Export Map response on the first service differ from the Query response on the second service? **Export map on a Map Service returned an image. Query on a Feature Service returned feature geometry**
0. What kind of layer item was created when you added the first URL? **Map Image Layer**
0. What kind of layer item was created when you added the second URL? **Feature Layer**


## Cached vs. Dynamic map service
0. If you have a map service of parcels that are updated quarterly and is used as a basemap by many different users, should that service be cached? **Yes. Quarterly updates to the underlying data mean infrequent cache rebuilding. Large number of users means it is a good idea to minimize the server resources used to respond to requests.**
0. If you have a feature service that is edited annually, should that service be cached? **No. Caching only applies to map services because the image of the data can be pregenerated. The feature geometry of a feature service cannot be cached in the same way.**

## Hosted vs. By-reference service
0. An organization wants to expand the number of people who can publish services but is concerned about the additional load on the ArcGIS Server machine. Should they train these new publishers to create hosted services or by-ref services to minimize server machine load? **Hosted. By-ref services require more memory.**
0. A gas utility needs to make sure that the geometry of their features adheres to defined spatial relationships (for example, no overlaps in pipeline features). Should they use an ArcGIS-managed or user-managed datastore for these features? **User-managed. ArcGIS-managed datastores cannot use topology rules to validate feature geometry.** 
