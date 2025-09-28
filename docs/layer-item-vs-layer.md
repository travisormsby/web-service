# Layer item vs. Layer

When publishing a service, it is possible to include multiple layers into that single service. That service will have a single configuration that applies to all the layers. The service will be referenced in the portal by a layer item. A single layer item might therefore reference multiple individual layers.

Confusingly, people sometimes say “layer” when they mean “layer item”. If somebody says "layer" it can be hard to know if they mean a layer item or a layer contained within that layer item. Layers are also called sublayers to help differentiate them from the layer item they are contained within. To understand the difference, you can think of a layer item like a group layer in ArcGIS Pro. In fact, if you add a layer item to ArcGIS Pro, it will come into the map as a group layer that includes all the sublayers in that layer item.  

Sublayers do not have their own Item ID, and you do not manage access to them individually. Sharing, tags, and categories are a property of the layer item, and apply equally to all the sublayers within it. You do have control over the representation of individual sublayers by separately configuring their symbology, filters, and popups.

Even though sublayers do not have an Item ID in the portal, they do have a unique Layer ID. This Layer ID allows each sublayer to reference its own unique REST endpoint, with the Layer ID at the end of the general service URL. This unique REST endpoint means that sublayers can be added individually to a map, separate from other sublayers in the same layer item. If the Layer ID for a sublayer ever changes, maps and apps that reference the sublayer’s previous URL will break. For that reason, it is extremely important to maintain Layer ID stability. This is why you must [allow assignment of unique numeric IDs](https://pro.arcgis.com/en/pro-app/latest/help/sharing/overview/assign-layer-ids.htm) in an ArcGIS Pro map before publishing layers from that map.

## Exercise: Investigate a layer (5 minutes)
0. Open the Item Details page for the RainGaugeSites item you created earlier
0. Click on the first layer in the Layers section
0. Copy the URL for the REST endpoint of this layer and paste it into a private/incognito browser tab
0. Answer these questions:
    0. How many sublayers does this layer item have?
    0. How does the REST endpoint URL referenced by the first sublayer compare to the REST endpoint referenced by layer item that contains the sublayer?
    0. What is the Layer ID of the first sublayer?
    0. How would you prevent people from viewing the first sublayer without logging in?

## Summary
|                                       | Layer item | Layer |
| ------------------------------------- | ---------- | ----- |
| Item ID                               | ✔️         | ❌   |
| Layer ID                              | ❌         | ✔️   |
| References a unique REST endpoint URL	| ✔️         | ✔️   |
| Sometimes called a layer              | ✔️         | ✔️   | 
| Sometimes called a sublayer           | ❌         | ✔️   |