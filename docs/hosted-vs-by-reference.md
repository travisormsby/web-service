For map and feature services, there are two different technologies that enable turning feature classes on disk into services accessible from a REST endpoint.

## Hosted services
Feature services published to ArcGIS Online are considered “hosted”. This phrasing means more than just saying that ArcGIS Online generically serves as a host for data and services. It refers to a particular technology that makes resources available as web services. This technology provides only limited control over the service configuration and requires that the underlying data be copied to a specially optimized ArcGIS-managed data store.

You can also publish hosted services to ArcGIS Enterprise because you can create your own ArcGIS-managed data stores. The relational and spatiotemporal data stores both support hosted feature services, the tile cache data store supports hosted 3D scene services, and raster data stores support hosted image services. When you publish a hosted service to ArcGIS Enterprise, the data must be copied into one of these specialized data stores.

The main benefit of a hosted service is that it uses dramatically less RAM than a by-ref service. Hosted services are also automatically tuned and optimized by the ArcGIS system. 

## By-reference services
Unlike ArcGIS Online, ArcGIS Enterprise also supports a second type of service, which is often called a by-reference (or by-ref) service. These services use a different technology that does not require a specialized data store. The data might be stored in an enterprise geodatabase, a network share, a cloud store, or even just a directory on the ArcGIS Server machine.

The main benefit of a by-ref service comes from using a data store that you have full control over. With by-ref services there is no need to copy data, and you can take advantage of the capabilities of user-managed data stores (like versioning, topology, or direct SQL access) that ArcGIS-managed data stores do not have. You also get substantially more control over the precise service configuration than you do with hosted services.

## Questions
0. An organization wants to expand the number of people who can publish services but is concerned about the additional load on the ArcGIS Server machine. Should they train these new publishers to create hosted services or by-ref services to minimize server machine load?
0. A gas utility needs to make sure that the geometry of their features adheres to defined spatial relationships (for example, no overlaps in pipeline features). Should they use an ArcGIS-managed or user-managed datastore for these features?

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
