---
title: Custom roles for role-based access control
description: Learn how to manage custom roles in the Microsoft Defender portal
ms.service: defender-xdr
f1.keywords: 
  - NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 03/04/2024
manager: dansimp
audience: ITPro
ms.collection: 
- m365-security
- tier3
ms.topic: conceptual
search.appverid: 
  - MOE150
  - MET150
---
# Custom roles in role-based access control for Microsoft Defender XDR

> [!NOTE]
> Microsoft Defender XDR users can now take advantage of a centralized permissions management solution to control user access and permissions across different Microsoft security solutions. Learn more about the [Microsoft Defender XDR Unified role-based access control (RBAC)](manage-rbac.md).

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**Applies to:**

- Microsoft Defender XDR

[!INCLUDE [Microsoft Defender XDR rebranding](../includes/microsoft-defender.md)] 

There are two types of roles that can be used to access to Microsoft Defender XDR:

- **Global Microsoft Entra roles**
- **Custom roles**

Access to Microsoft Defender XDR can be managed collectively by using [Global roles in Microsoft Entra ID](m365d-permissions.md)

If you need greater flexibility and control over access to specific product data, Microsoft Defender XDR access can also be managed with the creation of Custom roles through each respective security portal.

For example, a Custom role created through Microsoft Defender for Endpoint would allow access to the relevant product data, including Endpoint data within the Microsoft Defender portal. Similarly, a Custom role created through Microsoft Defender for Office 365 would allow access to the relevant product data, including Email & collaboration data within the Microsoft Defender portal.

Users with existing Custom roles can access data in the Microsoft Defender portal according to their existing workload permissions with no additional configuration required.

## Create and manage custom roles

Custom roles and permissions can be created and individually managed through each of the following security portals:

- Microsoft Defender for Endpoint – [Edit roles in Microsoft Defender for Endpoint](/defender-endpoint/user-roles)
- Microsoft Defender for Office 365 – [Permissions in the Security & Compliance Center](/defender-office-365/scc-permissions?preserve-view=true&view=o365-worldwide)
- Microsoft Defender for Cloud Apps – [Manage admin access](/cloud-app-security/manage-admins)

Each custom role created through an individual portal allows access to the data of the relevant product portal. For example, a custom role created through Microsoft Defender for Endpoint will only allow access to Defender for Endpoint data.

> [!TIP]
> Permissions and roles can also be accessed through the Microsoft Defender portal by selecting Permissions & roles from the navigation pane. Access to Microsoft Defender for Cloud Apps is managed through the Defender for Cloud Apps portal and controls access to Microsoft Defender for Identity as well.  See [Microsoft Defender for Cloud Apps](/cloud-app-security/manage-admins)

> [!NOTE]
> Custom roles created in Microsoft Defender for Cloud Apps have access to Microsoft Defender for Identity data as well. Users with User group admin, or App/instance admin Microsoft Defender for Cloud Apps roles are not able to access Microsoft Defender for Cloud Apps data through the Microsoft Defender portal.

<a name='manage-permissions-and-roles-in-the-microsoft-365-defender-portal'></a>

## Manage permissions and roles in the Microsoft Defender portal

Permissions and roles can also be managed in the Microsoft Defender portal:

1. Sign in to the Microsoft Defender portal at security.microsoft.com.
2. In the navigation pane, select **Permissions & roles**.
3. Under the **Permissions** header, select **Roles**.

> [!NOTE]
> This only applies to Defender for Office 365 and Defender for Endpoint. Access for other workloads must be done in their relevant portals.

## Required roles and permissions

The following table outlines the roles and permissions required to access each unified experience in each workload. Roles defined in the table refer to custom roles in individual portals and aren't connected to global roles in Microsoft Entra ID, even if similarly named.

> [!NOTE]
> Incident management requires management permissions for all products that are part of the incident.

> [!IMPORTANT]
> Microsoft recommends that you use roles with the fewest permissions. This helps improve security for your organization. Global Administrator is a highly privileged role that should be limited to emergency scenarios when you can't use an existing role.

|Microsoft Defender XDR workload|One of the following roles is required for Defender for Endpoint|One of the following roles is required for Defender for Office 365|One of the following roles is required for Defender for Cloud Apps and Defender for Identity | One of the following roles is required for Microsoft Defender for Cloud |
|---|---|---|---|---|
|Viewing investigation data: <ul><li>Alert page</li> <li>Alerts queue</li> <li>Incidents</li>  <li>Incident queue</li> <li>Action center</li></ul>|View data- security operations|<ul><li>View-only Manage alerts </li> <li>Organization configuration</li><li>Audit logs</li> <li>View-only audit logs</li> <li>Security reader</li> <li>Security admin</li><li>View-only recipients</li></ul>|<ul><li>Global admin</li> <li>Security admin</li> <li>Compliance admin</li> <li>Security operator</li> <li>Security reader</li> <li>Global reader</li></ul>|<ul><li>Global admin</li><li>Security admin</li></ul> |
|Viewing hunting data, saving, editing, and deleting hunting queries and functions|View data- security operations|<ul><li>Security reader</li> <li>Security admin</li> <li>View-only recipients</li>|<ul><li>Global admin</li> <li>Security admin</li> <li>Compliance admin</li> <li>Security operator</li> <li>Security reader</li> <li>Global reader</li></ul>|<ul><li>Global admin</li><li>Security admin</li></ul> |
|Managing alerts and incidents|Alerts investigation|<ul><li>Manage alerts</li> <li>Security admin</li>|<ul><li>Global admin</li> <li>Security admin</li> <li>Compliance admin</li> <li>Security operator</li> <li>Security reader</li></ul>|<ul><li>Global admin</li><li>Security admin</li></ul> |
|Action center remediation|Active remediation actions – security operations|Search and purge||<ul><li>Global admin</li><li>Security admin</li></ul> |
|Setting custom detections|Manage security settings|<ul><li>Manage alerts</li> <li>Security admin</li></ul>|<ul><li>Global admin</li> <li>Security admin</li> <li>Compliance admin</li> <li>Security operator</li> <li>Security reader</li> <li>Global reader</li></ul>|<ul><li>Global admin</li><li>Security admin</li></ul> |
|Threat Analytics|Alerts and incidents data: <ul><li>View data- security operations</li></ul>Defender Vulnerability Management mitigations:<ul><li>View data - Threat and vulnerability management</li></ul>|Alerts and incidents data:<ul> <li>View-only Manage alerts</li> <li>Manage alerts</li> <li>Organization configuration</li><li>Audit logs</li> <li>View-only audit logs</li><li>Security reader</li> <li>Security admin</li><li>View-only recipients</li> </ul> Prevented email attempts: <ul><li>Security reader</li> <li>Security admin</li><li>View-only recipients</li>|<ul><li>Global admin</li> <li>Security admin</li> <li>Compliance admin</li> <li>Security operator</li> <li>Security reader</li> <li>Global reader</li></ul>|<ul><li>Global admin</li><li>Security admin</li></ul> |

For example, to view hunting data from Microsoft Defender for Endpoint, View data security operations permissions are required.

Similarly, to view hunting data from Microsoft Defender for Office 365, users would require one of the following roles:

- View data security operations
- Security reader
- Security admin
- View-only recipients

## Related articles

- [RBAC roles](/defender-office-365/migrate-to-defender-for-office-365-onboard#rbac-roles)
- [Manage access to Microsoft Defender XDR](m365d-permissions.md)
- [Manage admin access for Defender for Cloud Apps](/cloud-app-security/manage-admins)
[!INCLUDE [Microsoft Defender XDR rebranding](../includes/defender-m3d-techcommunity.md)]
