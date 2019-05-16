---
title: Vorbereiten von zugeordneten Laufwerken für Microsoft Managed Desktop
description: Wichtige Schritte, um sicherzustellen, dass
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b3fc4a4ed82c01188f348d2e494a0dbf7effc77a
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34079269"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>Vorbereiten von zugeordneten Laufwerken für Microsoft Managed Desktop

Viele Unternehmensumgebungen verfügen über Legacy Anforderungen für zugeordnete Laufwerke, damit Ihre Benutzer oder Teams Dateien freigeben und speichern können, oder für lokale Anwendungen. Microsoft empfiehlt nicht die Verwendung von zugeordneten Laufwerken mit Microsoft Managed Desktop. Stattdessen wird empfohlen, dass Sie die Dateizugriffs Lösungen wie folgt modernisieren:
  
- Migrieren der von einzelnen Benutzern verwendeten zugeordneten Laufwerke zu OneDrive for Business. 
- Migrieren von von Teams verwendeten zugeordneten Laufwerken zum Freigeben von Dateien für SharePoint Online 
- Modernisieren oder ersetzen Sie alle Anwendungen, die lokale Dateifreigaben verwenden, um diese Anforderung zu entfernen.
  
Die Modernisierung dieser Dienste ermöglicht eine optimale Endbenutzererfahrung mit Microsoft Managed Desktop. Microsoft-Support-Dienste können Sie bei der Modernisierung ihrer Umgebung unterstützen, indem Sie Microsoft Cloud Services verwenden. Sie können überprüfen, ob Sie bei [berechtigten Diensten und Plänen](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans) für die Dienste für den "Support"-Dienst berechtigt sind, und sich dann direkt an Microsoft Managed Desktop wenden. Hintergrundinformationen zur Migration von OneDrive for Business oder SharePoint Online finden Sie unter [Datenmigration](https://docs.microsoft.com/fasttrack/o365-data-migration).

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Zugeordnete Laufwerke auf Microsoft Managed Desktop
 
Wenn Sie für einige Anwendungsfälle keine zugeordneten Laufwerke entfernen oder ersetzen können, sollten Sie eine Supportanfrage im Microsoft Managed Desktop-Portal einreichen, damit diese für Microsoft Managed Desktop-Benutzer bereitgestellt werden.
    
Für eine solche Anforderung müssen Sie die folgenden Details in der Supportanfrage angeben: 

- Alle UNC-Pfade zu Dateifreigabe Speicherorten, die für Microsoft Managed Desktop-Geräte zugeordnet werden müssen 
- Benutzergruppen, die Zugriff auf diese Dateifreigabe Speicherorte benötigen 
- Beliebiger Laufwerkbuchstabe, der zugewiesen werden muss (falls erforderlich)

Zum Beispiel:

| Laufwerkbuchstabe | UNC-Pfad | Benutzergruppe |
|--------------|----------|------------|
| X  | \\\server\share\Marketing | ContosoMarketing |

Es liegt in ihrer Verantwortung, sicherzustellen, dass Benutzer und Gruppen über die erforderlichen Berechtigungen für den Zugriff auf Dateifreigabe Speicherorte verfügen, und dass die lokalen Dateidienste zugänglich bleiben. Außerdem sollten Sie Ihre Anforderungen für solche Dateifreigaben so bald wie möglich entfernen.

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>So stellen Sie zugeordnete Laufwerke in Microsoft Managed Desktop bereit
 
Stellen Sie sicher, dass zugeordnete Laufwerke nicht vermieden werden können, und Sie haben die Anforderungen sorgfältig überprüft, bevor Sie eine Serviceanfrage übermitteln. Führen Sie dann die folgenden Schritte aus:

1. Navigieren Sie zum [Microsoft Managed Desktop-Portal](https://aka.ms/mmdportal).  
2. Übermitteln Sie eine Supportanfrage mit dem Titel "Mapped Drives Deployment" über den Abschnitt **Support > Support** Requests, und stellen Sie alle erforderlichen Details zur Dateifreigabe bereit.  
3. Microsoft Managed Desktop-Vorgänge werden, wenn die Anforderung abgeschlossen wurde, mithilfe von Updates für Supportanfragen beraten. Diese Konfiguration wird anfänglich nur für Geräte in der Test Bereitstellungsgruppe bereitgestellt.  
4. Sie müssen testen und bestätigen, ob die vom Microsoft Managed Desktop Operations-Team bereitgestellte Konfiguration wie erwartet funktioniert. Verwenden Sie die Support-Anforderung zum Aktualisieren von Microsoft Managed Desktop-Vorgängen, nachdem Sie die Tests abgeschlossen haben.  
5. Microsoft Managed Desktop Operations Team stellt die Konfiguration dann in den anderen Bereitstellungsgruppen bereit. 