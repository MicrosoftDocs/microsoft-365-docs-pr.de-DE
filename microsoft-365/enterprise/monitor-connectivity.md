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
description: In diesem Artikel erfahren Sie mehr über die Tools und Techniken, die Sie zum Überwachen und Verwalten der Microsoft 365 können.
ms.openlocfilehash: db3811b70f91efb9fd1e9f023df12d0852ce0189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920776"
---
# <a name="monitor-microsoft-365-connectivity"></a>Überwachen der Microsoft 365-Konnektivität

Nachdem Sie die Microsoft 365 bereitgestellt haben, können Sie Microsoft 365 Konnektivität mithilfe einiger der unten aufgeführten Tools und Techniken beibehalten. Sie sollten sich mit den offiziellen [Richtlinien](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) für dienstliche Integrität und Kontinuität sowie mit unseren bewährten Methoden für die Verwendung von Microsoft 365 in einem langsamen [Netzwerk verstehen.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) Sie möchten auch die [](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) Microsoft 365-Admin-App nutzen und unsere Microsoft 365 - Admin Help als Lesezeichen [markieren.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Überwachen Microsoft 365 Konnektivität

|||
|:-----|:-----|
|**Abrufen einer Benachrichtigung über Microsoft 365 Endpunkte** <br/> |Wenn Sie Microsoft 365 [verwalten,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)möchten Sie Benachrichtigungen erhalten, wenn wir neue Endpunkte veröffentlichen, können Sie unseren RSS-Feed mit Ihrem bevorzugten RSS-Reader abonnieren. Hier erfahren Sie, wie [Sie Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) abonnieren, oder Sie können die [RSS-Feedupdates per E-Mail an Sie senden lassen.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**Verwenden System Center zum Überwachen Microsoft 365** <br/> |Wenn Sie Microsoft System Center verwenden, können Sie das [System Center Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) für Office 365 herunterladen, um Microsoft 365 zu starten. Ausführlichere Anleitungen finden Sie im Management Pack Operations Guide oder in diesem Blogbeitrag [Office365 Monitoring using System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) <br/> |
|**Überwachen des Zustands von Azure ExpressRoute** <br/> |Wenn Sie eine Verbindung mit Microsoft 365 mithilfe von Azure ExpressRoute für Microsoft 365 herstellen, sollten Sie sicherstellen, dass Sie sowohl das Microsoft 365 Service Health Dashboard als auch das Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) verwenden. <br/> |
|**Verwenden von Azure AD Connect Health mit AD FS** <br/> |Wenn Sie AD FS für einmaliges Sign-On mit Microsoft 365 verwenden, sollten Sie mit der Verwendung von Azure AD Verbinden Health beginnen, um Ihre [AD FS-Infrastruktur zu überwachen.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**Programmgesteuerte Überwachung Microsoft 365** <br/> |Lesen Sie unsere Anleitungen zur [Microsoft 365 Management-API](/office/office-365-management-api/office-365-management-apis-overview).  <br/> |

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>Verwandte Themen

[Konfigurieren Microsoft 365 Enterprise Dienste und Anwendungen](configure-services-and-applications.md)
  
[Machen Sie Ihre Organisation bereit für Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Netzwerkplanung und Leistungsoptimierung für Microsoft 365](network-planning-and-performance.md)
  
[Microsoft 365 integration in lokale Umgebungen](microsoft-365-integration.md)
  
[Verwalten Microsoft 365 Endpunkten](managing-office-365-endpoints.md)