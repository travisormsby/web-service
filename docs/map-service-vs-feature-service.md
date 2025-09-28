# Map service vs Feature service

There are different kinds of services. Most of these differences are based on the type of resource the service makes available. For example, [geoprocessing services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-geoprocessing-service.htm) enable server-side analysis and [print services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/printing-in-web-applications.htm) enable creation of printable files.

[Map services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-map-service.htm) and [feature services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-feature-service-.htm) both provide a REST endpoint for accessing feature data. For both types of services, that endpoint can be used to query the data, access the attribute table, and as an input for analysis tools. But these two types of services provide those capabilities in different ways that are useful for different purposes.

## Response differences
A map service will have a REST endpoint that ends with MapServer. When a client sends a request to this URL, the service responds by sending a rendered image of the data. A feature service, by contrast, will have a REST endpoint that ends with FeatureServer. When a client sends a request to this URL, the service responds by sending the spatial reference, vertex coordinates, and geometry type of the features. The client then renders the geometry.

An image of the data is typically a smaller file size than the geometries themselves. Compared to a feature service, a map service consumes less network bandwidth and is more easily rendered by low-powered client applications. Sending an image of the data also means map services can include both vector and raster data. The advantage of a feature service, on the other hand, is that access to the geometries enables editing of the features. Feature services can also reduce CPU usage by the server by offloading feature rendering to the client.

## Content item differences
Because map and feature services are different kinds of services, they are associated with different types of layer items in the organization. A map service is referenced by a [map image layer](https://enterprise.arcgis.com/en/portal/latest/use/map-image-elevation-imagery-layers.htm#ESRI_SECTION1_E2CAA2B7A0394D75AF58759CC1D070EA), while a feature service is referenced by [feature layer](https://enterprise.arcgis.com/en/portal/latest/use/feature-layers.htm).

## Exercise: Add external services to the portal (10 minutes)

0. Open <a href="https://arcgis.metc.state.mn.us/server/rest/services/ESWastewater/RainGaugeSitesPublic/MapServer" target="_blank">this link</a> (opens in new tab)
0. From the Supported Operations at the bottom of the page, click Export Map
0. For format, select JSON, then click Export Map Image (GET)
0. Copy the URL listed in the href property and navigate to that page
0. In the ArcGIS Online Home app, on the Content tab, click New item
0. Click URL, paste the first URL into the URL box, then click Next
0. Type RainGaugeSites1_<your initials\> for the title, then click Save
0. Open <a href="https://arcgis.metc.state.mn.us/server/rest/services/ESWastewater/RainGaugeSitesPublic/FeatureServer" target="_blank">this link</a> (opens in new tab)
0. From the Supported Operations at the bottom of the page, Click Query
0. For Layer Definitions, copy and paste this value: `[{"layerId": 0, "where": "1=1", "outFields": "SiteName"}]`
0. For format, select JSON, then click Query (GET)
0. Copy the URL for the page with this query response.
0. Repeat the process for adding this URL as an content item to ArcGIS Online, titling the item RainGaugeSites2_<your initials\>
0. Answer these questions:
    0. What kind of service is the first REST endpoint?
    0. How can you be sure of the type of service a REST endpoint provides access for?
    0. Is Export Map a supported operation for the second REST endpoint?
    0. How did the Export Map response on the first service differ from the Query response on the second service?
    0. What kind of layer item was created when you added the first URL?
    0. What kind of layer item was created when you added the second URL?

## Summary
|                       | Map Service	            | Feature Service  |
| --------------------- | ------------------------- | ---------------- |
Analyzable*             | ✔️                        | ✔️              |
Queryable*              | ✔️                        | ✔️              |
Attribute table access* | ✔️                        | ✔️              |
Enables editing*	    | ❌                        | ✔️              |
Geometry rendered by    | Server                    | Client           |
REST endpoint           | MapServer                 | FeatureServer    |
File transfer size      | Generally smaller         | Generally larger |
Associated portal item  | Map image layer           | Feature layer    |

\* If enabled as a capability of the service
