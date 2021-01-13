---
title: Voraussetzungen zugeordneter Laufwerke für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 34b2186ea3f9129ae7bb602aee879d7d23424136
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841064"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Voraussetzungen zugeordneter Laufwerke für Microsoft Managed Desktop

Viele Unternehmensumgebungen haben Legacyanforderungen für zugeordnete Laufwerke, damit ihre Benutzer oder Teams Dateien freigeben und speichern können, oder für lokale Anwendungen. Microsoft empfiehlt nicht die Verwendung von zugeordneten Laufwerken mit Microsoft Managed Desktop. Stattdessen wird empfohlen, die Dateizugriffslösungen wie folgt zu modernisieren:
  
- Migrieren Sie zugeordnete Laufwerke, die von einzelnen Benutzern verwendet werden, zu OneDrive for Business. 
- Migrieren Sie zugeordnete Laufwerke, die von Teams zum Freigeben von Dateien verwendet werden, zu SharePoint Online. 
- Modernisieren oder ersetzen Sie Anwendungen, die lokale Dateifreigaben verwenden, um diese Anforderung zu entfernen.
  
Die Modernisierung dieser Dienste ermöglicht die beste Benutzererfahrung mit Microsoft Managed Desktop. Microsoft FastTrack Services kann Sie bei der Modernisierung Ihrer Umgebung mithilfe von Microsoft Cloud Services unterstützen. Sie können überprüfen, ob Sie für die FastTrack-Dienste bei [berechtigten](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) Diensten und Plänen berechtigt sind, und diese dann direkt kontaktieren, um sich auf Microsoft Managed Desktop vorzubereiten. Hintergrundinformationen zur FastTrack OneDrive for Business- oder SharePoint #A0 finden Sie unter [Datenmigration.](https://docs.microsoft.com/fasttrack/o365-data-migration)

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Zugeordnete Laufwerke auf Microsoft Managed Desktop
 
Wenn Sie zugeordnete Laufwerke für einige Verwendungsfälle nicht entfernen oder ersetzen können, sollten Sie eine Supportanfrage im Microsoft Managed Desktop Admin Portal übermitteln, damit sie für Microsoft Managed Desktop-Benutzer bereitgestellt werden.
    
Für eine solche Anforderung müssen Sie die folgenden Details in der Supportanfrage bereitstellen: 

- Alle UNC-Pfade zu Speicherorten für Dateifreigaben, die für Microsoft Managed Desktop Geräte zugeordnet werden müssen 
- Benutzergruppen, die Zugriff auf diese Dateifreigabeorte benötigen 
- Ein bestimmter Laufwerkbuchstabe, der (falls erforderlich) zugewiesen werden muss

Beispiel:

| Laufwerkbuchstabe | UNC-Pfad | Benutzergruppe |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

Es liegt in Ihrer Verantwortung sicherzustellen, dass Benutzer und Gruppen über die richtigen Berechtigungen für den Zugriff auf Speicherorte für Dateifreigaben verfügen und dass die lokalen Dateidienste weiterhin zugänglich sind. Darüber hinaus sollten Sie Ihre Anforderungen für solche Dateifreigaben so bald wie möglich entfernen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>So müssen zugeordnete Laufwerke in Microsoft Managed Desktop bereitgestellt werden
 
Stellen Sie sicher, dass zugeordnete Laufwerke nicht vermieden werden können, und dass Sie die Anforderungen sorgfältig überprüft haben, bevor Sie eine Dienstanforderung übermitteln. Führen Sie dann die folgenden Schritte aus:

1. Navigieren Sie [zu Microsoft Endpoint Manager,](https://endpoint.microsoft.com/) und wählen Sie "Problembehandlung + Support" aus, und suchen Sie dann im Abschnitt "Microsoft Managed Desktop" nach "Serviceanfragen".  
2. Übermitteln Sie eine Supportanfrage mit dem Titel "Bereitstellung zugeordneter Laufwerke", und geben Sie alle erforderlichen Dateifreigabedetails an.  
3. Microsoft Managed Desktop IT Operations wird mithilfe von Supportanfrageupdates informieren, wenn die Anforderung abgeschlossen wurde. Zunächst wird diese Konfiguration nur auf Geräten in der Testbereitstellungsgruppe bereitgestellt.  
4. Sie müssen testen und überprüfen, ob die von Microsoft Managed Desktop -IT-Vorgängen bereitgestellte Konfiguration wie erwartet funktioniert. Antworten Sie über die Registerkarte "Diskussion" in den Details derselben Supportanfrage, um microsoft Managed Desktop -IT-Vorgänge zu benachrichtigen, nachdem Sie die Tests abgeschlossen haben.  
5. Microsoft Managed Desktop IT Operations team will then deploy the configuration to the other deployment groups. 
