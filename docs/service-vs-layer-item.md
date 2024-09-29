# Service vs. Layer item

Sometimes people will use the words "service" and "layer" interchangeably. But they are not the same.

## Service
A [service](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/services-in-arcgis-enterprise.htm) defines a set of capabilities. What will you be allowed to do with a resource? Will you be able to edit data? Can you upload local data for analysis? Are you allowed to export the data? Any questions about capabilities are answered by the service configuration. In ArcGIS Enterprise, you publish services to an ArcGIS Server site you control. In ArcGIS Online, you publish services to Esri’s servers.

A service makes these capabilities available via a URL that let you use web protocols to access the resource. These URLs are referred to as [REST endpoints](https://developers.arcgis.com/rest/services-reference/enterprise/get-started-with-the-services-directory.htm). Some services also make resources available through a different standard called SOAP, but this is rarely used. In this workshop, you will work only with REST endpoints.

## Layer item
A [layer item](https://doc.arcgis.com/en/arcgis-online/manage-data/add-items.htm) references a particular service, but it does not change that service’s capabilities. You can use a layer item to represent the resource with different symbology, popups, or filters than the service’s default representation. Layer items (unlike services) are items in the portal, so you can also use a layer item to integrate its associated service into the portal’s content management capabilities. In both ArcGIS Online and ArcGIS Enterprise, the typical publishing process involves adding a new layer item to the portal, which automatically creates the associated service for that layer item. 

Because [a layer item is not a service](https://www.esri.com/arcgis-blog/products/arcgis-living-atlas/mapping/give-the-rest-a-rest/), it does not have its own REST endpoint. Instead, it has a unique [Item ID](https://developers.arcgis.com/documentation/glossary/item-id/) and it references the REST endpoint of the underlying service. One important implication of the fact that a layer item sits on top of a service is that there might be multiple layer items that all reference the same service. A second implication is that you can create layer items for any service whose REST endpoint you can access, even if that service exists outside your organization.

## Exercise: Publish a service (10 minutes)

0. Log into ArcGIS Online with the workshop credentials you have
0. In the Home app, click the Content tab
0. Click the New item button, then click Your device
0. Navigate to the location where you downloaded the Rain Gauge Sites shapefile
0. Select the .zip archive then click Open
0. Select the default option to add the file and create a hosted feature layer
0. Title the item RainGaugeSites_<your initials\>, then click Save
0. On the item details page, note the item ID in the URL (it is a 32 character hexadecimal value) 
0. Change the sharing options to share this item with everyone
0. At the bottom of the Overview, copy the URL
0. Navigate back to the Content tab so you can see all the items owned by your username
0. In an incognito browser window, navigate to the URL you copied, then click the link to the RainGaugeSites layer
0. Scroll to the bottom of the page and review the supported operations
0. Answer these questions:
    0. What is the Item ID of the first layer item you created?
    0. How many new content items were created? 
    0. How many of them were layer items?
    0. What is the URL of the REST endpoint for the service you published?
    0. Why is the REST endpoint accessible without logging in?
    0. Among the supported operations for the layer, which editing capabilities are supported? 

## Summary

|                                         |	Service	| Layer Item |
| --------------------------------------- | ------- | ---------- |
| Define what can be done with a resource |	✔️      | ❌        |
| REST endpoint                           |	✔️	    | ❌        |
| Representation of data                  |	✔️      | ✔️        |
| Specify users who can access            |	❌      | ✔️        |
| Tags/Categories                         |	❌      | ✔️        |
| Item ID                                 |	❌      | ✔️        |



