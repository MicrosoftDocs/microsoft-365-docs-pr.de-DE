---
title: Sichern von Daten vor dem Umstieg auf Office 365 Business-Pläne
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Sichern Sie Outlook-, OneDrive-, Yammer- und SharePoint-Inhalte, bevor Sie Office 365-Abonnements wechseln oder wenn ein Benutzer die Organisation verlässt.
ms.openlocfilehash: 16fb6972869c3caf010c25cbe043dbf79f458531
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241899"
---
# <a name="back-up-data-before-switching-office-365-for-business-plans"></a>Sichern von Daten vor dem Umstieg auf Office 365 Business-Pläne

[] Wenn ein Benutzer auf ein anderes Abonnement umgestellt wird, das über weniger datenbezogene Dienste verfügt oder ein Benutzer die Organisation verlässt, kann eine Kopie von dessen Daten, die in Office 365 gespeichert sind, vor dem Umstieg in das neue Abonnement heruntergeladen werden.
  
## <a name="save-a-copy-of-outlook-information"></a>Sichern einer Kopie von Outlook-Daten

Wenn Benutzer über Outlook verfügen, können sie [E-Mails, Kontakte und Kalender in eine Outlook-PST-Datei exportieren](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91), bevor ihr Plan gewechselt wird. 
  
Nachdem der Wechsel zum neuen Plan abgeschlossen ist, können Benutzer [E-Mails, Kontakte und Kalender aus einer Outlook-PST-Datei importieren](https://support.office.com/article/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Sichern von in OneDrive for Business gespeicherten Dateien

Bevor sie auf ein anderes Abonnement umgestellt werden, können Benutzer[Dateien und Ordner aus OneDrive oder SharePoint herunterladen](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05). Diese werden dann an einem anderen Speicherort, wie z. B. in einem Ordner auf ihrer Festplatte oder einer Dateifreigabe im Netzwerk ihrer Organisation, gespeichert. 
  
## <a name="save-yammer-information"></a>Sichern von Yammer-Daten

Administratoren können alle Nachrichten, Notizen, Dateien, Themen, Benutzer und Gruppen in Form einer ZIP-Datei exportieren. Weitere Informationen finden Sie unter [Exportieren von Daten aus Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Entwickler können hierfür auch die [Yammer-API](https://go.microsoft.com/fwlink/p/?linkid=842495) verwenden. 
  
## <a name="how-to-save-sharepoint-information"></a>Sichern von SharePoint-Daten

Wenn ein Benutzer von einem Abonnement, in dem SharePoint Online verfügbar ist, zu einem Abonnent wechselt, in dem SharePoint Online nicht verfügbar ist, wird die Kachel **SharePoint** im Office 365-Menü nicht mehr angezeigt. 
  
Solange sich das neue Abonnement jedoch in derselben Organisation wie der befindet, in der der Umstieg erfolgt ist, sind die Benutzer weiterhin in der Lage, auf die SharePoint-Teamwebsite zuzugreifen. Sie können Notizbücher, Dokumente, Aufgabe und Kalender anzeigen und aktualisieren, indem sie die direkte URL der Teamwebsite aufrufen.
  
> [!TIP]
> Es wird empfohlen, dass Benutzer zur Teamwebsite wechseln, bevor der Wechsel des Abonnements erfolgt, um die URL in den Favoriten oder als Textmarke zu speichern. 
  
Standardmäßig weist die URL der Teamwebsite das folgende Format auf:
  
```
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

Hierbei steht _\<OrgDomäne\>_ für die URL der Organisation. 
  
Wenn die Domäne der Organisation beispielsweise contoso.onmicrosoft.com lautet, ist die direkte URL der Teamwebsite https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Natürlich können die Benutzer ihre SharePoint Online-Dokumente auch jederzeit von der SharePoint-Teamwebsite auf ihre lokalen Computer oder an einen anderen Speicherort herunterladen.