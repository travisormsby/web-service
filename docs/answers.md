## Client vs. Server
0. What was the resource that was requested when you clicked Download? **The .zip archive file**
0. Which application was the client that sent the request? **The browser**
0. Which application was the server that sent the resource? **ArcGIS Online**

## “Portal” vs. “Server”
0. If somebody says “That item isn’t shared to any groups in the portal”, what do they likely mean by “portal”? **They are likely referring to the ability to manage content sharing. They are not referring to the Portal for ArcGIS software, nor a particular app or API they used to manage the item or group.**
0. If somebody says “I installed Server” what do they likely mean by “Server”? **They are likely referring to the ArcGIS Server software. They are probably not referring to a particular installation of that software configured as a specific licensing role nor a particular app or API they used to manage services on that installation.**
0. If somebody says “Go into the portal, click organization, then click members.” what do they likely mean by “portal”? **They are likely referring to the portal Home app, since they describe particular buttons in the app interface. They are not referring generally to the ability to manage users and content, nor to the installation of the Portal for ArcGIS software.**

## Service vs. Layer item
0. How many new content items were created? How many of them were layer items? **Two content items were created. Only one of them was a layer item. The other was a shapefile item.**
0. What is the URL of the REST endpoint for the service you published? **Values will vary, but it should start https://services.arcgis.com**
0. Why is the REST endpoint of the service accessible without logging in? **Because the sharing settings on the associated layer item were set to Everyone.**
0. What is the Item ID of the first layer item you created? **Values will vary, but it should be a 32-character alphanumeric string**
0. Is the service configured to allow editing? **No**

## Layer item vs. Layer
0. How many layers does this layer item have? **One**
0. How does the REST endpoint URL referenced by the first layer compare to the REST endpoint referenced by layer item that contains the layer? **It is the same, except it has a /0 at the end of the URL**
0. What is the Layer ID of the first layer? **0, matching the end of the URL for the layer.**
0. How would you prevent people from viewing the first layer without logging in? **Change the sharing settings on the layer item the layer is contained in**

## Map service vs. Feature service
0. Is the first URL a REST endpoint for a map service or a feature service? How do you know? **A map service. The URL ends MapServer**
0. What kind of layer item was created when you added the first URL? **A map image layer, because the URL is for a map service.**
0. Why were you unable to set a filter in the first layer item? **Because the owners of the service turned off querying capability**
0. Is the second URL a REST endpoint for a map service or a feature service? How do you know? **A feature service. The URL ends FeatureServer**
0. What kind of layer item was created when you added the second URL? **A feature layer, because the URL is for a feature service.**

## Cached vs. Dynamic map service
0. If you have a map service of parcels that are updated quarterly and is used as a basemap by many different users, should that service be cached? **Yes. Quarterly updates to the underlying data mean infrequent cache rebuilding. Large number of users means it is a good idea to minimize the server resources used to respond to requests.**
0. If you have a feature service that is edited annually, should that service be cached? **No. Caching only applies to map services because the image of the data can be pregenerated. The feature geometry of a feature service cannot be cached.**

## Hosted vs. By-reference service
0. An organization wants to expand the number of people who can publish services but is concerned about the additional load on the ArcGIS Server machine. Should they train these new publishers to create hosted services or by-ref services to minimize server machine load? **Hosted. By-ref services require more memory.**
0. A gas utility needs to make sure that the geometry of their features adheres to defined spatial relationships (for example, no overlaps in pipeline features). Should they use an ArcGIS-managed or user-managed datastore for these features? **User-managed. ArcGIS-managed datastores cannot use topology rules to validate feature geometry.** 
