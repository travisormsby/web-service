In the ArcGIS context, there are several different components that include “portal” or “server” in their name, which makes it hard to know exactly what these terms might mean. They could be referencing software components you install, the capabilities provided by that software, or the applications users interact with to access those capabilities.

## Software you install
[Portal for ArcGIS](https://enterprise.arcgis.com/en/portal/latest/install/windows/welcome-to-the-portal-for-arcgis-installation-guide.htm) and [ArcGIS Server](https://enterprise.arcgis.com/en/server/latest/install/windows/welcome-to-the-arcgis-for-server-install-guide.htm) are software components you install on infrastructure you control. Generally you would do this as part of an ArcGIS Enterprise deployment. These are also the names of the processes that run on the infrastructure after you install these components. Sometimes when people use the words "portal" and "server", they are referring those these software components. Because ArcGIS Online is Software-as-a-Service (SaaS), you do not install or configure any software, so there is not equivalent in ArcGIS Online to Portal for ArcGIS or ArcGIS Server. 

## Capabilities provided by software
If you install and configure Portal for ArcGIS, you will get an [ArcGIS Enterprise portal](https://enterprise.arcgis.com/en/portal/latest/administer/windows/what-is-portal-for-arcgis-.htm). You can get an ArcGIS Online portal if you subscribe to that service. Either way, this portal members are named users who have credentials to log into the system. Portal administrators control the [user type](https://doc.arcgis.com/en/arcgis-online/administer/user-types-orgs.htm) and [role](https://doc.arcgis.com/en/arcgis-online/administer/member-roles.htm) of each member. The portal has [sharing options](https://doc.arcgis.com/en/arcgis-online/share-maps/share-items.htm) to control which members have access to which content. It also has [tags](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjDqsLihPr9AhUsAjQIHT2QCKgQFnoECA4QAQ&url=https%3A%2F%2Fwww.esri.com%2Farcgis-blog%2Fproducts%2Farcgis-online%2Fmapping%2Fusing-tags-effectively%2F&usg=AOvVaw2_o433JAXXkcxmujkfq0o5) and [categories](https://doc.arcgis.com/en/arcgis-online/reference/content-categories.htm) to organize items and make them easier to search and discover.  Sometimes when people say "portal" they mean these content and user management capabilities.

When you install and configure ArcGIS Server, you get an ArcGIS Server site. This server site turns GIS resources like feature classes and geoprocessing tools into services that can be accessed through a URL. There are different ArcGIS Server [licensings roles](https://enterprise.arcgis.com/en/server/latest/get-started/windows/about-arcgis-server-licensing-roles.htm), that allow you to configure different ArcGIS Server sites for different purposes (e.g. Image Server, GeoEvent Server, etc). ArcGIS Online doesn't have server licensing roles, but it is likewise able to turn GIS resources into services accessed through a URL. Sometimes when people say "server" they mean this ability to publish a resource so that it is accessible from a URL.

## Web applications accessed by users
ArcGIS Enterprise and ArcGIS Online both have a web application called the portal [Home app](https://enterprise.arcgis.com/en/portal/latest/administer/windows/about-configuring-the-portal-website.htm). This is a web page you can go to that allows you to access the capabilities of your ArcGIS Enterprise or ArcGIS Online portal. You click on buttons in this app to do content and user management. Importantly, the Home app is not the same as the ArcGIS Enterprise or ArcGIS Online portal. It is a user interface for accessing capabilities. These capabilities are also accessible programatically by the [Sharing API](https://developers.arcgis.com/rest/users-groups-and-items/working-with-users-groups-and-items.htm) and would be available even if the Home app did not exist. But sometimes when people say "portal" they mean this Home app interface. 

An ArcGIS Server site will also have a web application that allows you to interact with the capabiltiies of the site. This is called the [Server Manager app](https://enterprise.arcgis.com/en/server/latest/get-started/windows/what-s-included-with-arcgis-server.htm#ESRI_SECTION1_91D60600C361477D9810DFB68270AC72). Similar to the Home app, the Server Manager app is a user interface. The capabilities of the site are also accessible programatically from the [Server Administration API](https://developers.arcgis.com/rest/enterprise-administration/server/overview.htm). Sometimes when people say "server" they mean the Server Manager app.

## Questions
0. If somebody says “That item isn’t shared to any groups in the portal”, what do they likely mean by “portal”?
0. If somebody says “I installed Server” what do they likely mean by “Server”?
0. If somebody says “Go into the portal, click organization, then click members” what do they likely mean by “portal”?

## Summary
|                                         | “Portal”             | “Server”                  |
| --------------------------------------- | -------------------- | --------------------------|
| **Unambiguous meaning**                 |	❌                   | ❌                       |
| **Associated software**                 |	Portal for ArcGIS    | ArcGIS Server             |
| **ArcGIS Enterprise configuration**     |	Enterprise portal    | Depends on licensing role |
| **ArcGIS Online configuration**         |	ArcGIS Online portal |	Controlled by Esri       |
| **User management**                     |	✔️                   | Limited                   |
| **Content management**                  |	✔️                   | Limited                   |
| **Enables publication of web services** | ❌                   | ✔️                       |
| **Interactive access via**              |	Home app             | Server Manager app*       |
| **Programmatic access via**             | Sharing API	Server   | Administration API*       |

\* Not available for ArcGIS Online
