---
title: Überwachen der Microsoft 365-Konnektivität
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: In diesem Artikel erfahren Sie mehr über die Tools und Techniken, mit denen Sie die Microsoft 365-Konnektivität überwachen und verwalten können.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690302"
---
# <a name="monitor-microsoft-365-connectivity"></a>Überwachen der Microsoft 365-Konnektivität

Nachdem Sie Microsoft 365 bereitgestellt haben, können Sie die Microsoft 365-Konnektivität mit einigen der unten aufgeführten Tools und Techniken aufrecht erhalten. Sie sollten die offiziellen Richtlinien für den [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) sowie unsere [bewährten Methoden für die Verwendung von Microsoft 365 in einem langsamen Netzwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)verstehen. Sie möchten auch die [Microsoft 365 admin-App](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) nutzen und unsere [Microsoft 365 for Business-Admin-Hilfe](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)mit einem Lesezeichen versehen.
  
## <a name="monitoring-microsoft-365-connectivity"></a>Überwachen der Microsoft 365-Konnektivität

|||
|:-----|:-----|
|**Erhalten einer Benachrichtigung über neue Microsoft 365-Endpunkte** <br/> |Wenn Sie [Microsoft 365-Endpunkte verwalten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), sollten Sie Benachrichtigungen erhalten, wenn wir neue Endpunkte veröffentlichen, können Sie unseren RSS-Feed mit Ihrem bevorzugten RSS-Reader abonnieren. Hier erfahren Sie, wie Sie [über Outlook abonnieren](https://go.microsoft.com/fwlink/p/?LinkId=532416) , oder Sie können [die RSS-Feed-Updates per e-Mail](https://go.microsoft.com/fwlink/p/?LinkId=532417)erhalten.  <br/> |
|**Verwenden von System Center zum Überwachen von Microsoft 365** <br/> |Wenn Sie Microsoft System Center verwenden, können Sie das [System Center Management Pack für Office 365](https://www.microsoft.com/download/details.aspx?id=43708) zum Starten der Überwachung von Microsoft 365 heute herunterladen. Ausführlichere Anleitungen finden Sie im Management Pack-Betriebshandbuch oder in dieser Blogbeitrag- [Office365-Überwachung mithilfe von System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) . <br/> |
|**Überwachen des Zustands von Azure ExpressRoute** <br/> |Wenn Sie eine Verbindung mit Microsoft 365 mithilfe von Azure Express Route für Microsoft 365 herstellen, sollten Sie sicherstellen, dass Sie sowohl das Microsoft 365 Service Health Dashboard als auch das Azure [reduzieren der Problem Behandlungszeit mit Azure-Ressourcen Integrität](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) verwenden. <br/> |
|**Verwenden von Azure AD Connect Health mit AD FS** <br/> |Wenn Sie AD FS für einmaliges Anmelden mit Microsoft 365 verwenden, sollten Sie zunächst [Azure AD Connect-Integrität zum Überwachen Ihrer AD FS-Infrastruktur verwenden](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).  <br/> |
|**Programmgesteuertes Überwachen von Microsoft 365** <br/> |Lesen Sie unsere Anleitung zur [Microsoft 365-Verwaltungs-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren von Microsoft 365 Enterprise-Diensten und-Anwendungen](configure-services-and-applications.md)
  
[Vorbereiten Ihrer Organisation für Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365-Integration in lokale Umgebungen](microsoft-365-integration.md)
  
[Verwalten von Microsoft 365-Endpunkten](managing-office-365-endpoints.md)
