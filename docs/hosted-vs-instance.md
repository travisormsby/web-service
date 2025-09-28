# Hosted vs. instance-based service

For map and feature services, there are two different technologies that enable turning feature classes on disk into services accessible from a REST endpoint. 

## Hosted services
Feature services published to ArcGIS Online are considered “hosted”. This phrasing means more than just saying that ArcGIS Online generically serves as a host for data and services. It refers to a particular technology that makes resources available as web services. This technology provides only limited control over the service configuration and requires that the underlying data be copied to a specially optimized ArcGIS-managed data store.

You can also publish hosted services to ArcGIS Enterprise because you can create your own ArcGIS-managed data stores. 

|Hosted service type|Data store|
|---|---|
|Hosted feature service|Relational or spatiotemporal big data store|
|Hosted image service|Raster store|
|Hosted 3D scene service|Tile cache (before version 11.4) or object store (11.4 and later)|
|Hosted vector tile service|Hosting server file system|

When you publish a hosted service to ArcGIS Enterprise, the data must be copied into one of these specialized data stores.

The main benefit of a hosted service is that it is very memory efficient. You can have many hosted services for a small memory footprint. Hosted services are also automatically tuned and optimized by the ArcGIS system. For that reason, there isn't much you can configure for hosted services.

## Instance-based services
ArcGIS Enterprise also supports a second type of service based on the same technology that powers ArcGIS Pro. These types of services go by several different names, depending on who you ask:

- By-reference (or by-ref) service
- Non-hosted service
- ArcGIS Server service
- ArcObjects service
- ArcSOC (or SOC) service

Because the settings for these services largely depends on what Server Manager calls intances, this workshop will refer to them as instance-based services.

The most important implication of using instance-based services is that they do not need to reference data in a specially-optimized ArcGIS-managed storage location. The data might be stored in a variety of supported databases, network shares, cloud store, or local file directories. This flexibility is only available in ArcGIS Enterprise. ArcGIS Online does not support instance-based services.

One benefit of an instance-based service comes from using a data store that you have full control over. With instance-based services there is no need to copy data, and you can take advantage of the capabilities of user-managed data stores that ArcGIS-managed data stores do not have (like versioning, topology, or direct SQL access). Another advantage is that you also get substantially more control over the precise service configuration than you do with hosted services.

## Questions
0. An organization wants to expand the number of people who can publish services but is concerned about the using too much memory on the ArcGIS Server machine. Which type of service will minimize the memory footprint of services?
0. A gas utility needs to make sure that the geometry of their features adheres to defined spatial relationships (for example, no overlaps in pipeline features). Which type of service enables topology rules?

## Summary
|                                   | Hosted service       | By-reference service        |
| --------------------------------- | -------------------- | --------------------------- |
| **Data**                          | ArcGIS-managed       | User-managed                |
| **Service configuration options** | Few                  | Many                        |
| **RAM usage**                     | Much less            | Much more                   |
| **Corresponding layer item**      | Specifies “(hosted)” | No additional specification |
| **Publish to ArcGIS Online**      | ✔️                   | ❌                         |
| **Publish to ArcGIS Enterprise**  | ✔️                   | ✔️                         |

|                          | ArcGIS-managed data | User-managed data        |
| ------------------------ | ------------------- | ------------------------ |
| **Storage technology**   | Chosen by Esri	     | Chosen by user           |
| **Backups/Updates**      | Managed by user     | Managed by user          |
| **Versioning/Archiving** | ❌                  | If supported by database |
| **Topology**             | ❌                  | If supported by database |
| **Direct SQL Access**    | ❌                  | If supported by database |
