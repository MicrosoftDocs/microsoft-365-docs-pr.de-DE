---
title: Office 365 ATP für SharePoint, OneDrive und Microsoft Teams
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
description: Erweitern Sie Office 365 Advanced Threat Protection auf Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams, um eine sicherere Zusammenarbeit für Ihre Organisation zu ermöglichen.
ms.openlocfilehash: ad2b5e06dab99bb2cdbe4b0e4c1785d716d865f7
ms.sourcegitcommit: 6e01543b3fff50a28719478b19b644991ba7505a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38035715"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Office 365 ATP für SharePoint, OneDrive und Microsoft Teams

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Übersicht über Office 365 ATP für SharePoint, OneDrive und Microsoft Teams

Personen teilen regelmäßig Dateien und arbeiten mit SharePoint, OneDrive und Microsoft Teams zusammen. Mit [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) kann Ihre Organisation auf sichere Weise zusammenarbeiten. ATP unterstützt das erkennen und Blockieren von Dateien, die als bösartig identifiziert werden, in Teamwebsites und Dokumentbibliotheken.  
  
## <a name="how-it-works"></a>Funktionsweise

Wenn eine Datei in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams als bösartig identifiziert wurde, wird ATP direkt in die Dateispeicher integriert, um diese Datei zu sperren. In der folgenden Abbildung ist ein Beispiel für eine in einer Bibliothek erkannte schädliche Datei dargestellt.
  
[![Dateien in OneDrive für Unternehmen mit einem als bösartig erkannt](../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Obwohl die blockierte Datei immer noch in der Dokumentbibliothek und den Webanwendungen, mobilen Anwendungen oder Desktopanwendungen aufgeführt ist, kann die blockierte Datei nicht geöffnet, kopiert, verschoben oder freigegeben werden. Personen können jedoch eine blockierte Datei löschen. Hier ist ein Beispiel dafür, wie das auf dem mobilen Gerät eines Benutzers aussieht:
  
[![Löschen einer gesperrten Datei aus OneDrive für Unternehmen aus dem OneDrive-Mobile App](../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Je nachdem, wie Office 365 konfiguriert ist, können Benutzer möglicherweise eine blockierte Datei herunterladen. Hier sehen Sie, wie das Herunterladen einer gesperrten Datei auf dem mobilen Gerät eines Benutzers aussieht:
  
[![Herunterladen einer gesperrten Datei in OneDrive für Unternehmen](../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
Weitere Informationen finden Sie unter [Office 365 ATP für SharePoint, OneDrive, und Microsoft Teams aktivieren](turn-on-atp-for-spo-odb-and-teams.md).
  
## <a name="keep-these-points-in-mind"></a>Beachten Sie diese Punkte

- ATP wird nicht jede einzelne Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams überprüfen. Dies ist so vorgesehen. Dateien werden asynchron durch einen Prozess überprüft, der Freigabe-und Gast Aktivitätsereignisse zusammen mit intelligenten Heuristiken und Bedrohungs Signalen verwendet, um bösartige Dateien zu identifizieren.

- Stellen Sie sicher, dass Ihre SharePoint-Websites so konfiguriert sind, dass Sie die [moderne Benutzeroberfläche](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)verwenden. Wenn eine Datei als bösartig und blockiert identifiziert wird, können die Benutzer sehen, dass dies in der modernen Benutzeroberfläche aufgetreten ist, jedoch nicht in der klassischen Ansicht. ATP-Schutz wendet an, ob die moderne Erfahrung oder die klassische Ansicht verwendet wird; visuelle Indikatoren, die eine Datei blockiert, sind jedoch nur in der modernen Benutzeroberfläche vorhanden.
    
- Dateien, die in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig identifiziert werden, werden in [Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md) und in [Explorer (und Echtzeiterkennung)](threat-explorer.md)angezeigt.
    
- ATP ist Teil der allgemeinen Bedrohungsschutz Strategie Ihrer Organisation, die den Schutz vor Spam und Schadsoftware sowie sichere Links und sichere Anlagen umfasst. Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).
    
- Ein SharePoint Online Administrator kann bestimmen, ob Personen das Herunterladen von Dateien aktivieren können, die als bösartig erkannt werden. Dies erfolgt durch Ausführen des PowerShell-Cmdlets "SPOTenant" mithilfe eines DisallowInfectedFileDownload-Parameters (siehe [aktivieren Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>Quarantäne in ATP für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams

 Ab Ende Mai 2018 werden die [Quarantäne](quarantine-email-messages.md) Funktionen im Security &amp; Compliance Center auf ATP für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams erweitert.
  
Wenn eine Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig erkannt wird, wird die Datei zusätzlich zu ATP blockiert, wenn die Datei geöffnet oder freigegeben wird, und diese Datei wird in eine Liste mit isolierten Elementen eingeschlossen. (Klicken Sie im &amp; Security Compliance Center auf **Threat Management** \> **Review** \> **Quarantine** und Filter for **Content**.) 
  
Wenn Sie Teil des Office 365 Sicherheitsteams in Ihrer Organisation sind und über die erforderlichen Berechtigungen verfügen, die [im Office 365 &amp; Security Compliance Center zugewiesen](permissions-in-the-security-and-compliance-center.md)sind, können Sie Dateien herunterladen, freigeben, melden und löschen, die von ATP als bösartig aus der Quarantäne erkannt wurden.
  
- Durch das **Freigeben und melden** einer Datei wird der ATP-Block für die Datei in der jeweiligen Teamwebsite oder Dokumentbibliothek für SharePoint, OneDrive oder Microsoft Teams entfernt. Benutzer können die Datei dann öffnen, freigeben und herunterladen. Wenn die Option **Bericht an Microsoft senden** ausgewählt ist, wird die Datei als falsch positiv für Microsoft gemeldet. 
    
- Durch das **Löschen einer Datei** wird die Datei aus der Quarantäne entfernt. die Datei wird jedoch weiterhin blockiert geöffnet oder freigegeben. Die Datei muss auch in der entsprechenden Dokumentbibliothek oder Teamwebsite (SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams) gelöscht werden. 
    
- Durch das **Herunterladen einer Datei** können Sie die Datei für alle falsch positiven Ergebnisse herunterladen und analysieren. 
    
## <a name="next-steps"></a>Nächste Schritte

1. [Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden](malicious-files-detected-in-spo-odb-or-teams.md)
    
