Because a map service responds to visualization requests with an image of the features, it needs to generate that image server-side. A [cached map service](https://enterprise.arcgis.com/en/server/latest/publish-services/windows/what-is-map-caching-.htm) means that every image is generated and then saved. Requests on a cached map service receive this saved image. A dynamic map service draws a new image every time it receives a request.

## Draw time differences
Drawing the image takes time, so a dynamic map service will be slower than a cached map service to respond to requests. But creating the cached map service in the first place is generally much slower, because the cache needs to be drawn. 

## Data update differences
Because a cached map service sends a saved image for every request, it may not reflect the most recent data. The cache would need to be recreated for the image to update. Dynamic map services, however, will always show the most recent edits to the data. For that reason, cached map services are typically best if the data are rarely updated, while dynamic map services are typically best for data that are frequently updated.

## Questions
0. If you have a map service of parcels that are updated quarterly and is used as a basemap by many different users, should that service be cached?
0. If you have a feature service that is edited annually, should that service be cached?

## Summary

|                            | Cached Map Service | Dynamic Map Service |
| -------------------------- | ------------------ | ------------------- |
| Geometry drawn             | On cache creation  |	On every request    |
| Service creation           | Slower             |	Faster              |
| Service response time      | Faster             | Slower              |
| Reflects most recent edits | ❌                 | ✔️                 |
| Best for data that         | Rarely change      |	Often change        |
