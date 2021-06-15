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
description: In diesem Artikel erfahren Sie mehr über die Tools und Techniken, die Sie verwenden können, um Microsoft 365 Konnektivität zu überwachen und aufrechtzuerhalten.
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924199"
---
# <a name="monitor-microsoft-365-connectivity"></a>Überwachen der Microsoft 365-Konnektivität

Nachdem Sie Microsoft 365 bereitgestellt haben, können Sie Microsoft 365 Konnektivität mithilfe einiger der unten aufgeführten Tools und Techniken aufrechterhalten. Sie sollten die offiziellen Richtlinien für [Dienstintegrität und -kontinuität](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) sowie unsere [bewährten Methoden für die Verwendung von Microsoft 365 in einem langsamen Netzwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)verstehen. Sie sollten auch die [Microsoft 365 Administrator-App](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) abrufen und unser Microsoft 365 für Unternehmen mit einem Lesezeichen versehen [– Administratorhilfe.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Überwachen Microsoft 365 Konnektivität

|Art der Überwachung |Beschreibung |
|:-----|:-----|
|**Benachrichtigung über neue Microsoft 365 Endpunkte** <br/> |Wenn Sie [Microsoft 365 Endpunkte verwalten,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)sollten Sie Benachrichtigungen erhalten, wenn wir neue Endpunkte veröffentlichen. Sie können unseren RSS-Feed mit Ihrem bevorzugten RSS-Reader abonnieren. Hier erfahren Sie, wie Sie [über Outlook abonnieren,](https://go.microsoft.com/fwlink/p/?LinkId=532416) oder Sie können [die RSS-Feedupdates per E-Mail an Sie senden](https://go.microsoft.com/fwlink/p/?LinkId=532417)lassen.  <br/> |
|**Verwenden von System Center zum Überwachen von Microsoft 365** <br/> |Wenn Sie Microsoft System Center verwenden, können Sie das [System Center Management Pack für Office 365](https://www.microsoft.com/download/details.aspx?id=43708) herunterladen, um noch heute mit der Überwachung Microsoft 365 zu beginnen. Ausführlichere Anleitungen finden Sie im Management Pack-Betriebshandbuch. <br/> |
|**Überwachen des Zustands von Azure ExpressRoute** <br/> |Wenn Sie mit Azure ExpressRoute für Microsoft 365 eine Verbindung mit Microsoft 365 herstellen, sollten Sie sicherstellen, dass Sie sowohl das Microsoft 365 Service Health Dashboard als auch die Azure [Reducing-Problembehandlungszeit mit Azure Resource Health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) verwenden. <br/> |
|**Verwenden von Azure AD Connect Health mit AD FS** <br/> |Wenn Sie AD FS für einzelne Sign-On mit Microsoft 365 verwenden, sollten Sie azure [AD Verbinden Health verwenden, um Ihre AD FS-Infrastruktur zu überwachen.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Programmgesteuerte Überwachung Microsoft 365** <br/> |Lesen Sie unsere Anleitung zur [Microsoft 365-Verwaltungs-API.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren Microsoft 365 Enterprise Dienste und Anwendungen](configure-services-and-applications.md)
  
[Vorbereiten Ihrer Organisation auf Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365 Integration in lokale Umgebungen](microsoft-365-integration.md)
  
[Verwalten Microsoft 365 Endpunkte](managing-office-365-endpoints.md)
