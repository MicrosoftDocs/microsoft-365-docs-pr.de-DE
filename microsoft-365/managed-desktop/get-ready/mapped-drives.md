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
ms.openlocfilehash: 04c3901155ecd80fad472e07e7e46620c3ddee1f
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289273"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Voraussetzungen zugeordneter Laufwerke für Microsoft Managed Desktop

Viele Unternehmensumgebungen weisen Legacy Anforderungen für zugeordnete Laufwerke auf, damit Ihre Benutzer oder Teams Dateien freigeben und speichern können, oder für lokale Anwendungen. Microsoft empfiehlt nicht die Verwendung von zugeordneten Laufwerken mit dem Microsoft Managed Desktop. Stattdessen wird empfohlen, die Dateizugriffs Lösungen wie folgt zu modernisieren:
  
- Migrieren Sie zugeordnete Laufwerke, die von einzelnen Benutzern verwendet werden, in OneDrive für Unternehmen. 
- Migrieren Sie von Teams verwendete zugeordnete Laufwerke, um Dateien für SharePoint Online freizugeben. 
- Modernisieren oder ersetzen Sie Anwendungen, die lokale Dateifreigaben verwenden, um diese Anforderung zu entfernen.
  
Durch die Modernisierung dieser Dienste wird die beste Benutzererfahrung mit Microsoft Managed Desktop ermöglicht. Microsoft-Kurzarbeits Dienste können Sie bei der Modernisierung ihrer Umgebung mithilfe von Microsoft Cloud Services unterstützen. Sie können überprüfen, ob Sie bei [berechtigten Diensten und Plänen](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) für die Dienstleistungen für die zeitlosen Dienste in Frage kommen, und sich dann direkt an den Microsoft Managed Desktop wenden. Hintergrundinformationen zu kurzOneDrive für Unternehmen oder SharePoint Online Migration finden Sie unter [Datenmigration](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Zugeordnete Laufwerke auf dem Microsoft Managed Desktop
 
Wenn Sie zugeordnete Laufwerke für einige Anwendungsfälle nicht entfernen oder ersetzen können, sollten Sie eine Supportanfrage im Verwaltungsportal von Microsoft Managed Desktop übermitteln, damit Sie für Benutzer von Microsoft Managed Desktop bereitgestellt werden.
    
Für eine solche Anforderung müssen Sie die folgenden Details in der Supportanforderung angeben: 

- Alle UNC-Pfade zu Dateifreigabe Standorten, die für Microsoft Managed Desktop-Geräte zugeordnet werden müssen 
- Benutzergruppen, die Zugriff auf diese Dateifreigabe Speicherorte benötigen 
- Ein bestimmter Laufwerksbuchstabe, der zugewiesen werden muss (falls erforderlich)

Zum Beispiel:

| Laufwerkbuchstabe | UNC-Pfad | Benutzergruppe |
|--------------|----------|------------|
| X  | \\\server\share\Marketing | ContosoMarketing |

Es liegt in ihrer Verantwortung, sicherzustellen, dass Benutzer und Gruppen die richtigen Berechtigungen für den Zugriff auf Dateifreigabe Standorte besitzen und beibehalten, und dass die lokalen Dateidienste weiterhin verfügbar sind. Außerdem sollten Sie die Anforderungen für solche Dateifreigaben so schnell wie möglich entfernen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>So haben Sie zugeordnete Laufwerke in Microsoft Managed Desktop bereitgestellt
 
Stellen Sie sicher, dass zugeordnete Laufwerke nicht vermieden werden können, und Sie haben die Anforderungen sorgfältig überprüft, bevor Sie eine Serviceanfrage übermitteln. Führen Sie dann die folgenden Schritte aus:

1. Navigieren Sie zum [Microsoft Managed Desktop Portal](https://aka.ms/mmdportal).  
2. Übermitteln Sie eine Supportanfrage mit dem Titel "Mapped Drives Deployment" im Abschnitt **Support > Supportanfragen** , und geben Sie alle erforderlichen Dateifreigabe Details an.  
3. Der Microsoft Managed Desktop-IT-Betrieb rät, wenn die Anforderung abgeschlossen wurde, mithilfe von Updates für die Supportanforderung ab. Diese Konfiguration wird anfänglich nur auf Geräten in der Test Bereitstellungsgruppe bereitgestellt.  
4. Sie müssen testen und überprüfen, ob die vom Microsoft Managed Desktop-IT-Betrieb bereitgestellte Konfiguration wie erwartet funktioniert. Antworten Sie mithilfe der Registerkarte Diskussion in der Support Anfrage, um Microsoft Managed Desktop-IT-Vorgänge zu benachrichtigen, nachdem Sie Ihre Tests abgeschlossen haben.  
5. Das Microsoft Managed Desktop-IT-Betriebsteam stellt die Konfiguration dann für die anderen Bereitstellungsgruppen bereit. 
