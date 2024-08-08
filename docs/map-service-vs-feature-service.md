There are different kinds of services. Most of these differences are based on the type of resource the service makes available. For example, [geoprocessing services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-geoprocessing-service.htm) enable server-side analysis and [print services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/printing-in-web-applications.htm) enable creation of printable files.

[Map services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-map-service.htm) and [feature services](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-a-feature-service-.htm) both provide a REST endpoint for accessing feature data. For both types of services, that endpoint can be used to query the data, access the attribute table, and as an input for analysis tools. But these two types of services provide those capabilities in different ways that are useful for different purposes.

## Response differences
A map service will have an endpoint that ends with MapServer. When a client sends a request to this URL, the service responds by sending a rendered image of the data. A feature service, by contrast, will have an endpoint that ends with FeatureServer. When a client sends a request to this URL, the service responds by sending the spatial reference, vertex coordinates, and geometry type of the features. The client then renders the geometry.

An image of the data is typically a smaller file size than the geometries themselves. Compared to a feature service, a map service consumes less network bandwidth and is more easily rendered by low-powered client applications. Sending an image of the data also means map services can include both vector and raster data. The advantage of a feature service, on the other hand, is that access to the geometries enables editing of the features.

## Portal item differences
Because map and feature services are different kinds of services, they are associated with different types of layer items in the portal. A map service is referenced by a [map image layer](https://enterprise.arcgis.com/en/portal/latest/use/map-image-elevation-imagery-layers.htm#ESRI_SECTION1_E2CAA2B7A0394D75AF58759CC1D070EA), while a feature service is referenced by [feature layer](https://enterprise.arcgis.com/en/portal/latest/use/feature-layers.htm).

## Exercise: Add external services to the portal
0. Open this URL in a new browser tab: [tinyurl.com/bdf669eb](tinyurl.com/bdf669eb)
0. Copy the full URL of the service
0. Under Layers, click the RainGaugeSites link
0. Scroll down to the bottom and review the supported operations. The owners of this service could have turned on the Query capability but chose to disable it.
0. In ArcGIS Online, on the Content tab, click the New item button
0. Click URL, copy the full URL of the service into the URL field, then click Next
0. In the Title field, type RainGaugeSitesMIL_<your initials>, then click Save
0. From the Item Details page, select Open in Map Viewer
0. Interact with the layer by panning, zooming, and attempting to set a filter
0. Repeat steps 1 – 9 with this URL (giving the item a unique name): [tinyurl.com/376anu3y](tinyurl.com/376anu3y)
0. Answer these questions:
    0. Is the first URL a REST endpoint for a map service or a feature service? How do you know?
    0. What kind of layer item was created when you added the first URL?
    0. Why weren’t you able to set a filter in the first layer item?
    0. Is the second URL a REST endpoint for a map service or a feature service? How do you know?
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
